
## Descripción

*Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings) without running it?*

## Pistas

*[strings](https://linux.die.net/man/1/strings)*

## Solución 

*WebShell*

```
ceciSolis-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings
--2025-02-19 00:35:54--  https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings                                    100%[======================================================================================>] 757.84K  1.86MB/s    in 0.4s    

2025-02-19 00:35:55 (1.86 MB/s) - 'strings' saved [776032/776032]

ceciSolis-picoctf@webshell:~$ ls
strings
ceciSolis-picoctf@webshell:~$ file strings 
strings: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=047a5079a5f563cd0e540d28f42a37161093ffda, not stripped
ceciSolis-picoctf@webshell:~$ chmod +x strings
ceciSolis-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_827aee91}
```
==picoCTF{5tRIng5_1T_827aee91}==

## Notas Adicionales

## Referencias 

https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings
https://webshell.picoctf.org/
https://linux.die.net/man/1/strings