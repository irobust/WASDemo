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

## Recon-ng
### recon-ng
| command | definition |
|---------|------------|
| show modules		  | แสดงรายการของ modules ที่มีทั้งหมด 		   	|
| use google_site_web | เลือก module ที่ต้องการใช้งาน 	  			|
| show info 		  | ดูว่าต้องการ parameter อะไรบ้าง 				|
| show domains 		  | แสดงรายการของ domain ทั้งหมดที่ต้องหารทดสอบ 	|
| show hosts 		  | แสดงรายการของ host ทั้งหมดใน domains 		|

### Modules
_______
* google_site_web
* bing_domain_web
* resolve `แปลงจาก domain ไปเป็น ip`
* freegeoip `หา location ของ server`
* shodan_hostname `หา domain จาก web shodan`
* ipinfodb `หา location ของ server`
* brute_hosts
* builtwith
* xssed `เคยโดน XSS มาเมื่อไหร่`
