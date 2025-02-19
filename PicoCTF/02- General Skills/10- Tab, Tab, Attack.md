
## Descripción

*Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip)*

## Pistas

*After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)*
## Solución 1

*WebShell*

```
ceciSolis-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip
--2025-02-19 00:57:37--  https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4520 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip                       100%[======================================================================================>]   4.41K  --.-KB/s    in 0s      

2025-02-19 00:57:37 (1.31 GB/s) - 'Addadshashanammu.zip' saved [4520/4520]

ceciSolis-picoctf@webshell:~$ file A
A: cannot open `A' (No such file or directory)
ceciSolis-picoctf@webshell:~$ file Addadshashanammu.zip 
Addadshashanammu.zip: Zip archive data, at least v1.0 to extract, compression method=store
ceciSolis-picoctf@webshell:~$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
ceciSolis-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip
ceciSolis-picoctf@webshell:~$ cd Addadshashanammu/
ceciSolis-picoctf@webshell:~/Addadshashanammu$ ls
Almurbalarammi
ceciSolis-picoctf@webshell:~/Addadshashanammu$ cd Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
ceciSolis-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet
ceciSolis-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ file fang-of-haynekhtnamet 
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=b71f20bc162221a31840f68a978261097ecadac2, not stripped
ceciSolis-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}
```
==picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}==


## Solución 2

*WebShell*

```
ceciSolis-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip
--2025-02-19 02:18:55--  https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4520 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip 100%[=====================>]   4.41K  --.-KB/s    in 0s      

2025-02-19 02:18:55 (2.37 GB/s) - 'Addadshashanammu.zip' saved [4520/4520]

ceciSolis-picoctf@webshell:~$ unzip Addadshashanammu.zip Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
ceciSolis-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
ceciSolis-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurna
bitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet
ceciSolis-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurna
bitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ chmod +x fang-of-haynekhtnamet
ceciSolis-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurna
bitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}
```
==picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}==
## Notas Adicionales

*Con ayuda del Tab nos puede ayudar a llegar hasta el fondo de las carpetas, por el autocompletado*
## Referencias 
https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip
https://medium.com/@CYberVIaz/ctf-writeups-tab-tab-attack-70fabe73f8eb