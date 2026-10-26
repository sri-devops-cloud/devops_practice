website_connectivity.md
# Website Connectivity Investigation

## Objective

To investigate website reachability, verify DNS resolution, and test HTTPS connectivity using Windows command-line tools.

## Tools Used

- Windows PowerShell
- Ping
- Nslookup
- cURL

## Task 1: Check Website Reachability

### Command

```powershell
ping google.com
```

### Purpose

The `ping` command sends ICMP echo requests to a destination to check whether it responds over the network.

### Procedure

1. Open PowerShell.
2. Run `ping google.com`.
3. Observe the replies, packet loss, and response times.

### Expected Result

If ICMP requests are permitted and the destination responds, you may see replies containing the destination IP address and response time.

**Note:** A failed ping does not always mean the website is down. Some networks or servers block ICMP traffic.

## Task 2: Verify DNS Resolution

### Command

```powershell
nslookup google.com
```

### Purpose

DNS (Domain Name System) translates domain names, such as `google.com`, into IP addresses that computers can use to connect to servers.

### Procedure

1. Run `nslookup google.com` in PowerShell.
2. Check which DNS server is used.
3. Look for the resolved IP addresses.

### Expected Result

The output may contain IPv4 addresses, IPv6 addresses, or both.

If the DNS request times out, investigate whether the configured DNS server is responding.

## Task 3: Verify HTTPS Response Headers

### Command

```powershell
curl.exe -I https://google.com
```

### Purpose

The `-I` option requests HTTP response headers without downloading the full response body. The request uses HTTPS.

### Procedure

1. Run the command in PowerShell.
2. Observe the HTTP status and response headers.
3. Check for a redirect or another HTTP response.

### Expected Result

Google may return `301 Moved Permanently` with a `Location` header pointing to `https://www.google.com/`.

A 301 response is a normal redirect and indicates that an HTTP response was received.

## Task 4: Detailed HTTPS Connectivity Test

### Command

```powershell
curl.exe -v --max-time 10 https://google.com
```

### Purpose

The `-v` option displays detailed connection information, including connection attempts, TLS negotiation details, HTTP request headers, and response headers. The timeout limits the request to 10 seconds.

### Procedure

1. Run the command in PowerShell.
2. Check whether the connection is established.
3. Observe the HTTPS/TLS details and HTTP status.
4. Review any error messages if the connection fails.

### Expected Result

A successful connection may show `Connected to google.com`, TLS-related information, and an HTTP response such as `301 Moved Permanently`.

## Conclusion

These tests help investigate network reachability, DNS resolution, and HTTPS connectivity. Interpret each result separately because a failed ping does not necessarily mean that DNS or HTTPS is unavailable.