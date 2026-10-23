# Network Connectivity Testing

## 1. Ping Google's DNS Server
Command: ping 8.8.8.8 -n 20

Results:
- Packets sent: 20
- Packets received: 20
- Packet loss: 0%
- Minimum response time: 25 ms
- Maximum response time: 46 ms
- Average response time: 34 ms

## 2. Test Local Network Connectivity
Command: ping 192.168.56.1

Results:
- Packets received: 4 out of 4
- Packet loss: 0%

Note: 192.168.56.1 may be a VirtualBox host-only adapter rather than the physical router.

## 3. Compare Response Times
The local adapter responded in approximately 0 ms when rounded, while Google's DNS server had an average response time of 34 ms during the 20-packet test.

## Conclusion
Network connectivity testing was completed successfully. The Google DNS test showed 0% packet loss and an average response time of 34 ms.
