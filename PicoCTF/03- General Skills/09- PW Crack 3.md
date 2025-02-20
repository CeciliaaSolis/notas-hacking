
## Descripción

*Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/16/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/16/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.*

## Pistas

*To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`*

*To exit `bvi` type `:q` and press enter.*

*The `str_xor` function does not need to be reverse engineered for this challenge.*

## Solución

*WebShell, Python,BVI*

```
ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.py
--2025-02-20 02:47:27--  https://artifacts.picoctf.net/c/16/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.128, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py            100%[=====================>]   1.31K  --.-KB/s    in 0s      

2025-02-20 02:47:27 (1.16 GB/s) - 'level3.py' saved [1337/1337]

ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.flag.txt.enc
--2025-02-20 02:48:53--  https://artifacts.picoctf.net/c/16/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.92, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc  100%[=====================>]      31  --.-KB/s    in 0s      

2025-02-20 02:48:53 (346 KB/s) - 'level3.flag.txt.enc' saved [31/31]

ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.hash.bin
--2025-02-20 02:49:06--  https://artifacts.picoctf.net/c/16/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.16, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin      100%[=====================>]      16  --.-KB/s    in 0s      

2025-02-20 02:49:06 (11.0 MB/s) - 'level3.hash.bin' saved [16/16]

ceciSolis-picoctf@webshell:~$ ls
level3.flag.txt.enc  level3.hash.bin  level3.py

ceciSolis-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: 865e
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}

```

picoCTF{m45h_fl1ng1ng_2b072a90}
## Notas Adicionales 
*Habia 7 contraseñas posibles en el archivo level3.py abierto con nano, solamente probe con todas para ver cual era la que daba la bandera*
"6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"
## Referencias 

https://artifacts.picoctf.net/c/16/level3.py
https://artifacts.picoctf.net/c/16/level3.flag.txt.enc
https://artifacts.picoctf.net/c/16/level3.hash.bin
