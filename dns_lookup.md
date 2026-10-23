# Task 6: DNS Lookup

## Objective
To find the IP address of a website using DNS tools and compare results from different DNS servers.

## Commands Used
1. nslookup google.com
2. nslookup google.com 8.8.8.8
3. nslookup google.com 1.1.1.1

## Results
- Default DNS Server: 10.221.99.74
- Default DNS IPv4: 142.251.221.206
- Default DNS IPv6: 2404:6800:4007:80f::200e
- Google DNS (8.8.8.8): Request timed out; no IP address returned.
- Cloudflare DNS (1.1.1.1): 142.251.43.142

## Comparison
The default DNS server successfully returned IPv4 and IPv6 addresses. Google DNS timed out, while Cloudflare DNS returned an IPv4 address after a timeout message.

## Conclusion
The nslookup command was used to resolve google.com and compare responses from the default DNS server, Google DNS, and Cloudflare DNS. The results show that DNS server responses and availability can differ.
