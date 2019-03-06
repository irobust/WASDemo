# Phase II: Mapping
## Nmap
	* nmap 10.0.2.0/24
	* nmap 10.0.2.0/24 --exclude 10.0.2.2
	* nmap -iL list.txt
	* nmap 10.0.2.4
	* nmap -p1-3000 10.0.2.4
	* nmap -p80,443 10.0.2.4
	* nmap -F 10.0.2.4
	* nmap --top-ports 10 10.0.2.4
	* nmap -sS 10.0.2.4
	* nmap -sT 10.0.2.4
	* nmap -Pn 10.0.2.4 `สำหรับ server ที่ปิด ICMP`
	* nmap -T0 10.0.2.4
	* nmap -O -sV --traceroute --script default 10.0.2.4
	* nmap -A 10.0.2.4 `same as above`
	* nmap --script vuln,default 10.0.2.4
	* nmap --script http-title 10.0.2.4
	* nmap --script http-title --script-args="http-title.url=/sqli/example1.php" 10.0.2.4

	


