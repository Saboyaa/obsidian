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
less
```shell-session
 less /etc/passwd
```
head/tail
```shell-session
tail /etc/passwd
```
sort
```shell-session
cat /etc/passwd | sort
```
grep
```shell-session
cat /etc/passwd | grep "/bin/bash"
```
cut 
```shell-session
cat /etc/passwd | grep -v "false\|nologin" | cut -d":" -f1
```
tr
```shell-session
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " "
```
wc
```shell-session
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " " | awk '{print $1, $NF}' | wc -l
```
