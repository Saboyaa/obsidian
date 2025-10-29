System logs on [[Linux]] are a set of files that contain information about the system and the activities taking place on it. These logs are important for monitoring and troubleshooting the system, as they can provide insights into system behavior, application activity, and [[Linux Security]] events.

- [[#Kernel Logs]]
- [[#System Logs]]
- [[#Authentication Logs]]
- [[#Application Logs]]
- [[#Security Logs]]

## Kernel Logs
These logs contain information about the system's kernel, including hardware drivers, system calls, and kernel events. They are stored in the `/var/log/kern.log`
Kernel logs can reveal the presence of vulnerable or outdated drivers that could be targeted by attackers to gain access to the system.
## System Logs
These logs contain information about system-level events, such as service starts and stops, login attempts, and system reboots. They are stored in the `/var/log/syslog`
By analyzing login attempts, service starts and stops, and other system-level events, we can detect any possible access or activities on the system.
## Authentication logs

These logs contain information about user authentication attempts, including successful and failed attempts. They are stored in the `/var/log/auth.log` file
Therefore, it is essential for penetration testers to review the logs stored in the `/var/log/auth.log` file to ensure that the system is secure and has not been compromised.
## Application logs

These logs contain information about the activities of specific applications running on the system. They are often stored in their own files, such as `/var/log/apache2/error.log`
These logs are particularly important when we are targeting specific applications, such as web servers or [[Databases]], as they can provide insights into how these applications are processing and handling data.
## Security logs

These security logs and their events are often recorded in a variety of log files, depending on the specific security application or tool in use.
As penetration testers, we can use log analysis tools and techniques to search for specific events or patterns of activity that may indicate a security issue and use that information to further test the system for vulnerabilities or potential attack vectors.