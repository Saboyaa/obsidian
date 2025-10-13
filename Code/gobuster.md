Gobuster is a versatile tool that can be used for various types of brute-forcing, including virtual host discovery. Its `vhost` mode is designed to enumerate virtual hosts by sending requests to the target IP address with different hostnames. If a virtual host is configured for a specific hostname, Gobuster will receive a response from the web server.

To use Gobuster to brute-force virtual hosts, you'll need a wordlist containing potential hostnames. Here's an example command:

Code: bash

```bash
gobuster vhost -u http://192.0.2.1 -w hostnames.txt
```

```bash
gobuster vhost -u http://inlanefreight.htb:81 -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-110000.txt --append-domain
```
