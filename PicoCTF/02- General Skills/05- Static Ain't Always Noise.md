
## Descripción

*Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static)? This [BASH script](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/ltdis.sh) might help!*

## Pistas 

*None*

## Solución 1

*WebShell*
```
ceciSolis-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static
--2025-02-19 00:20:08--  https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                                               100%[===================================================================================================================>]   8.18K  --.-KB/s    in 0s      

2025-02-19 00:20:08 (256 MB/s) - 'static' saved [8376/8376]

ceciSolis-picoctf@webshell:~$ file static
static: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=33934f7b8aea8e359749ed57dca4cd26d6059acf, not stripped
ceciSolis-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/ltdis.sh
--2025-02-19 00:21:17--  https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/ltdis.sh
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh                                             100%[===================================================================================================================>]     785  --.-KB/s    in 0s      

2025-02-19 00:21:17 (594 MB/s) - 'ltdis.sh' saved [785/785]

eciSolis-picoctf@webshell:~$ chmod +x static
ceciSolis-picoctf@webshell:~$ ./static
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
ceciSolis-picoctf@webshell:~$ bash ltdis.sh
Attempting disassembly of  ...
objdump: 'a.out': No such file
objdump: section '.text' mentioned in a -j option, but not found in any input file
Disassembly failed!
Usage: ltdis.sh <program-file>
Bye!
ceciSolis-picoctf@webshell:~$ bash ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
ceciSolis-picoctf@webshell:~$ nano ltdis.sh
ceciSolis-picoctf@webshell:~$ ls
ltdis.sh  static  static.ltdis.strings.txt  static.ltdis.x86_64.txt
ceciSolis-picoctf@webshell:~$ cat static.ltdis.strings.txt | grep pico
   1020 picoCTF{d15a5m_t34s3r_1e6a7731}
```
==picoCTF{d15a5m_t34s3r_1e6a7731}==

## Solución 2

*WebShell*
```
ceciSolis-picoctf@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_1e6a7731}

```
==picoCTF{d15a5m_t34s3r_1e6a7731}==

## Notas Aicionales

*Ambas soluciones están bien simplemente son pasos diferentes, en una solo nos metimos al archivo y buscamos la bandera, en la otra fuimos carpeta, por carpeta buscando la bandera*

## Referencias 

https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static
https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/ltdis.sh
https://webshell.picoctf.org/
