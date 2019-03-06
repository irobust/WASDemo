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
* nmap --script vuln,default 10.0.2.4
* nmap --script http-title 10.0.2.4
* nmap --script http-title --script-args="http-title.url=/sqli/example1.php" 10.0.2.4

## Banner
1. Wappalyzer (Chrome Plug-in)
2. BuiltWith.com
3. whatweb example.com

## SSL Analysis
1. ssllabs.com
2. sslscan example.com
3. sslyze example.com --heartbleed

## Web Archetecture

### Virtual Host
* search with Bing.com `ip:111.111.111.111`
* robtex.com

### Load Balance
* lbd sanook.com

### Web Application Firewall(WAF)
* wafw00f example.com

## Web Spider and directory brute forcing
* OWASP ZAP (GUI)
* Burp suite (GUI)
* dirbuster (GUI)
* dirb http://10.0.2.4
* gobuster -u ... -w ... -x php `apt-get install gobuster`
* wfuzz --hc 404 -w ... http://10.0.2.4/FUZZ



	


