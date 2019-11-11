# Introduction to Web Application Security
## Wireshark
### Filter by IP Address
* ip.addr == 10.0.0.1
* ip.src == 10.0.0.1
* ip.dst == 10.0.0.1

### Filter By HTTP Protocol
* http.accept
* http.request.method == “GET”
* http.content_type == “text/html”

### Filter By Https
* ssl

### Filter by Port
* tcp.port == 80
