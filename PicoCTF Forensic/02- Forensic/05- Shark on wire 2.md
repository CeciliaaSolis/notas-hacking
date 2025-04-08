## Descripción

*We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.*

## Pistas


*None*
## Solución

*Kali*
```
┌──(kali㉿kali)-[/]
└─$ sudo wget https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap  
[sudo] password for kali: 
--2025-04-08 15:17:11--  https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap              100%[====================================>] 109.69K   652KB/s    in 0.2s    

2025-04-08 15:17:11 (652 KB/s) - ‘capture.pcap’ saved [112318/112318]

                                                                                                       
┌──(kali㉿kali)-[/]
└─$ file capture.pcap  
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
                                                                                                       
┌──(kali㉿kali)-[/]
└─$ wireshark capture.pcap &                                                                          
[1] 33435
                                                                                                       
┌──(kali㉿kali)-[/]
└─$ Warning: program compiled against libxml 212 using older 209
python3                            
Python 3.12.7 (main, Nov  8 2024, 17:55:36) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> sudo apt install python3-scapy
  File "<stdin>", line 1
    sudo apt install python3-scapy
         ^^^
SyntaxError: invalid syntax
>>> sudo apt install python3-scapy
KeyboardInterrupt
>>> 
>>> 
KeyboardInterrupt
>>> exit
Use exit() or Ctrl-D (i.e. EOF) to exit
>>> 
                                                                                                       
┌──(kali㉿kali)-[/]
└─$ nano llave 
from scapy.all import *

packets = rdpcap('capture.pcap')

flag=''

for p in packets:
    if UDP in p and p[UDP].dport == 22:
        if p[UDP].sport > 5000:
            flag+=chr(p[UDP].sport - 5000)

print(flag)


                                                                                                       
┌──(kali㉿kali)-[/]
└─$ sudo nano llave

                                                                                                       
┌──(kali㉿kali)-[/]
└─$ python llave  
picoCTF{p1LLf3r3d_data_v1a_st3g0}

```
picoCTF{p1LLf3r3d_data_v1a_st3g0}
## Notas Adicionales 

*Con WireShark se puede buscar todos los udp*
*Con nano hcimos un codigo donde importamos scapy que es una herramienta de python, que nos permitiera sacar los valores de la bandera*


## Referencias 
https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap