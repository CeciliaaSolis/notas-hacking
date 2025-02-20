
## Descripción

*Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/25/fixme1.py)*

## Pistas

*Indentation is very meaningful in Python*

*To view the file in the webshell, do: `$ nano fixme1.py`*

*To exit `nano`, press Ctrl and x and follow the on-screen prompts.*

*The `str_xor` function does not need to be reverse engineered for this challenge.*

## Solución

*WebShell, Python3 y Nano*

```
ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/25/fixme1.py
--2025-02-20 02:00:50--  https://artifacts.picoctf.net/c/25/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.92, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py'

fixme1.py            100%[=====================>]     837  --.-KB/s    in 0s      

2025-02-20 02:00:50 (34.9 MB/s) - 'fixme1.py' saved [837/837]

ceciSolis-picoctf@webshell:~$ nano fixme1.py
ceciSolis-picoctf@webshell:~$ python3 fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_6a476c8f}
```
picoCTF{1nd3nt1ty_cr1515_6a476c8f}

## Notas Adicionales

*El error que habia al ver el archivo en nano, era la identacion, tenia dos espacios demas en un print al salir y guardarlo, ya funciona y muestra la bandera*
## Referencias 
https://artifacts.picoctf.net/c/25/fixme1.py
https://shibushivansh.medium.com/
https://webshell.picoctf.org/