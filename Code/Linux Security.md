[[Linux]] systems are also less prone to viruses that affect [[Windows]] operating systems and do not present as large an attack surface as [[Active Directory]] domain-joined hosts. Regardless, it is essential to have certain fundamentals in place to secure any Linux system.
## Hints

- If a user needs to run a command as root, then that command should be specified in the `sudoers` configuration instead of giving them full sudo rights.
- common protection mechanism that can be used is `fail2ban`. This tool counts the number of failed login attempts, and if a user has reached the maximum number, the host that tried to connect will be handled as configured.
- There are different applications and services such as [Snort](https://www.snort.org/), [chkrootkit](http://www.chkrootkit.org/), [rkhunter](https://packages.debian.org/sid/rkhunter), [Lynis](https://cisofy.com/lynis/), and others that can contribute to Linux's security.

### Settings to see 

- Removing or disabling all unnecessary services and software
- Removing all services that rely on unencrypted authentication mechanisms
- Ensure NTP is enabled and Syslog is running
- Ensure that each user has its own account
- Enforce the use of strong passwords
- Set up password aging and restrict the use of previous passwords
- Locking user accounts after login failures
- Disable all unwanted SUID/SGID binaries
