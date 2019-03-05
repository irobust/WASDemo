# Reconnaissance

## Search engine
theharvester -b all -d sanook.com
search ip:111.111.111.111 with Bing.com

## AXFR
dig acisonline.net -t ANY (A, AAA, CNAME, MX, NS, TXT, AXFR)

dig acisonline.net -t NS

dig @NS...... acisonline.net -t AXFR

## Scan AXFR
dnsrecon -d acisonline.net -a

## Brute Forcing
dnsenum -f /usr/share/dnsenum/dns.txt sanook.com
dnsenum -f /usr/share/wordlists/dnsmap.txt sanook.com

fierce -dns sanook.com -wordlist /usr/share/dnsenum/dns.txt
