
<!-- TOC -->

- [Whois domain lookup?](#whois-domain-lookup)
    - [Answer the questions below](#answer-the-questions-below)
        - [When was TryHackMe.com registered?](#when-was-tryhackmecom-registered)

<!-- /TOC -->
## Whois domain lookup?

- A Whois domain lookup is a tool used to query databases that store information about registered domain names. When someone registers a domain name (e.g., example.com), they must provide contact information such as their name, address, email address, and phone number. This information is stored in a Whois database and is publicly accessible.

- A Whois domain lookup allows users to retrieve this registration information for a given domain name. It can be useful for various purposes, such as identifying the owner of a domain, checking the availability of a domain, or investigating potential cases of domain abuse or infringement.

- However, due to privacy concerns, some domain registrars offer a service called Whois privacy protection or domain privacy, which replaces the registrant's contact information with that of a proxy service, shielding the registrant's personal details from public view in the Whois database.


To get this information, we need to use a `whois` client or an online service. Many online services provide `whois `information; however, it is generally faster and more convenient to use your local whois client. Using the AttackBox (or your local Linux machine, such as Parrot or Kali), you can easily access your whois client on the terminal. The syntax is `whois DOMAIN_NAME`, where DOMAIN_NAME is the domain about which you are trying to get more information. Consider the following example executing `whois tryhackme.com.`


```base

╭─abhishekg@abhishek in repo: CEH/04_Day_Information Gathering on  master [!?] took 2s
╰─λ whois tryhackme.com


Domain Name: TRYHACKME.COM
Registry Domain ID: 2282723194_DOMAIN_COM-VRSN
Registrar WHOIS Server: whois.namecheap.com
Registrar URL: http://www.namecheap.com
Updated Date: 2021-05-01T19:43:23Z
Creation Date: 2018-07-05T19:46:15Z
Registry Expiry Date: 2027-07-05T19:46:15Z
Registrar: NameCheap, Inc.
Registrar IANA ID: 1068
Registrar Abuse Contact Email: abuse@namecheap.com
Registrar Abuse Contact Phone: +1.6613102107


Domain Status: clientTransferProhibited https://icann.org/epp#clientTransferProhibited
Name Server: KIP.NS.CLOUDFLARE.COM
Name Server: UMA.NS.CLOUDFLARE.COM
DNSSEC: unsigned
URL of the ICANN Whois Inaccuracy Complaint Form: https://www.icann.org/wicf/
>>> Last update of whois database: 2024-05-19T04:40:40Z <<< For more information on Whois status codes, please visit https://icann.org/epp

NOTICE: The expiration date displayed in this record is the date the registrar's sponsorship of the domain name registration in the registry is currently set to expire.

 This date does not necessarily reflect the expiration
date of the domain name registrant's agreement with the sponsoring registrar. 

 Users may consult the sponsoring registrar's Whois database to view the registrar's reported date of expiration for this registration.

TERMS OF USE: You are not authorized to access or query our Whois database through the use of electronic processes that are high-volume and automated except as reasonably necessary to register domain names or modify existing registrations; the Data in VeriSign Global Registry Services' ("VeriSign") Whois database is provided by VeriSign for
information purposes only, and to assist persons in obtaining information about or related to a domain name registration record. VeriSign does not
guarantee its accuracy.


 By submitting a Whois query, you agree to abide
by the following terms of use: You agree that you may use this Data only for lawful purposes and that under no circumstances will you use this Data
to: (1) allow, enable, or otherwise support the transmission of mass
unsolicited, commercial advertising or solicitations via e-mail, telephone,
or facsimile; or (2) enable high volume, automated, electronic processes
that apply to VeriSign (or its computer systems). The compilation,
repackaging, dissemination or other use of this Data is expressly
prohibited without the prior written consent of VeriSign. You agree not to
use electronic processes that are automated and high-volume to access or
query the Whois database except as reasonably necessary to register
domain names or modify existing registrations. VeriSign reserves the right
to restrict your access to the Whois database in its sole discretion to ensure
operational stability.  VeriSign may restrict or terminate your access to the
Whois database for failure to abide by these terms of use. VeriSign
reserves the right to modify these terms at any time.



The Registry database contains ONLY .COM, .NET, .EDU domains and
Registrars.
Domain name: tryhackme.com
Registry Domain ID: 2282723194_DOMAIN_COM-VRSN
Registrar WHOIS Server: whois.namecheap.com
Registrar URL: http://www.namecheap.com
Updated Date: 2021-05-01T19:43:23.31Z
Creation Date: 2018-07-05T19:46:15.00Z
Registrar Registration Expiration Date: 2027-07-05T19:46:15.00Z


Registrar: NAMECHEAP INC
Registrar IANA ID: 1068
Registrar Abuse Contact Email: abuse@namecheap.com
Registrar Abuse Contact Phone: +1.9854014545
Reseller: NAMECHEAP INC
Domain Status: clientTransferProhibited https://icann.org/epp#clientTransferProhibited
Registry Registrant ID:
Registrant Name: Redacted for Privacy
Registrant Organization: Privacy service provided by Withheld for Privacy ehf
Registrant Street: Kalkofnsvegur 2
Registrant City: Reykjavik
Registrant State/Province: Capital Region
Registrant Postal Code: 101


Registrant Country: IS
Registrant Phone: +354.4212434
Registrant Phone Ext:
Registrant Fax:
Registrant Fax Ext:
Registrant Email: a70a4ff6d25041a48378997194f9e834.protect@withheldforprivacy.com
Registry Admin ID:
Admin Name: Redacted for Privacy
Admin Organization: Privacy service provided by Withheld for Privacy ehf
Admin Street: Kalkofnsvegur 2
Admin City: Reykjavik


Admin State/Province: Capital Region
Admin Postal Code: 101
Admin Country: IS
Admin Phone: +354.4212434
Admin Phone Ext:
Admin Fax:
Admin Fax Ext:
Admin Email: a70a4ff6d25041a48378997194f9e834.

protect@withheldforprivacy.com
Registry Tech ID:
Tech Name: Redacted for Privacy
Tech Organization: Privacy service provided by Withheld for Privacy ehf
Tech Street: Kalkofnsvegur 2
Tech City: Reykjavik
Tech State/Province: Capital Region
Tech Postal Code: 101


Tech Country: IS
Tech Phone: +354.4212434
Tech Phone Ext:
Tech Fax:
Tech Fax Ext:
Tech Email: a70a4ff6d25041a48378997194f9e834.protect@withheldforprivacy.com
Name Server: kip.ns.cloudflare.com
Name Server: uma.ns.cloudflare.com
DNSSEC: unsigned


URL of the ICANN WHOIS Data Problem Reporting System: http://wdprs.internic.net/
>>> Last update of WHOIS database: 2024-05-18T19:23:07.15Z <<<
For more information on Whois status codes, please visit https://icann.org/epp


````

We can see plenty of information; we will inspect them in the order displayed. First, we notice that we were redirected to `whois.namecheap.com` to get our information. In this case and at the time being, `namecheap.com` is maintaining the WHOIS record for this domain name. Furthermore, we can see the creation date along with the last-update date and expiration date.

Next, we obtain information about the registrar and the registrant. We can find the registrant’s name and contact information unless they are using some privacy service. Although not displayed above, we get the admin and tech contacts for this domain. Finally, we see the domain name servers that we should query if we have any DNS records to look up.

The information collected can be inspected to find new attack surfaces, such as social engineering or technical attacks. For instance, depending on the scope of the penetration test, you might consider an attack against the email server of the admin user or the DNS servers, assuming they are owned by your client and fall within the scope of the penetration test.

It is important to note that due to automated tools abusing WHOIS queries to harvest email addresses, many WHOIS services take measures against this. They might redact email addresses, for instance. Moreover, many registrants subscribe to privacy services to avoid their email addresses being harvested by spammers and keep their information private.

On the AttackBox, open the terminal and run the whois tryhackme.com command to get the information you need to answer the following questions.


### Answer the questions below

#### 1. When was TryHackMe.com registered?

`Question Hint`


Use the format YYYYMMDD
````
Creation Date: 2018-07-05T19:46:15Z
````


`Answer`
````
20180705

```


#### 2. What is the registrar of TryHackMe.com?

`Question Hint`

Give its domain name


`Answer`
```
namecheap.com
```


#### 3. Which company is TryHackMe.com using for name servers?


`Question Hint`

 Give its domain name


```plaintext
Name Server: kip.ns.cloudflare.com
Name Server: uma.ns.cloudflare.com
```

`Answer`
```
Cloudflare.com 
```


 