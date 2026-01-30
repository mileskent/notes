A kernel module is an [[Object File]] that can be dynamically loaded in and out of the [[Kernel]] without rebooting.
* Kernel modules allow [[Monolithic Kernel]]s (like [[Linux]]) to dynamically add kernel functionality, e.g. a keyboard is plugged in, without recompiling the entire kernel
* All [[Driver]]s are Kernel Modules, but not all Kernel Modules are Drivers
* Find them in `/lib/modules/$(uname -r)/kernel/`. They end in the `.ko` (Kernel Object) extension.
# Commands

| Command                   | Action     | Description                                                                             |
| :------------------------ | :--------- | :-------------------------------------------------------------------------------------- |
| `lsmod`                   | **List**   | Shows all currently loaded modules and their sizes.                                     |
| `modinfo <name>`          | **Info**   | Displays metadata (author, license, description, parameters).                           |
| `sudo modprobe <name>`    | **Load**   | Intelligently loads a module and all its **dependencies**.                              |
| `sudo modprobe -r <name>` | **Remove** | Safely unloads a module and its unused dependencies.                                    |
| `insmod` / `rmmod`        | **Raw**    | Older, "dumb" tools that load/unload a single `.ko` file without checking dependencies. |
