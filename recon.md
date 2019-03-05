// Search engine
theharvester -b all -d sanook.com

// AXFR
dig acisonline.net -t ANY (A, AAA, CNAME, MX, NS, TXT, AXFR)

dig acisonline.net -t NS

dig @NS...... acisonline.net -t AXFR

// Scan AXFR
dnsrecon -d acisonline.net -a

// Brute Force
dnsenum -f /usr/share/dnsenum/dns.txt sanook.com
dnsenum -f /usr/share/wordlists/dnsmap.txt sanook.com

fierce -dns sanook.com -wordlist /usr/share/dnsenum/dns.txt
