


## host 

- The `host` command is used to perform DNS (Domain Name System) lookups, which translates domain names to IP addresses. When you run the command host www.example.com, it queries the DNS server to find the IP address associated with the domain name "www.example.com". 

- it is used to find ip Address with the help of domain name

```bash
$ host www.example.com
```

`OutPut :- `

```bash
www.example.com has address 93.184.215.14
www.example.com has IPv6 address 2606:2800:21f:cb07:6820:80da:af6b:8b2c
```

## nslookup

`nslookup` is another command-line tool used for querying DNS (Domain Name System) servers to obtain domain name or IP address information. You can use it to perform various types of DNS queries, such as looking up the IP address associated with a domain name (forward lookup) or finding the domain name associated with an IP address (reverse lookup).

#### Here's an example of how you can use nslookup:

1. To find the IP address associated with a domain name:

```bash
$ nslookup www.google.com
```
```
Server:         192.168.0.1
Address:        192.168.0.1#53

Non-authoritative answer:
Name:   www.google.com
Address: 142.250.206.132
Name:   www.google.com
Address: 2404:6800:4002:82c::2004

```
`output`

2. To find the domain name associated with an IP address:

```bash
$ nslookup 93.184.216.34
```

```
132.206.250.142.in-addr.arpa    name = del11s21-in-f4.1e100.net.

Authoritative answers can be found from:
```

```bash
$ nslookup  del11s21-in-f4.1e100.net
```


## WhatWeb

 WhatWeb is an open-source web scanner that identifies websites by analyzing their HTML, JavaScript, CSS, and other aspects of their web presence. It's primarily used for reconnaissance and information gathering purposes in cybersecurity assessments.


```bash
$ whatweb www.example.com
```

#### Here are some websites where you can find details like IP addresses, domain information, DNS records, and more:

#### `Whois.net` 

- This website provides domain name registration information, including the domain owner's contact details, registration date, and expiration date.

####  `IPVoid`
    
- IPVoid offers various tools for analyzing IP addresses, including WHOIS lookup, IP geolocation, reverse DNS lookup, and blacklist check.

#### `MXToolbox` 
    
- MXToolbox provides a wide range of network diagnostic tools, including DNS lookup, WHOIS lookup, domain health monitoring, and email blacklist check.

#### `WhatIsMyIPAddress`

- This website offers tools for finding your IP address, as well as IP lookup, geolocation, and WHOIS lookup services.

#### `DomainTools`

-  DomainTools provides comprehensive domain name and DNS-related information, including WHOIS lookup, domain ownership history, DNS records, and domain monitoring services.

#### `DNSstuff`

-  DNSstuff offers a suite of DNS and network diagnostic tools, including DNS lookup, WHOIS lookup, IP geolocation, and email testing tools.

### `wappalyzer`

- Find out the technology stack of any website. Create lists of websites that use certain technologies, with company and contact details. Use our tools for lead generation, market analysis and competitor research.