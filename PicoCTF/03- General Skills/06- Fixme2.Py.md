
## Descripción

*Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/5/fixme2.py)*

## Pistas

*Are equality and assignment the same symbol?*

*To view the file in the webshell, do: `$ nano fixme2.py`*

*To exit `nano`, press Ctrl and x and follow the on-screen prompts.*

*The `str_xor` function does not need to be reverse engineered for this challenge.*

## Solución

*WebShell, Python3, Nano*

```
ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/5/fixme2.py
--2025-02-20 02:08:17--  https://artifacts.picoctf.net/c/5/fixme2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1029 (1.0K) [application/octet-stream]
Saving to: 'fixme2.py'

fixme2.py            100%[=====================>]   1.00K  --.-KB/s    in 0s      

2025-02-20 02:08:17 (328 MB/s) - 'fixme2.py' saved [1029/1029]

ceciSolis-picoctf@webshell:~$ nano fixme2.py
ceciSolis-picoctf@webshell:~$ python3 fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
```

picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
## Notas Adicionales 

*La linea que se corrigio es esta se le agrego un igual*
*if flag == "":*
## Referencias 
https://artifacts.picoctf.net/c/5/fixme2.py
https://medium.com/@itsaulgoodman9610/
https://webshell.picoctf.org/