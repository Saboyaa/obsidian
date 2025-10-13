Once the DNS directs traffic to the correct server, the web server configuration becomes crucial in determining how the incoming requests are handled. Web servers like Apache, Nginx, or IIS are designed to host multiple websites or applications on a single server. They achieve this through virtual hosting, which allows them to differentiate between domains, subdomains, or even separate websites with distinct content.
![[ig_virtualhosts_1.png]]
### How to exploit
Websites often have subdomains that are not public and won't appear in DNS records. These `subdomains` are only accessible internally or through specific configurations. `VHost fuzzing` is a technique to discover public and non-public `subdomains` and `VHosts` by testing various hostnames against a known IP address.
Using [[gobuster]] or [[ffuf]] we can do the fuzzing, example:
```shell-session
gobuster vhost -u http://<target_IP_address> -w <wordlist_file> --append-domain
```
OBS: you can change the host on the `/etc/host`
``` 
127.0.0.1 localhost
::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters

ip vhost
```
