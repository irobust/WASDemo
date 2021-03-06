# Phase II: Mapping
## Nmap
* nmap 10.0.2.0/24
* nmap 10.0.2.0/24 --exclude 10.0.2.2
* nmap -iL list.txt
* nmap 10.0.2.4
* nmap -p1-3000 10.0.2.4
* nmap -p80,443 10.0.2.4
* nmap -F 10.0.2.4 `Scan เฉพาะ Famous port เท่านั้น`
* nmap --top-ports 10 10.0.2.4
* nmap -sS 10.0.2.4 `SYNC Scan`
* nmap -sT 10.0.2.4 `Establish connection`
* nmap -Pn 10.0.2.4 `สำหรับ server ที่ปิด ICMP`
* nmap -T0 10.0.2.4 `delay request ให้ช้าลงเพื่อหลบ IDS, IPS`
* nmap -O -sV --traceroute --script default 10.0.2.4 `-sC same as --script default`
* nmap -A 10.0.2.4 `same as above`
* nmap --script vuln,default 10.0.2.4 `/usr/share/nmap/scripts/http-title.nse`
* nmap --script http-title 10.0.2.4
* nmap --script http-title --script-args="http-title.url=/sqli/example1.php" *IP Address*
* nmap -p80 --script "http-title"  *IP Address*
* nmap -p80 --script "http-title" --script-args "http-title.url=/sqli/example1.php" *IP Address*
* nmap -p80 --script "http-enum" -d *IP Address*
* nmap -p80 --script "http-enum" --script-args "http-enum-displayall=1"  -d *IP Address*

## Other Tools
* masscan
* zenmap
* [angry scanner](https://angryip.org)
* SPARTA
* zmap

## Banner
1. Wappalyzer (Chrome Plug-in)
2. BuiltWith.com
3. whatweb example.com

## SSL Analysis
1. ssllabs.com
2. sslscan example.com
3. sslyze example.com --heartbleed --hsts
4. curl -I http://example.com

## Web Archetecture

### Virtual Host
* search with Bing.com `ip:"111.111.111.111"`
* robtex.com
* [Pentest Tools](https://pentest-tools.com/information-gathering/find-virtual-hosts)
* dig axfr @ns5.linode.com scanme.org +nostat +nocmd +nocomments

### Load Balance
* lbd sanook.com

### Web Application Firewall(WAF)
* wafw00f example.com
* nmap -p80,443 --script "http-waf-detect" *Target Website*

## Web Spider and directory brute forcing
* OWASP ZAP (GUI)
* Burp suite (GUI)
* dirbuster (GUI)
* dirb http://10.0.2.4
* gobuster -u [URL] -w [Wordlist] -x php `apt-get install gobuster`
* wfuzz --hc 404 -w [wordlist] http://10.0.2.4/FUZZ



	


