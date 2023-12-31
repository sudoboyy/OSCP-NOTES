# HTTP(S) - TCP 80, 443, 8080, 8443

### Things to check :&#x20;

**1 . Check SSL certificate for potential usernames or hostnames**

**2 . View source code for comments or interesting links**

**3 . Knowing what version of Apache running might give clues on what version of distro installed**&#x20;

**Might useful when we want the shell and run any Kernel exploits**

**4 . Check for the existence of a robots.txt file that discloses hidden paths**

```
curl http://<url>/robots.txt
```

### Check for SSL vulnerabilites

```
sslscan <ip address>
```

### Scan for common vulnerabilities in webservers with nikto&#x20;

```
nikto --url http://<ip address> -p <port(s)>
```

**OR**&#x20;

```
nikto -h <ip address> | tee nikto.log 
```

### Discover subdomains with FFUF

```
# Get response size of nonexistent subdomain
curl -s -H "Host: nonexistent.<target url>" <target url> | wc -c
# Filter out response size
ffuf -c -w <wordlist> -u <target url> -H "Host: FUZZ.<target url>" -fs 169
```

