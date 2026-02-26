---
date: 2026-02-26
aliases:
  - FHS
---
*The [[Filesystem]] Hierachy Standard* is the official convention that defines the [[Directory]] structure and contents in [[Linux]] distributions and other [[UNIX]]-like operating systems. It is maintained by the [Linux Foundation](https://en.wikipedia.org/wiki/Linux_Foundation).

# UsrMerge
Historically the root level and usr level directories were separate, due to [[Storage]]-imposed space limitations meaning that root and usr were separate [[Hard Disk Drive|Hard Disks]]. However, we no longer physically separate them, because the space constraint no longer exists, and because the separation causes confusion. Merging the two makes snapshotting and atomic updates easier.

In practice, the merging just means that every root level instance of a directory like `bin` is [[Symlink|Symlinked]] to its usr equivalent.

# Root
* `/` is the root/trunk/base/head of the filesystem, within which everything else lives.

# Home
* `/home` is where user owned directories live, e.g. `/home/alice`, `/home/bob`
* `/root` is the home directory equivalent for the [[Root User]]

# Binaries
* `bin` contains general purpose binaries that everyone can use
* `sbin`contains binaries that only the Root User should be using, i.e. "System Binaries"

| Directory    | Binaries         | System Binaries   | Purpose                        |
| :----------- | :--------------- | :---------------- | :----------------------------- |
| `/`          | `/bin`           | `/sbin`           | Bare minimum                   |
| `/usr`       | `/usr/bin`       | `/usr/sbin`       | Standard. [[Package Manager]]. |
| `/usr/local` | `/usr/local/bin` | `/usr/local/sbin` | Manually installed.            |
See [[#UsrMerge]], i.e. `bin -> usr/bin, sbin -> usr/sbin`

# Libraries
* `lib` contains 32 bit libaries
* `lib64` contains 64 bit libaries

| Directory    | 32 bit           | 64 bit             | Purpose                        |
| :----------- | :--------------- | :----------------- | :----------------------------- |
| `/`          | `/lib`           | `/lib64`           | Bare minimum                   |
| `/usr`       | `/usr/lib`       | `/usr/lib64`       | Standard. [[Package Manager]]. |
| `/usr/local` | `/usr/local/lib` | `/usr/local/lib64` | Manually installed.            |
See [[#UsrMerge]], i.e. `lib -> usr/lib, lib64 -> usr/lib64`

# Optional
* `/opt` is for manually installed *optional* software. 
	* e.g. `/usr/bin/google-chrome -> /opt/google/chrome/google-chrome`

# Hardware 
* `/dev` contains handles to hardware via files
	* e.g. hard drive might be at `/dev/sda`
	* e.g. webcam might be at `/dev/video0`
* `/media` or `/mnt` are where the system automatically "mounts" removable media devices into the filesystem

# Configuration
* `/etc` entirely contains files relevant to system configuration. "Et-cetera".
	* `/etc/passwd` is a list of all [[User]] accounts; usernames, user ids, group ids, home directory paths, and the type of shell they use
	* `/etc/shadow` has encrypted passwords and account expiration information
	* `/etc/sudoers` defines which users and groups are allowed to runn commands as root using [[sudo]]
	* `/etc/hostname` oneliner file that contains the hostname of the machine
	* `/etc/os-release` is basically the ID for the machine
	* `/etc/fstab` is the "Filesystem Table" that tells the OS which hard drives, partitions, or networks shares to automatically mount upon boot
	* `/etc/hosts` is a local address book that maps [[IP]]s to hostnames. A [[Domain Name System|DNS]] cache.
* `$HOME/.config`

# Temporary
* `/tmp` is where "Temporary"/Ephemeral data gets stored. It is automatically wiped.
* `/run` is a temporary storage area for system data that has accumulated during the runtime of the OS since the last boot. It stores [[Process ID|PID]]s and [[Socket]]s. It also holds information about logged-in users and temporary network settings.

# Magic
* `/proc` is a window into the [[Linux Kernel]] that essentially acts as a [[File]]-driven API for either querying information from the kernel, or requesting the kernel to do something. Instead of some special command to query some information from the kernel, you can simply just read a particular file in `/proc` to get that information. Because `/proc` is magic, the [[inode|inodes]] located there are posers! They are ephermeral, exist only in RAM, and are generated on-demand.
	* e.g.  `/proc/1234/` contains information about [[Process]] number 1234
	* e.g. `/proc/cpuinfo` contains information about the [[CPU]]
	* e.g. `/proc/meminfo` contain information about [[RAM]] usage
	* e.g. `/proc/sys` can be written to tune kernel configuration
* `/sys` stores a structures view of every piece of hardware connected to the machine. Unlike, `/proc`, `/sys` alows you the *change* thing by writing the files. Unlike `/proc/sys`, `/sys` is for hardware interaction, whereas the former is for kernel interaction.

# Misc
* `/var` is used for holding persistent data. "Variable".
	* `/var/log` holds logs
	* `/var/lib` contains persistent state data, e.g. database tables or container volumes
	* `/var/cache` contains cached data, e.g. package manage might cache data here
