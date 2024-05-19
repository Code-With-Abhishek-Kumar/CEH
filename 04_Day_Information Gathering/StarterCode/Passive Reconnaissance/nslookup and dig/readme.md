

## Nslookup 

- Nslookup (stands for “Name Server Lookup”) is a useful command for getting information from the DNS server. It is a network administration tool for querying the Domain Name System (DNS) to obtain domain name or IP address mapping or any other specific DNS record. It is also used to troubleshoot DNS-related problems.




- Find the IP address of a domain name using `nslookup`, which stands for Name Server Look Up. You need to issue the command `nslookup DOMAIN_NAME`, for example, `nslookup tryhackme.com`. Or, more generally, you can use `nslookup OPTIONS DOMAIN_NAME SERVER`. These three main parameters are:

- OPTIONS contains the query type as shown in the table below. For instance, you can use `A` for IPv4 addresses and `AAAA` for IPv6 addresses.

- DOMAIN_NAME is the domain name you are looking up.

- SERVER is the DNS server that you want to query. 

- You can choose any local or public DNS server to query. Cloudflare offers `1.1.1.1` and `1.0.0.1`, Google offers 8.8.8.8 and 8.8.4.4, and Quad9 offers `9.9.9.9` and `149.112.112.112`. 

- There are many more public DNS servers that you can choose from if you want alternatives to your ISP’s DNS servers.



![Image Description](/Image/Screenshot_20240519_114708.png)

- For instance, `nslookup -type=A tryhackme.com 1.1.1.1 `(or `nslookup -type=a tryhackme.com 1.1.1.1 ` as it is case-insensitive) can be used to return all the IPv4 addresses used by tryhackme.com.

```bash

user@TryHackMe$ nslookup -type=A tryhackme.com 1.1.1.1
Server:		1.1.1.1
Address:	1.1.1.1#53

Non-authoritative answer:
Name:	tryhackme.com
Address: 172.67.69.208
Name:	tryhackme.com
Address: 104.26.11.229
Name:	tryhackme.com
Address: 104.26.10.229


```

- The `A` and `AAAA` records are used to return IPv4 and IPv6 addresses, respectively. This lookup is helpful to know from a penetration testing perspective. In the example above, we started with one domain name, and we obtained three IPv4 addresses. Each of these IP addresses can be further checked for insecurities, assuming they lie within the scope of the penetration test.

- Let’s say you want to learn about the email servers and configurations for a particular domain. You can issue `nslookup -type=MX tryhackme.com`. Here is an example:

````bash

user@TryHackMe$ nslookup -type=MX tryhackme.com
Server:		127.0.0.53
Address:	127.0.0.53#53

Non-authoritative answer:
tryhackme.com	mail exchanger = 5 alt1.aspmx.l.google.com.
tryhackme.com	mail exchanger = 1 aspmx.l.google.com.
tryhackme.com	mail exchanger = 10 alt4.aspmx.l.google.com.
tryhackme.com	mail exchanger = 10 alt3.aspmx.l.google.com.
tryhackme.com	mail exchanger = 5 alt2.aspmx.l.google.com.


````

- Such pieces of information might prove valuable as you continue the passive reconnaissance of your target. You can repeat similar queries for other domain names and try different types, such as `-type=txt`. Who knows what kind of information you might discover along your way!

- For more advanced DNS queries and additional functionality, you can use `dig`, the acronym `for “Domain Information Groper`,” if you are curious. 

- Let’s use `dig` to look up the `MX records` and compare them to `nslookup`. We can use `dig DOMAIN_NAME`, but to specify the record type, we would use `dig DOMAIN_NAME` TYPE. Optionally, we can select the server we want to query using dig @SERVER DOMAIN_NAME TYPE.

- SERVER is the DNS server that you want to query.

- DOMAIN_NAME is the domain name you are looking up.

- TYPE contains the DNS record type, as shown in the table provided earlier.

````bash

user@TryHackMe$ dig tryhackme.com MX

; <<>> DiG 9.16.19-RH <<>> tryhackme.com MX
;; global options: +cmd
;; Got answer:
;; ->>HEADER<
        

````

- A quick comparison between the output of `nslookup and dig` shows that dig returned more information, such as the TTL (Time To Live) by default.

-  If you want to query a `1.1.1.1` DNS server, you can execute `dig @1.1.1.1 tryhackme.com MX`.


### Answer the questions below

#### Check the TXT records of thmlabs.com. What is the flag there?


`Answer`

```
THM{a5b83929888ed36acb0272971e438d78}

```



## How to find Answer

`````base

╭─abhishekg@abhishek in ~ via  v22.0.0 took 191ms
╰─λ nslookup -type=TXT thmlabs.com 1.1.1.1
Server:         1.1.1.1
Address:        1.1.1.1#53

Non-authoritative answer:
thmlabs.com     text = "THM{a5b83929888ed36acb0272971e438d78}"

Authoritative answers can be found from:

`````

also Use 

`````

╭─abhishekg@abhishek in ~ via  v22.0.0 took 223ms
╰─λ dig  thmlabs.com  TXT

; <<>> DiG 9.18.27 <<>> thmlabs.com TXT
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 15472
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;thmlabs.com.                   IN      TXT

;; ANSWER SECTION:
thmlabs.com.            300     IN      TXT     "THM{a5b83929888ed36acb0272971e438d78}"

;; Query time: 314 msec
;; SERVER: 192.168.0.1#53(192.168.0.1) (UDP)
;; WHEN: Sun May 19 12:05:39 IST 2024
;; MSG SIZE  rcvd: 90


`````