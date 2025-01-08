# TOOLS
## 1. Enumeration
- __```netdiscover -I eth0 -r <ip>/24```___
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

## Hydra 
- __```hydra -L /usr/share/metasploit-framework/data/wordlists/common_users.txt -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt  127.0.0.1 ftp```__

## Mysql
- __```mysql -h 10.0.1.22 -u root```__


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

