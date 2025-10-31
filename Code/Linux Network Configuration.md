A solid understanding of [[Linux]] [[Network]] configuration gives us the ability to tailor our testing approach to suit specific needs, helping optimize both our testing procedures and results.

## Network Access Control 
Configuring Linux network devices for NAC involves setting up security policies like `SELinux` (Security-Enhanced Linux), `AppArmor` profiles for application security, and using `TCP wrappers` to control access to services based on IP addresses. More about this in the future sections.
Tools such as `syslog`, `rsyslog`, `ss` (for socket statistics), `lsof` (to list open files), and the [[ELK stack]]
### Types of Network Access

- Discretionary Access Control (`DAC`) This model allows the owner of the resource to set permissions for who can access it.
- Mandatory Access Control (`MAC`) Permissions are enforced by the operating system, not the owner of the resource, making it more secure but less flexible.
- Role-Based Access Control (`RBAC`) Permissions are assigned based on roles within an organization, making it easier to manage user privileges.

## Configuring Network Interfaces
When working with Ubuntu, you can configure local network interfaces using the `ifconfig` or the `ip` command.
#### activate a interface

```shell-session
sudo ifconfig eth0 up
```
or
```shell-session
sudo ip link set eth0 up
```
#### Assign IP Address 

```shell-session
sudo ifconfig eth0 192.168.1.2
```
#### Assign a Netmask

```shell-session
sudo ifconfig eth0 netmask 255.255.255.0
```
#### Assign the Route to an interface

```shell-session
sudo route add default gw 192.168.1.1 eth0
```

When configuring a network interface in Linux, it is often necessary to set Domain Name System (`DNS`) servers to ensure proper network functionality. DNS servers are responsible for translating domain names (like example.com) into [[Network Protocols|IP]] addresses, which allows devices to locate and connect to one another on the internet.
## Troubleshooting
Network troubleshooting is an essential process that involves diagnosing and resolving network issues that can adversely affect the performance and reliability of the network. 
- Ping
-  Traceroute
-  Netstat
-  Tcpdump
-  [[Wireshark]]
-  [[nmap]]
## Hardening
#### Security-Enhanced Linux

Security-Enhanced Linux (`SELinux`) is a mandatory access control (`MAC`) system integrated into the Linux kernel. It provides fine-grained control over access to system resources and applications by enforcing security policies.
SELinux operates at a low level, and though it offers strong security, it can be complex to configure and manage due to its granular controls.
#### AppArmor
AppArmor is implemented as a Linux Security Module (`LSM`) and uses application profiles to define what resources an application can access. While it may not provide the same level of fine-grained control as SELinux, AppArmor is often easier to configure and is generally considered more straightforward for day-to-day use.
#### TCP Wrappers
`TCP wrappers` are a host-based network access control tool that restricts access to network services based on the IP address of incoming connections. When a network request is made, TCP wrappers intercept it, checking the request against a list of allowed or denied IP addresses.
## Remote Desktop
- `Remote Desktop Protocol` (`RDP`): Primarily used in Windows environments. RDP allows administrators to connect remotely and interact with the desktop of a Windows machine as if they were sitting right in front of it.
- `Virtual Network Computing` (`VNC`): A popular protocol in Linux environments, although it is also cross-platform. VNC provides graphical access to remote desktops, allowing administrators to perform tasks on Linux systems in a similar way to RDP on Windows.
### X11 Security

As we mentioned earlier, X11 is not a secure protocol by default because its communication is unencrypted. 
An attacker on the same network could read the contents of the `X server's` windows without the user's knowledge, making it unnecessary for them to even perform traditional network sniffing. This vulnerability allows for serious security breaches. An attacker could potentially intercept sensitive information, such as passwords or personal data, by simply using standard X11 tools like `xwd` (which captures screenshots of X windows) and `xgrabsc`.
#### Known Vulnerabilities
CVE-2017-2624, CVE-2017-2625, and CVE-2017-2626
[This](https://www.x41-dsec.de/lab/advisories/x41-2017-001-xorg/)article provides an excellent summary
### VNC

`Virtual Network Computing` (`VNC`) is a remote desktop sharing system based on the RFB protocol that allows users to control a computer remotely. It allows a user to view and interact with a desktop environment remotely over a network connection. The user can control the remote computer as if sitting in front of it. This is also one of the most common protocols for *remote graphical connections* for Linux hosts.
#### Tools for VNC

- [RealVNC](https://www.realvnc.com/en/)
- [UltraVNC](https://uvnc.com/)
