---
date: 2026-01-29
aliases:
  - List Dynamic Dependendies
---
`ldd` is a command that displays the [[Shared Library|Dynamic Libaries]] required by a particular binary.

> [!Example] Running `ldd` on `ls`
> ```
> $ ldd /usr/bin/ls
> 	linux-vdso.so.1 (0x00007ffe6badf000)
> 	libselinux.so.1 => /lib64/libselinux.so.1 (0x00007f86e97d8000)
> 	libcap.so.2 => /lib64/libcap.so.2 (0x00007f86e97ce000)
> 	libc.so.6 => /lib64/libc.so.6 (0x00007f86e9400000)
> 	libpcre2-8.so.0 => /lib64/libpcre2-8.so.0 (0x00007f86e9732000)
> 	/lib64/ld-linux-x86-64.so.2 (0x00007f86e9842000)
> ```
