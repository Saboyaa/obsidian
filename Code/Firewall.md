The primary goal of firewalls is to provide a security mechanism for controlling and monitoring network traffic between different network segments, such as internal and external networks or different network zones.
# Linux Firewall
In [[Linux]], the firewall functionality is typically implemented using the Netfilter framework, which is an integral part of the kernel. Netfilter provides a set of hooks that can be used to intercept and modify [[Network]] traffic as it passes through the system. The iptables utility is commonly used to configure the firewall rules on Linux systems.
## Iptables
- `Tables` Used to organize and categorize firewall rules.
- `Chains` Used to group a set of firewall rules applied to a specific type of network traffic.
- `Rules` defines the criteria for filtering network traffic and the actions to take for packets that match the criteria.
- `Matches` Matches are used to match specific criteria for filtering network traffic, such as source or destination IP addresses, ports, [[Network Protocols]], and more.
- `Targets` Targets specify the action for packets that match a specific rule. For example, targets can be used to accept, drop, or reject packets or modify the packets in another way.

