# Checking DNS Configuration
## `nslookup`

**Nslookup** (stands for “Name Server Lookup”) is a useful command for getting information from the DNS server. 

It is a network administration tool for querying the **Domain Name System** (DNS) to obtain domain name or IP address mapping or any other specific DNS record. 

It is also used to troubleshoot DNS-related problems.

To exit interactive mode, type: `exit`.

Syntax:

`nslookup [option] [hosts]`

Example: `nslookup softserveinc.com`

`-domain=[domain-name]` allows you to change the default DNS name:

`nslookup -domain=google.com`

`-port=[port-number]`: Use the **-port** option to specify the port number for queries. 
By **default**, nslookup uses **port 53** for DNS queries.

`nslookup -port=53 google.com`

### Lookup for any record
We can also view all the available DNS records using the `-type=any` option.

`nslookup -type=any google.com`

### Lookup for an `ns` record
**NS (Name Server)** record maps a domain name to a list of DNS servers authoritative for that domain. 

It will output the name serves which are associated with the given domain.

`nslookup -type=ns google.com`

### Lookup for an `mx` record
**MX (Mail Exchange)** maps a domain name to a list of mail exchange servers for that domain. 

The MX record says that all the mails sent to “google.com” should be routed to the Mail server in that domain.

`nslookup -type=mx google.com`

## `dig`
**DIG (Domain Information Groper command)** is a network tool with a basic command-line interface that serves for making different **DNS (domain name system)** queries. 

You can use the DIG command to: 
- Diagnose your name servers.
- Check all of them or each individual server and their response.

### Find the website’s IP address

`dig google.com`

Finds the IP address of a certain domain name, for example Google.

This `dig` command will give you a lot of extra information too:
- Data like the version of the **DIG** command you are using.
- A header that shows you what you did and who answered you.
- The port and protocol you used (usually UDP).
- The time it took for the query.
- The TTL of the record.
- The server which answered you and other.

If you don’t want so much information, go for the short answer with this command:

`dig google.com +short`

Find the name servers, responsible for your domain.

`dig NS google.com +short`

Which is the responsible mail server for your domain?

`dig MX google.com +short`

**Reverse DNS check, IP address to hostname** allows you to determine which IP address the domain name is associated with, for example:

`dig -x 142.250.186.46`

See when the cache with the answer will expire, for example:

`dig google.com +noall +answer`

## `host`
The `host` command in Linux is used for **DNS lookup operations**. 

This command is used to find the IP address of a specific domain name or if you want to know the domain name of a specific IP address. You can also find more specific information about a domain by specifying the appropriate option along with the domain name.

Syntax:

`host [-aCdlriTWV] [-c class] [-N ndots] [-t type] [-W time] [-R number] [-m flag] hostname [server]`

Print version number and exit:

`host -V`

Рrint the IP address details of the specified domain:

`host google.com`

Рrint the domain details record of the specified IP address:

`host 74.125.133.101`

Indicates the type of query or whether verbose output is enabled:

`host -a google.com`

`host -v google.com`

Show the type of query:

`host -t ns google.com`










