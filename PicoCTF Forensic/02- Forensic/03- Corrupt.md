## Descripción

*We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.*
## Pistas

*Try fixing the file header*

## Solución

*Kali*

```
                                                                                                       
┌──(kali㉿kali)-[/]
└─$ sudo wget https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
[sudo] password for kali: 
--2025-04-08 14:50:22--  https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 202940 (198K) [application/octet-stream]
Saving to: ‘mystery’

mystery                    72%[=========================>           ] 143.72K   262KB/s               ^mystery                   100%[====================================>] 198.18K   277KB/s    in 0.7s    

2025-04-08 14:50:24 (277 KB/s) - ‘mystery’ saved [202940/202940]

                                                                                                       
┌──(kali㉿kali)-[/]
└─$ file mystery       
mystery: data
                                                                                                       
┌──(kali㉿kali)-[/]
└─$ exiftool mystery 
ExifTool Version Number         : 13.00
File Name                       : mystery
Directory                       : .
File Size                       : 203 kB
File Modification Date/Time     : 2020:10:26 14:30:20-04:00
File Access Date/Time           : 2025:04:08 14:50:29-04:00
File Inode Change Date/Time     : 2025:04:08 14:50:24-04:00
File Permissions                : -rw-r--r--
Error                           : Unknown file type

┌──(kali㉿kali)-[~]
└─$ hexeditor mystery

                                                                                                       
┌──(kali㉿kali)-[~]
└─$ hexeditor mystery
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ hexeditor mystery
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ hexeditor mystery

                                                                                                       
┌──(kali㉿kali)-[~]
└─$ open mystery 



```

picoCTF{c0rrupt10n_1847995}
## Notas Adicionales 
*e280 83e2 8083 Es un espacio de 2 tipos *

*tuvimos que abrir 4 veces el hexeditor para cambiar cosas de las imagenes*

*IDAT = 49 44 41 54
 `89 50 4E 47 0D 0A 1A 0A`*
```
 00000000: 89 65 4e 34 0d 0a b0 aa 00 00 00 0d 43 22 44 52  .eN4........C"DR
 00000010: 00 00 06 6a 00 00 04 47 08 02 00 00 00 7c 8b ab  ...j...G.....|..
 00000020: 78 00 00 00 01 73 52 47 42 00 ae ce 1c e9 00 00  x....sRGB.......
 00000030: 00 04 67 41 4d 41 00 00 b1 8f 0b fc 61 05 00 00  ..gAMA......a...
 00000040: 00 09 70 48 59 73 aa 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
 00000050: 52 24 f0 aa aa ff a5 ab 44 45 54 78 5e ec bd 3f  R$......DETx^..?
 00000060: 8e 64 cd 71 bd 2d 8b 20 20 80 90 41 83 02 08 d0  .d.q.-.  ..A....
 00000070: f9 ed 40 a0 f3 6e 40 7b 90 23 8f 1e d7 20 8b 3e  ..@..n@{.#... .>
 00000080: b7 c1 0d 70 03 74 b5 03 ae 41 6b f8 be a8 fb dc  ...p.t...Ak.....
 00000090: 3e 7d 2a 22 33 6f de 5b 55 dd 3d 3d f9 20 91 88  >}*"3o.[U.==. ..
```

## Referencias 

https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery