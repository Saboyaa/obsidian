## System information
- `whoami` Displays current username.
- `id` Returns user’s identity.
- `hostname` Sets or prints the name of current host system.
- `uname` Prints basic information about the operating system name and system hardware.
- `pwd` Returns working directory name.
- `ip` Is a utility to show or manipulate routing, network devices, interfaces and tunnels.
- `netstat` Shows network status.
- `ss` Another utility to investigate sockets.
- `ps` Shows process status.
- `who` Displays who is logged in.
- `env` Prints environment or sets and executes command.
- `lsblk` Lists block devices.
- `lsusb` Lists [[USB]] devices.
- `lsof` Lists opened files.
- `lspci` Lists [[PCI]] devices.
## Tricks
`2>/dev/null` sends the errors to the void
`>` sends the output to an archive
`<` gets the input from the file to the command
`<<` add a standard input through a stream example:
```shell-session
cat << EOF > stream.txt
```
`|` redirect the output to another command example:
```shell-session
find /etc/ -name *.conf 2>/dev/null | grep systemd | wc -l
```
## Useful Commands
[[find]]
```shell-session
 find / -type f -name *.conf -user root -size +20k -newermt 2020-03-03 -exec ls -al {} \; 2>/dev/null
```

## User Management 
- `sudo`Execute command as a different user.
- `su` The `su` utility requests appropriate user credentials via PAM and switches to that user ID (the default user is the superuser). A shell is then executed.
- `useradd` Creates a new user or update default new user information.
- `userdel` Deletes a user account and related files.
- `usermod` Modifies a user account.
- `addgroup` Adds a group to the system.
- `delgroup` Removes a group from the system.
- `passwd` Changes user password.
