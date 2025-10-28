Managing file systems on Linux is a crucial task that involves organizing, storing, and maintaining data on a disk or other storage device. 

- `ext2` is an older file system with no journaling capabilities, which makes it less suited for modern systems but still useful in certain low-overhead scenarios (like USB drives).
- `ext3` and `ext4` are more advanced, with journaling (which helps in recovering from crashes), and ext4 is the default choice for most modern Linux systems because it offers a balance of performance, reliability, and large file support. ( the one I use on my Arch System )
- `Btrfs` is known for advanced features like snapshotting and built-in data integrity checks, making it ideal for complex storage setups.
- `XFS` excels at handling large files and has high performance. It is best suited for environments with high I/O demands
- `NTFS`, originally developed for Windows, is useful for compatibility when dealing with [[dual-boot]] systems or external drives that need to work on both [[Linux]] and [[Windows]] systems.
## Kinds of storage
### Regular Files

Regular files are the most common type and typically consist of text data (such as ASCII) and/or binary data (such as images, audio, or executables). They reside in various directories throughout the file system, not just in the root directory. 
### Directories

Directories are special types of files that act as containers for other files (both regular files and other directories). When a file is stored in a directory, that directory is referred to as the file’s parent directory. Directories help organize files within the Linux file system, allowing for an efficient way to manage collections of files.

### Symbolic Links

In addition to regular files and directories, Linux also supports symbolic links (`symlinks`), which act as shortcuts or references to other files or directories. Symbolic links allow quick access to files located in different parts of the file system without duplicating the file itself. Symlinks can be used to streamline access or organize complex directory structures by pointing to important files across various locations.
## Disks & Drives
Disk management on Linux involves managing physical storage devices, including hard drives, solid-state drives, and removable storage devices.
The most common partitioning tool on Linux is also `fdisk`, `gpart`, and `GParted`.
### Fdisk ( the main partitioning tool )

```shell-session
sudo fdisk -l
```

## Mounting

Each logical partition or storage drive must be assigned to a specific directory in the file system. This process is known as `mounting`. 
Mounting involves linking a drive or partition to a directory, making its contents accessible within the overall file system hierarchy. Once a drive is mounted to a directory (also called a mount point), it can be accessed and used like any other directory on the system.

```shell-session
sudo mount /dev/sdb1 /mnt/usb
```

## SWAP

Swap space is an essential part of memory management in Linux and plays a critical role in ensuring smooth system performance, especially when the available physical memory (RAM) is fully utilized.
When the system runs out of physical memory, the kernel moves inactive pages of memory (data not immediately in use) to the swap space, freeing up [[RAM]] for active processes. This process is known as swapping.

- `mkswap` is used to prepare a device or file to be used as swap space by creating a Linux swap area
- `swapon` activates the swap space, allowing the system to use it
## Containerization
Containerization is the process of packaging and running applications in isolated environments
Technologies like [[Docker]], Docker Compose, and [[Linux Containers (LXC)]] make containerization possible, primarily in Linux-based systems. Containers differ from [[virtual machines]] in that they share the host system's kernel, making them far more lightweight and efficient.
### Security Warning
Docker containers are generally more secure out of the box, thanks to additional isolation layers like AppArmor and SELinux, along with its read-only filesystem feature. LXC containers, while secure, may need additional configurations to match the level of isolation Docker offers by default. Interestingly enough, when misconfigured, both Docker and LXC can present a vector for [[Privilege Escalation]]