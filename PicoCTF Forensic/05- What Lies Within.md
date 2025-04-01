## Descripción

*There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?*
## Pistas

*There is data encoded somewhere... there might be an online decoder.*

## Solución

*Kali*
```
──(kali㉿kali)-[~]
└─$ wget https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
--2025-04-01 16:43:26--  https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 625219 (611K) [application/octet-stream]
Saving to: ‘buildings.png’

buildings.png             100%[===================================>] 610.57K  1.56MB/s    in 0.4s    

2025-04-01 16:43:27 (1.56 MB/s) - ‘buildings.png’ saved [625219/625219]

#Con una herramienta en https://stylesuxx.github.io/steganography/
le pasamos la imagen y le damos decode y nos muestra la bandera.

picoCTF{h1d1ng_1n_th3_b1t5}

#Con consola
┌──(kali㉿kali)-[~]
└─$ zsteg  buildings.png 
b1,r,lsb,xy         .. text: "^5>R5YZrG"
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
b1,abgr,msb,xy      .. file: PGP Secret Sub-key -
b2,b,lsb,xy         .. text: "XuH}p#8Iy="
b3,abgr,msb,xy      .. text: "t@Wp-_tH_v\r"
b4,r,lsb,xy         .. text: "fdD\"\"\"\" "
b4,r,msb,xy         .. text: "%Q#gpSv0c05"
b4,g,lsb,xy         .. text: "fDfffDD\"\""
b4,g,msb,xy         .. text: "f\"fff\"\"DD"
b4,b,lsb,xy         .. text: "\"$BDDDDf"
b4,b,msb,xy         .. text: "wwBDDDfUU53w"
b4,rgb,msb,xy       .. text: "dUcv%F#A`"
b4,bgr,msb,xy       .. text: " V\"c7Ga4"
b4,abgr,msb,xy      .. text: "gOC_$_@o"

```

picoCTF{h1d1ng_1n_th3_b1t5}
## Notas Adicionales 

*Esteganografía: ocultar un mensaje dentro de algún otro formato, hay diferentes tipos y ahora la que ocupamos es la de imagenes.*

## Referencias 

https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png

https://stylesuxx.github.io/steganography/
