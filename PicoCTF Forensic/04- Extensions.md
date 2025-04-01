## Descripción

*This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?*
## Pistas

*How do operating systems know what kind of file it is? (It's not just the ending!*

*Make sure to submit the flag as picoCTF{XXXXX}*

## Solución

*Kali*

```
┌──(kali㉿kali)-[~]
└─$ wget https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
--2025-04-01 16:35:39--  https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 9984 (9.8K) [application/octet-stream]
Saving to: ‘flag.txt.1’

flag.txt.1                100%[===================================>]   9.75K  --.-KB/s    in 0s      

2025-04-01 16:35:39 (101 MB/s) - ‘flag.txt.1’ saved [9984/9984]
                                                                                  
┌──(kali㉿kali)-[~]
└─$ file flag.txt.1                                                                             
flag.txt.1: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ mv flag.txt.1 flag.png
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ open flag.png
                     

picoCTF{now_you_know_about_extensions}
```

picoCTF{now_you_know_about_extensions}
## Notas Adicionales 


*Nos dice que es txt, pero al analizarlo es una imagen.png*
*89 50 4e 47 Es una firma de archivos png*

*Le cambiamos la extension para que sea la correcta *

*Finalmente la abrimos y nos mostrara una imagen png con la bandera*
## Referencias 

https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
