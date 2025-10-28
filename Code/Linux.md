Made by the great Linus Torvalds, the most popular distros are [[Ubuntu]],  [[RedHat]], [[Kali]] and [[Arch]] 
## Philosophy
### Everything is a file 
All configuration files for the various services running on the Linux operating system are stored in one or more text files.
### Small, single-purpose programs
Linux offers many different tools that we will work with, which can be combined to work together.
### Ability to chain programs together to perform complex tasks 
The integration and combination of different tools enable us to carry out many large and complex tasks, such as processing or filtering specific data results.
### Avoid captive user interfaces
Linux is designed to work mainly with the shell (or terminal), which gives the user greater control over the operating system. 
### Configuration data stored in a text file
An example of such a file is the /etc/passwd file, which stores all users registered on the system.
## Components
### [[Bootloader]]
A piece of code that runs to guide the booting process to start the operating system. Parrot Linux uses the [[GRUB]] Bootloader.
### [[Kernel|OS Kernel]] 
The kernel is the main component of an operating system. It manages the resources for system's I/O devices at the hardware level.
### [[Daemons]] 	
Background services are called "daemons" in Linux. Their purpose is to ensure that key functions such as scheduling, printing, and multimedia are working correctly. These small programs load after we booted or log into the computer.
### [[Shell|OS Shell]] 	
The operating system shell or the command language interpreter (also known as the command line) is the interface between the OS and the user. This interface allows the user to tell the OS what to do. The most commonly used shells are Bash, Tcsh/Csh, Ksh, Zsh, and Fish.
### [[Graphics server]]
This provides a graphical sub-system (server) called "X" or "X-server" that allows graphical programs to run locally or remotely on the X-windowing system.
### [[Window Manager]]
Also known as a graphical user interface (GUI). There are many options, including [[GNOME]], [[Hyprland]]. A desktop environment usually has several applications, including file and web browsers. These allow the user to access and manage the essential and frequently accessed features and services of an operating system.
## Architecture
### [[Hardware]] 
Peripheral devices such as the system's RAM, hard drive, CPU, and others.
### [[Kernel]]
The core of the Linux operating system whose function is to virtualize and control common computer hardware resources like [[CPU]], allocated memory, accessed data, and others. The kernel gives each process its own virtual resources and prevents/mitigates conflicts between different processes.
### [[Shell]]
A command-line interface (CLI), also known as a shell that a user can enter commands into to execute the kernel's functions.
## Backup and Restore 
- `Rsync` - Fast and secure backups locally or remote
- `Deja Dup` - a simple backup, more user-friendly
- `Duplicity` - Same as Rsync but encrypted

### Rsync Usage

```shell-session
rsync -av /path/to/mydirectory user@backup_server:/path/to/backup/directory
```

This command will copy the entire directory (`/path/to/mydirectory`) to a remote host (`backup_server`), to the directory `/path/to/backup/directory`. The option `archive` (`-a`) is used to preserve the original file attributes, such as permissions, timestamps, etc., and using the `verbose` (`-v`) option provides a detailed output of the progress of the `rsync` operation.

## [[Linux File System Management]]
Managing file systems on Linux is a crucial task that involves organizing, storing, and maintaining data on a disk or other storage device. 