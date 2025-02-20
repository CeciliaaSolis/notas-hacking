
## Descripción

*Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.*

## Pistas

*To view the file in the webshell, do: `$ nano level1.py`*

*To exit `nano`, press Ctrl and x and follow the on-screen prompts.*

*The `str_xor` function does not need to be reverse engineered for this challenge.*

## Solución

*WebShell, Nano*

```
ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/12/level1.py
--2025-02-20 02:27:12--  https://artifacts.picoctf.net/c/12/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.128, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py            100%[=====================>]     876  --.-KB/s    in 0s      

2025-02-20 02:27:12 (35.3 MB/s) - 'level1.py' saved [876/876]

ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
--2025-02-20 02:27:27--  https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.16, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc  100%[=====================>]      30  --.-KB/s    in 0s      

2025-02-20 02:27:27 (1.35 MB/s) - 'level1.flag.txt.enc' saved [30/30]


ceciSolis-picoctf@webshell:~$ nano level1.py
ceciSolis-picoctf@webshell:~$ python3 level1.py
Please enter correct password for flag: 8713
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_1b2fd683}

```
picoCTF{545h_r1ng1ng_1b2fd683}
## Notas Adicionales 

*la contraseña se encontraba en una funcion, solo se extrae se escribe cuando la pide y nos genera la bandera.*
## Referencias 
https://artifacts.picoctf.net/c/12/level1.py
https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
https://medium.com/@nigel.pepeon/
https://webshell.picoctf.org/