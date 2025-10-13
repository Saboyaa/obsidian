Subdomain brute-forcing is a proactive technique used in web reconnaissance to uncover subdomains that may not be readily apparent through passive methods. It involves systematically generating many potential subdomain names and testing them against the target's DNS server to see if they exist. This approach can unveil hidden subdomains that may host valuable information, development servers, or vulnerable applications.

One of the most versatile tools for subdomain brute-forcing is `dnsenum`. This powerful command-line tool combines various DNS enumeration techniques, including dictionary-based brute-forcing, to uncover subdomains associated with your target.

To use `dnsenum` for subdomain brute-forcing, you'll typically provide it with the target domain and a wordlist containing potential subdomain names. The tool will then systematically query the DNS server for each potential subdomain and report any that exist.

```bash
dnsenum example.com -f subdomains.txt
```
this txt can be a [[SecList]] wordlist 