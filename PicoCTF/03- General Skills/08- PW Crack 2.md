
## Descripción

*Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.*

## Pistas

*Does that encoding look familiar?*

*The `str_xor` function does not need to be reverse engineered for this challenge.*

## Solución

*WebShell,Nano y Python3*

```
ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/14/level2.py
--2025-02-20 02:36:41--  https://artifacts.picoctf.net/c/14/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.16, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py            100%[=====================>]     914  --.-KB/s    in 0s      

2025-02-20 02:36:41 (310 MB/s) - 'level2.py' saved [914/914]

ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
--2025-02-20 02:36:53--  https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.128, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc  100%[=====================>]      31  --.-KB/s    in 0s      

2025-02-20 02:36:53 (30.1 MB/s) - 'level2.flag.txt.enc' saved [31/31]

ceciSolis-picoctf@webshell:~$ nano level2.py
ceciSolis-picoctf@webshell:~$ python3  level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}

```

*CyberChef*
*Input: chr(0x34)+chr(0x65) + chr(0x63) + chr(0x39) 
Recipe: From Hex
Output: 4ec9*

picoCTF{tr45h_51ng1ng_9701e681}
## Notas Adicionales 

*Al abrir el archivo level2.py en nano, la contraseña estaba en hexadecimal, entonces solamente se hace la conversión*
## Referencias 
https://artifacts.picoctf.net/c/14/level2.py

https://artifacts.picoctf.net/c/14/level2.flag.txt.enc

http://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=CmNocigweDM0KQoKY2hyKDB4NjUpICsgY2hyKDB4NjMpICsgY2hyKDB4MzkpIA&oeol=FF

https://webshell.picoctf.org/
