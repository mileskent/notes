---
date: 2026-01-29
aliases:
  - vdso
---
A tiny [[Shared Library|Shared Object]] used for optimization, brought to you by the [[Linux Kernel]]. The kernel is able to provide a memory mapping between a few [[Paging#Page|Pages]] of its memory and the [[Address Space]] of the [[Program]] that uses the vsdo shared object. This allows the program to call [[Computer Science/Architecture/Programming/Function]]s in the kernel's address space as if it were part of its own address space. This is efficient, because it eliminates [[Context Switch|Context Switching]] from user to kernel mode and back for trivial hardware requests from the kernel that don't really need kernel level protection, e.g. requesting the system time.