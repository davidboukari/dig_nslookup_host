# dig_nslookup_host

```
ping -c 1   www.dailymotion.fr
PING www.dailymotion.fr (195.8.215.136): 56 data bytes
```

## host
```
host 195.8.215.136
136.215.8.195.in-addr.arpa domain name pointer www.dailymotion.com.
```

## dig 
```
#
dig mx www.google.fr

dig txt www.google.fr



#Use a specific dns server @server
dig @ns200.anycast.me  lapetiteboutiquefrancaise.fr

dig www.dailymotion.fr
...

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;www.dailymotion.fr.		IN	A

;; ANSWER SECTION:
www.dailymotion.fr.	1940	IN	A	195.8.215.136

;; AUTHORITY SECTION:
dailymotion.fr.		172641	IN	NS	a.dailymotion.com.
dailymotion.fr.		172641	IN	NS	b.dailymotion.com.

;; ADDITIONAL SECTION:
a.dailymotion.com.	139177	IN	A	195.8.214.1
b.dailymotion.com.	139177	IN	A	195.8.214.2
```

# reverse dns
```
dig -x 195.8.215.136

; <<>> DiG 9.10.6 <<>> -x 195.8.215.136
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 23101
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 2, ADDITIONAL: 3

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;136.215.8.195.in-addr.arpa.	IN	PTR

;; ANSWER SECTION:
136.215.8.195.in-addr.arpa. 86123 IN	PTR	www.dailymotion.com.

;; AUTHORITY SECTION:
215.8.195.in-addr.arpa.	94425	IN	NS	b.dailymotion.com.
215.8.195.in-addr.arpa.	94425	IN	NS	a.dailymotion.com.

;; ADDITIONAL SECTION:
a.dailymotion.com.	139046	IN	A	195.8.214.1
b.dailymotion.com.	139046	IN	A	195.8.214.2

;; Query time: 45 msec
;; SERVER: 10.44.0.3#53(10.44.0.3)
;; WHEN: Fri Sep 03 07:07:12 CEST 2021
;; MSG SIZE  rcvd: 152
...
```

## nslookup
* https://geek-university.com/linux/nslookup-command/

```
nslookup www.dailymotion.fr
Server:		10.44.0.3
Address:	10.44.0.3#53

Non-authoritative answer:
Name:	www.dailymotion.fr
Address: 195.8.215.136
```

```
slookup 195.8.215.136
Server:		10.44.0.3
Address:	10.44.0.3#53

Non-authoritative answer:
136.215.8.195.in-addr.arpa	name = www.dailymotion.com.

Authoritative answers can be found from:
215.8.195.in-addr.arpa	nameserver = a.dailymotion.com.
215.8.195.in-addr.arpa	nameserver = b.dailymotion.com.
a.dailymotion.com	internet address = 195.8.214.1
b.dailymotion.com	internet address = 195.8.214.2
```









