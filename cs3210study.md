# Notes

## Ch 0
- fork and exec, bit about why not combine them, and about what happens in the shell when you type a command
    - One reason they are separate is because it enables IO redirection like in cat < input.txt
    - xv6 has no notion of users; in linux terms, all xv6 user programs run as *root.* In OS's with users, each user has permissions (rwx). This is unrelated to the concept of ring level, i.e. ring 0 vs ring 3. To be explicit, root is ring 3. Even a root application has to ask the kernel via syscalls for privledged tasks. 
    - File descriptor
    - IO FD
        - process FD table behavior
        - Process FD replacement behavior 
        - Not only do file descriptors abstract away many details (e.g. where data in a pipe or file is stored), they also are defined in a way that simplifies interaction.
    - Xv6 syscalls
    - Esp pipe, advtanges of pipes over temp files
    - Principle of Unix philosophy is ideal for OS design
    - Runcmd vs exec
    - Filesystem
    - Processes have a cwd
        - Relevant Sys calls
        - Inodes
    - POSIX IO
    -  Any operating system must multiplex processes onto the underlying hardware, isolate processes from each other, and provide mechanisms for controlled inter-process communication.
    - Multiplexing
        - Isolation
        - Interaction

## Ch 1
- Monolithic vs Micro Kernel, or in other words, what OS responsibilities do we put in the kernel vs user land?
    - When the entire OS resides in the kernel, we call that OS a monolithic kernel
        - Pros
            - OS modules can easily share resources and cooperate
                - OS designer doesn’t have to decide which modules deserve to be in the kernel
            - Cons
            - “Interfaces between modules are complex” I don’t understand this
                - Very high surface area for mistakes, which means exploits and bugs which means a peripheral module can lead to CVEs and crashes of the entire OS
                - Worse extensibility 
        - When only the core OS resides in the kernel, and the rest as user land servers, we can it a micro kernel
        - Pros
            - Converse of monolithic kernels cons
                - Extensibility
            - Cons
            -  Context Switching overhead and lack of integrated resource sharing
    - Isolation
    - To achieve strong isolation it’s helpful to forbid applications from directly accessing sensitive hardware resources, and instead to abstract the resources into services.
        - Strong isolation requires a hard boundary between applications and the operatingsystem. If the application makes a mistake, we don’t want the operating system to failor other applications to fail. Instead, the operating system should be able to clean upthe failed application and continue running other applications. Process isolation, OS-process isolation. Or in other words kernel vs user isolation. 
        - Processors provide HW support for kernel vs user mode
    - User vs Kernel, User/Kernel Space, Privileged instructions
    - Only kernel can do IO, expect if MMIO
    - Trace from User application wanting IO, to IO
    - User app calls user space syscall fn
        - User space syscall fn loads its syscall id into %eax, and its args into other registers, then calls trap int T_SYSCALL
        - We are now in the kernel. int T_SYSCALL calls the interrupt handler, which loads the interrupt handler at index T_SYSCALL. Index T_SYSCALL in the IDT contains a Gate Descriptor to the syscall dispatch fn. note int is an ISA instruction, not a syscall. IDT tells CPU where to go on traps.
	        - Trap frame data structure tells the kernel: where the trap is coming from, where to return (if needed)
        - Gate descriptor contains Segment Selector and Offset. Offset is the fn ptr. Segment Selector is an index into the GDT which contains Segment Selectors. The Segment Selector we index give us information on a Segment: base, size, descriptor privledge level (ring clearance requirement), and permissions. The int instruction checks that the segment selector privilege permits our current ring level. 
            -  Processors provide a special instruction that switches the processor from user mode to kernel mode and enters the kernel at an entry point specified by the kernel. This is int.
        - Jump into kernel mode and use gate descriptor offset to jump to fn
        - Kernel calls the fn ptr and th syscall dispatch fn uses %eax to decide what kernel space syscall fn to dispatch
        - Call the kernel space syscall fn, kernel validates arguments
        - Syscall execs IO is handled
        - Return to user space
	        - run trapret
		        - pop user reg
		        - restore user eip and esp
		        - run iret to drop PL back to ring 3
    - User space processes shall not decide kernel space entry point, and this could be used to bypass kernel validation, which would entail full ring 0 escalation
    - Isolation
    - Processes: individual mode flag, address spaces (pd/pt/pages), time slicing
        - Each process has both its own and the kernels memory mapped in, meaning that when we do syscalls, the kernel can directly modify the user memory and only needs to mode switch
        - Each process has both a unique  kernel and user stack.
        - Threads
    - Context switch vs mode switch

* BIOS data area exists between the kernel and user in virtual address space

* Tracing from power-on to entering the shell
	* Computer powers on, physical memory empty, **16 bit real mode**
	* Computer always runs BIOS upon powering on, loads from reset vector
		* BIOS firmware is on the motherboard's ROM
		* CPU executes BIOS from directly on the ROM
	* BIOS begins executing
		* BIOS scans disk for boot block
			* The boot block is also referred to as the Master Boot Record (MBR)
		* 512 byte Boot block is found and loaded into physical memory 0x7c00
		* Start to execute contents of Boot block, called Boot loader
	* Bootloader begins executing
		* Transitions to **32 bit protected mode**
			* Loads the GDT
			* Enables protected mode with cr0 |= CR0_PE
			* Load 32 bit segment selector
		* Loads the kernel ELF binary into physical memory at 0x100000
		* Begins executing the kernel at its entrypoint (entry.S) after checking the kernel's ELF headers, and parsing the entrypoint from the ELF
	* Kernel begins executing
		* entry.S assembly
			* Sets up a page table to map physical 0 to physical kernel space end to this same thing, shifted up by KERNBASE = 0x80000000
				* Enable 4MB page sizes
					* cr4 |= CR4_PSE, set PDE PTE_PS bits
				* Set Page Dir Base Register
					* cr3 = phys addr &entrypgdir
					* entrypgdir is statically defined in main.c, that is temporary, just for the duration of entry
			* **Enable Paging**
				* cr0 |= CR0_PG | CR0_WP
			* Set stack pointer to the top of the stack (stack grows down)
				* esp = top of stack in memory
			* indirect jump to main (vadd space)
		* main.c ANSI C
			* Virtual memory is now in effect and we are in the ANSI C code, thanks to entry.S
			* Init physical page allocateor for the 4MB of RAM that entrypgdir can see
				* kinit1
			* Set up the real kernel page table kpgdir that readies vmem for all of RAM
				* kvmalloc
			* Init a bunch of stuff
				* "Multi-Processor", detects cores: mpinit
				* "Local APIC": lapicinit
				* "Segment Descriptors/GDT": seginit
				* "Disable PIC": picinit
				* "Initialize modern I/O APIC": ioapicinit
				* "Console": consoleinit
				* "UART serial port": uartinit
				* "Process Table": pinit
				* "Trap Vectors": tvinit
				* "Block buffer": binit
				* "File Table": fileinit
				* "IDE disk controller": ideinit
			* Boot other codes
				* startothers
			* Expands physical page allocator to the rest of RAM
				* kinit2
		* Allocate the primordial init user process
			* userinit
				* allocates a process PCB and its page dir and page table and gives info to initcode.S
				* puts a fake trapframe on the top of the kernel stack
				* loads initcode.S into memory
		* mpmain
			* Load IDT register onto CPU core
				* idtinit
			* Tells startothers other CPU cores we have started on this core
				* atomic_store(&mycpu()->started, 1);
			* Call scheduler (infinite loop)
				* scheduler
		* Scheduler executes userinit process
			* Scheduler finds the RUNNABLE process PCB that userinit created and tries to schedule it
			* When we try to context switch to the fake process, a fake trapframe gets triggered based on the kernel stack which sends the PC to vaddr 0 which is where initcode.S is
			* Start executing initcode.S which sets up the init process to be the first user process by manually calling exec on it in assembly
			* init sets up the console, fd, etc. and call the sh process



> [!question]- KERNBASE limits the amount of memory a single process can use, which might be irritating on a machine with a full 4 GB of RAM. Would raising KERNBASE allow a process to use more memory?
> 
> Raising KERNBASE would allow user processes to use more of the virtual address space. However, this would be in a zero sum manner, taking away from the kernel, without actually expanding virtual memory. xv6 is 32 bit, so you cannot just increase virtual address space beyond what is addressable by 32 bit pointers. However, modifying the kernel like in Lab 1 to dynamically set PHYSTOP, which gives you access to more physical memory, but this doesn't change virtual memory.

## Ch 2

This chapter is on Paging

Eflags Register. The eflags register contains transient state related to the execution of the CPU.
* Arithmetic Status Flags
	* Carry, zero, sign, overflow
* System Flags
	* interrupt enabled (mask interrupt), trap, io priviledge requirement
* Other stuff


PTE flags


Registers. Notably: eax, esp, eip.

| Register | Name/Purpose                |
| :------- | :-------------------------- |
| EAX      | **A**ccumulator Register    |
| EBX      | **B**ase Register           |
| ECX      | **C**ount Register          |
| EDX      | **D**ata Register           |
| ESI      | **S**ource **I**ndex        |
| EDI      | **D**estination **I**ndex   |
| EBP      | **B**ase **P**ointer        |
| ESP      | **S**tack **P**ointer       |
| EIP      | **I**nstruction **P**ointer |

![[Pasted image 20261019221036.png]]
* ![[Pasted image 20261018225005.png|650]]
	* PTE flags take note
* virtual address space
	* ![[Pasted image 20261018211533.png|389]]
	* ![[Pasted image 20261018224931.png|497]]

* xv6 maps the kernel into every process address space. It does this so that it only has to mode switch when a process needs to do something with the kernel. 
	* The problem with this is that PHYSTOP cannot be more than 2 GB, because KERNBASE + 2GB is the end of 32 bit addressable memory (not accounting for MMIO @ 0xfe000000 which makes it even sooner).
	* Furthermore, it is less secure to have the kernel and user memory mapped to the same space.
* It seems like there is a guard page between process data and stack region. It's purpose is to act as a grace region for stack overflows, because the stack grows downwards. The guard page has it PTE metadata set such that any access causes a page fault; present = 0. This is a simple way to get graceful termination of when the stack overflows, and prevents the data region from being clobbered. ![[Pasted image 20261018231114.png|411]] 
* invlpage -> invalidate cached entry in TLB, also reload cr3 invalidates all cached entries
* xv6 uses super pages only temporarily for entrypgdir in the bootloader. We use super pages here in order to map the kernel before full page allocation is running. Without super pages, the code would become more complex, as entrypgdir would no longer be able to simple map a 4 MB chunk all at once. Rather, it would have to construct the neccessary page tables to support many 4 KB pages in order to map this same region.
* sbrk takes pages
* You can make null pointer dereferences trigger a page fault my creating a guard page at address 0x0

* kalloc is free to allocate any free page within virtual kernel memory from the P2V(end) and P2V(PHYSTOP). The end marker indicates the end of the kernel's instructions and static data. It always returns exactly one virtual page (4 KB). For example, allocating a pgdir or pgtable, we kalloc a page to store the array. 


## Ch 3
This chapter is about traps, interrupts, and drivers, isolation

* Ring/Priviledge Levels
	* 0, 3. Others don't matter
	* CPL is Current Privilege Level, which is stored in the %cs register and represents the privilege level with which the x86 currently executes instructions
	* DPL is Descriptor Privilege Level, which is the privilege level specified within a descriptor (such as an IDT entry) against which priviledge checks are performed, i.e. we check that CPL is sufficient priviledge to access a segment that has a DPL


* Prefacing descriptor table mappings
	* GDT/LDT - Global/Local Descriptor Table
		* Key
			* Segment Selector
				* Code Segment Selector: a segment selector for code
		* Value
			* Segment Descriptor: segment's base, limit, perms
				* Code Segment Descriptor: a segment descriptor that contains code
	* IDT - Interrupt Descriptor Table
		* Key
			* Interrupt Handler ID, e.g. T_SYSCALL
		* Value
			* Gate Descriptor: contains the follow information for a Interrupt Handler
				* Code Segment Selector (%cs) of the Interrupt Handler fn
				* Instruction Pointer (%eip) of the label of the Interrupt Handler fn
				* DPL of the **Gate***
					* Notably the GD DPL *does not* have to match the DPL of the CS. In fact, it often *does not* match. For example, T_SYSCALL has a Ring 3 DPL so that users can trigger an interrupt. Meanwhile, the DPL of the CS of the syscall handler is Ring 0. Think of the Gate DPL as controlling access of the "doorbell" to trigger a trap, whereas who can actually has priviledge to execute the handler is isolated from and irrelevant to the ringer of the doorbell. 
				* Metadata
	
* IDT  maps interrupt vector (id) $\rightarrow$ Gate Descriptor

Tradeoffs of different levels of paging
* More levels means less memory overhead
* More levels means slower lookup given a TLB miss
* Everything more than one level does not need contiguous memory

## Ch 4
Locking

* Spinlock, spins unless the lock is releasedA
	* Lower overhead, more pervasive
* Sleeplock, sleeps until the lock is released
	* Leave interrupts enabled, cannot be used in interrupt handlers
	* Used mainly in filesystem
* Deadlock



## Ch 5
* Scheduling is an isolation mechanism to conceal the existence of processes from one another.
* 
* Conditional Synchronization
	* Sleep
		* sleep(channel, lock) releases the CPU burst and listens to channel for a signal to wakeup
	* Wakeup
		* wakeup(channel) sends a signal to channel to wakeup
	* This process uses the process metadeta marker, adding SLEEPING. Sleep sets SLEEPING. Wakeup sets RUNNABLE.
* Lost Wakeup
	* In a data race between the receiver confirming it needs to sleep and and it actually sleep, the producer sends data and calls wakeup. The wakeup does nohing, and the receiver sleeps for too long.
	
## GDB
* p/x $reg prints the raw hex of reg
* x/x reg dereferences the value, gives mem\[$reg\]

## Misc
- Figure out correspondence to LC3 registers, eg PTBR, PC, etc
* Other registers? eax?
* EIP is the PC
* ESP is stack pointer
* EBP is frame pointer
* IDT Register
- Control Registers: crX
	- cr3: page dir PTBR; pointer to the current proccess' page dir
	- cr0: 
	- cr4: Extended CR; set variosu architectural extensions that aren't part of the 386 design
- powers of 2 for different storage sizes, needed for PHYSTOP to GB conversion, for example.



# Labs
## Lab Quiz 1



# PExam
## Q1
## Q2
## Q3
Youur friend Robert is construction a new 32 bit CPu architecture and considering makin the vmem page size on his architecture 32 bytes, much smaller than the class 4 kb page
#### A
> Would you expect a kernel runninng on top of Rob's architecture to be more or less memory efficient than a classic 4kb page architecture. Please explain why.

- Offset: for a 32 byte page size means offset is 5 bits.
- PPN: 32 - 5 = 27 bits

What I am wondering for this question is what are the tradeoffs of different page sizes.
- Less internal fragmentation for smaller pages
- Smaller pages get us a bigger page table
- More TLB misses because the TLB size stays the same, but there are far more pages to cache
- More Page faults for the same reason

It is less memory efficient.

#### B
> Robert also wants his hardware to have a robust tracking and permisison system, adding a permission bit for reading, writer, user/superuser, a control bit to disable HW caching and some Hw monitoring bits for access,, and dirtyy to each page,


### Q4
#### A
Marking the user space stack as nonexecutable makes sense because the stack is not meant to be executed. The user programs have control over the stack, so if the stack can be executed, this could pose security risks.
#### B
- **Parse ELF Program Header Flags:** The ELF binary format contains program headers (`elfprog`) that specify the permissions for each segment (such as read, write, and execute flags via `p_flags`). `exec` must inspect these flags for each loadable segment rather than treating all memory segments uniformly.
- **Differentiated Page-Table Permission Mapping:** When `exec` allocates and loads segments into memory (using functions like `allocuvm` or `loaduvm`), it must pass distinct permission flags to the page-table mapping functions (`mappages`):
    - **Code Segment:** Set the execute bit enabled (and typically clear the write bit to make the text segment read-only).
    - **Static Dataspace (Data/BSS):** Keep the execute bit cleared (non-executable) while retaining read/write permissions.
- **Update Underlying VM Helpers:** Modify helper functions called during execution loading so they can accept and apply granular permission flags (including the architecture's execute bit) directly to the corresponding Page Table Entries (PTEs).

### Q5
#### A
Second Chance clock thing. See [[Replacement Algorithm|Page Replacement Algorithms]].

Treat the present bit as the accessed bit. Use this bit for both purposes at the same time. 

#### B
The access bit second chance semantics remain the same. The present bit semantics stay the same, its just that we have to unnessarily remap the page when it already does have a mapping.

### Q6
Response time
B
B

### Q7
#### A
Inconclusive

#### B
Put x = 10 in the T1 lock

# Pexam 2
## Q1
#### A
You can use 5 | 5 | 6 for the split. 6 bits for the regular 64 B page. The page dir and page table both evenly split 10 bits.
#### B
* 2^5 page dir entries, 2^5 page table entries, 2^6 sized pages
* Total bytes used by all page tables.
	* 2^5 * 16 + 2^5 * 2^5 * 16 + (2^5 * 2^5) * (2^6) bits
* Virtual memory allocated by process.




# Tmp
## Registers
CPU registers on x86.
* Various different kinds (in lecture)
* EFLAGS holds current CPU state
# Segment Selectors

Register Name/Purpose
CS Code Segment
DS Data Segment
SS Stack Segment
ES Extra Segment
FS F Segment
GS G Segment

### Segmentation
The original and simple way to do virtual memory. 
* Segmentation divides the physical memory into different “segments”
	* Each segment then appears like its own unique physical memory.
	* Segments typically have an “offset” and “size” property
	* Provides simple separation of memory spaces between processes
* x86 supports segmentation (on by default)
	* 16-bit real mode has simple segmentation
	* 32-bit mode uses more complex segmentation

Segmentation permissions are per segment

Postsegmentation in x86, addresses are called linear addresses

Segmentations provides the following abstractions
* Isolation (non-overlapping segments are isolated)
* Multiplexing (multiple processes can share the same physical memory)

* Segmentation not really used today (mostly disabled on x86_64) in favor of paging –
why?
	* Segmentation requires contiguous physical memory segments (versus arbitrary page mapping)
	* Segmentation permissions are per-segment (versus per-page, which is finer grained)


> [!Question]- Why would we want segmentation over paging?
> * Less overhead than Paging
> * Simple, which can be fine for specific edge applications



#### Real Mode vs Protected mode
Protected mode is the mode you will interact with 99% of the time. Real mode (16 bit) is the default state of the x86 processor for backward compatibility with the original Intel 8086. On systems with a BIOS, it switches in the early stages of the boot process. For UEFI systems, literally the first few assembly instructions of the boot process. This is muxed via CR0.PE.

#### Real Mode Segmentation
Code, data, and stack exist in different segments
* Real mode uses a specific type of segmentation model
* Linear address space for a program/OS consists of 64K segments
* Max linear address space available in real mode is 1MB (2^20 bytes)
* A program can only access up to 6 segments at a time
* Must load segment selector into a segment register befor

#### Protected Mode Segmentation
* In 32 bit mode, segment registers aren’t direct offsets
	* Instead, they point into the “Global Descriptor Table” or GDT
	* This table holds segment information
		* It isn’t just an offset, but contains
			* Region bounds
			* Protection (read/write access)
			* …and more
* Segment selectors then point to indexes in GDT
* Global Descriptor Table (GDT)
	* Memory segments which apply to all processes
* Local Descriptor Table (LDT)
	* Private to each process, used very little in modern OS, due to [[Paging]]
	* Registers point to GDT or LDT as appropriate (CS, DS, etc.)
* Task State Segment (TSS)
	* Mainly used for returning from traps

## x86 Assembly
* AT&T syntax: op src, dst
* Operands can be registers, constant, mem via reg, mem via constant
### Instruction Classes
* Data Movement 
* Arithmetic
* I/O
* Control
* String
* System

## Memory Mapped I/O
A way to use normal physical memory addresses to access device memory by having them mapped to one another.

* Use normal physical memory addresses
	* Gets around limited size of I/O address space
	* No need for special instructions (i.e., no 1024 limitation)
	* System controller routes to appropriate device
* Works like "magic" memory:
	* Addressed and accessed like memory
	* Reads and writes can have "side effects"
	* Reads can come from external objects (e.g., a hard drive)


# Boot Process
Most OS's have a three stage boot process
* BIOS
	* Enter via Reset Vector
	* Initialize lowest-level hardware details
	* Loads & begins executing the boot block
* Bootloader
	* Initial Processor Setup
	* Load Kernel and Execute
* Kernel
	* Actual executing kernel

## Reset Vector
* Most CPUs are hardcoded to start at a reset vector
	* Default location CPU looks at to find the first instruction to
	execute after a reset
	* 80386 and newer: Set IP -> 4GB - 16B (0xfffffff0)
	* 80286: 1MB - 16B (0xffff0) (IP = 0xfff0, CS = 0xf000)
	* ARM: 0x00
* x86 has a well-defined boot procedure
	* See “Minimal Boot Loader for Intel Architecture” (page 7):

* Bootstrap processor powers on
* First address the CPU fetches and executes is at 0xff ff ff f0 (reset vector)
* Addresses ROM/Flash device at the top of the ROM
* Bootloader must always contain a jump to initialization code in the top 16 bytes. Why?

# Boot Block
* Boot block is 512 bytes

Bootblock is in real mode
* x86 is backwards compatible with binaries from the 70s
* When the bootblock starts executing, the CPU is in 16 bit real mode
* Provides a naïve memory addressing model with physical access to the memory

Boot block sets up the following
• x86 state (e.g., registers)
• Memory referencing model (e.g., segmentation)
• Switch processor to 32-bit protected mode
• BIOS features (e.g., memory aliasing)

# BIOS Handover: real mode
• Real mode is 16 bit with 16 bit registers!
	• 16 bit segmented memory model introduced with 8086


> [!Question] What the fuck is *Real Mode*?

• Physical Address (PA) = 16 * segment register + offset (IP)
	• e.g., PA = 16 * CS + IP
	• CS = 0xf000, IP = 0xfff0
	• CS * 16 = 0xf0000
	• 16 * CS + IP = 0xffff0

"Real Address Mode Model Figure on slides"

# Memory Layout
Insert memory table from lecture, e.g. BIOS shadow, BIOS data, etc

# Protected Mode
# Initial Processor Mode
Hardware asserts top 3 bytes as high so that we can use 16 bit mode

Need to make sure BIOS is reachable in both modes, 32 bit address space and 20 bit addr space both at once, aliased to each other

# Full Boot Sequence Recap
• CPU comes out of reset
	• Hardwired first fetch at 0xFFFFFFF0
	• Must jump in the first 16 bytes
• BIOS initializes low-level hardware
	• Memory controller, chipset, etc.
• BIOS reads MBR (sector 0) of the boot device
	• Loads one 512-byte sector
• BIOS jumps to the loaded boot block (0x7C00)
• Bootloader prepares CPU
	• Switch to protected mode
	• Load kernel, then jump to its entry

BIOS $\rightarrow$ Bootloader $\rightarrow$ Kernel

Layout
* MBR (512 Bytes)
* Boot Code (446 bytes)
* Partition Table (64 bytes, 4 entries x 16 bytes)
* Signature (2 bytes)




| **System call**             | **Description**                            |
| --------------------------- | ------------------------------------------ |
| `fork()`                    | Create a process                           |
| `exit()`                    | Terminate the current process              |
| `wait()`                    | Wait for a child process to exit           |
| `kill(pid)`                 | Terminate process pid                      |
| `getpid()`                  | Return the current process's pid           |
| `sleep(n)`                  | Sleep for n clock ticks                    |
| `exec(filename, *argv)`     | Load a file and execute it                 |
| `sbrk(n)`                   | Grow process's memory by n bytes           |
| `open(filename, flags)`     | Open a file; the flags indicate read/write |
| `read(fd, buf, n)`          | Read n bytes from an open file into buf    |
| `write(fd, buf, n)`         | Write n bytes to an open file              |
| `close(fd)`                 | Release open file fd                       |
| `dup(fd)`                   | Duplicate fd                               |
| `pipe(p)`                   | Create a pipe and return fd's in p         |
| `chdir(dirname)`            | Change the current directory               |
| `mkdir(dirname)`            | Create a new directory                     |
| `mknod(name, major, minor)` | Create a device file                       |
| `fstat(fd)`                 | Return info about an open file             |
| `link(f1, f2)`              | Create another name (f2) for the file f1   |
| `unlink(filename)`          | Remove a file                              |




# Isolation
* Hardware Isolation, e.g. Processor rings
* Address Spaces 
* Time Slicing
* Interrupts
## Tradeoffs
* Isolation can be desirable because it prevents outside sources of failure, danger, chaos. This meaning we have higher predictability and determinism.
* Isolation can be undesirable because it prevents cohesion & collaboration. This can have the side effect of worse performance.

# Kernel Threading Models
* Many-to-One
	* All user processes have one kernel thread
	* Bad
* One-to-One
	* Each user process has its own kernel thread
	* Ubiquitous
* Many-to-Many
	* Maps a pool of user threads to a pool of kernel threads
	* Scheduler Activations
* Hybrid

# Kernel Types
![[Pasted image 20261019220608.png|351]]

# Pinned Page
You can pin pages to prevent them from being evicted. 

# Page Cache
The Page Cache is a cache for files, that exists in a reserved section of physical RAM, and is managed by the kernel

# mmap
When you mmap, the kernel allocates a region of the process' memory to serve as a one to one Virtual Memory Area for that file, while the actual file on disk becomes the swap space for its own VMA. However, the mapping is not to the actual file on disk through magic, but rather to that file's entries in the Page Cache. Once the VMA exists, all the subsequent virtual memory behavior is precisely the same behavior as if there was no mmap. The mmap's VMA is process specific. Cross process communication happens instantly through the Page Cache; when a process writes the VMA, all other processes can instantly see the change, because their individual VMAs are mapped to the exact same physical RAM pages in the Page Cache. It is basically like having a bunch of hardlinks to the same inode or a bunch of pointers to the same datum, but for virtual memory.


# Descriptor Tables
* GDT
	* Describes segments across the entire system
* IDT
	* IDT tells CPU where to go on traps with Gate descriptors
* LDT
	* GDT but local to a process

# Maskable Interrupts
Maskable Inerrupts can be ignored. sti and cli. Non Maskable Interrupts can never be ignored. You can have both at the same time.

# Page Replacement Algorithms

# Total Store Ordering
any W-R where the W and R are different variables can be reordered



