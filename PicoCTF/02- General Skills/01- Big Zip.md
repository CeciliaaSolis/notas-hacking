
## Descripción

*Unzip this archive and find the flag.*
- *[Download zip file]()* 
## Pistas
 *Can grep be instructed to look at every file
  in a directory and its subdirectories?*
## Solución 1

*Webshell *

```
ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/504/big-zip-files.zip
--2025-02-18 01:23:50--  https://artifacts.picoctf.net/c/504/big-zip-files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.128, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3182988 (3.0M) [application/octet-stream]
Saving to: 'big-zip-files.zip.4'

big-zip-files.zip.4                                  100%[===================================================================================================================>]   3.04M  1.82MB/s    in 1.7s    

2025-02-18 01:23:52 (1.82 MB/s) - 'big-zip-files.zip.4' saved [3182988/3182988]

ceciSolis-picoctf@webshell:~$ unzip big-zip-files.zip.4
ceciSolis-picoctf@webshell:~$ cd big-zip-files
ceciSolis-picoctf@webshell:~/big-zip-files$  grep pico
ceciSolis-picoctf@webshell:~/big-zip-files$  grep -r  pico
folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
```
==picoCTF{gr3p_15_m4g1c_ef8790dc}==
## Notas Adicionales 
*Para descomprimir arichvos se utiliza UNZIP*
## Referencias 
https://artifacts.picoctf.net/c/504/big-zip-files.zip
https://webshell.picoctf.org/