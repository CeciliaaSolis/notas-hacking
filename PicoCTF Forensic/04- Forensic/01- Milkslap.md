## Descripción

*http://mercury.picoctf.net:29522/*
## Pistas

*Look at the problem category.*

## Solución

*Kali*
```

┌──(kali㉿kali)-[~]
└─$ wget  http://mercury.picoctf.net:29522/concat_v.png
--2025-05-07 19:17:54--  http://mercury.picoctf.net:29522/concat_v.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:29522... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18095920 (17M) [image/png]
Saving to: ‘concat_v.png’

concat_v.png               15%[====>                               ]   2.63M  92.2KB/s    in 25s     

2025-05-07 19:18:19 (109 KB/s) - Connection closed at byte 2756600. Retrying.

--2025-05-07 19:18:20--  (try: 2)  http://mercury.picoctf.net:29522/concat_v.png
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:29522... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18095920 (17M) [image/png]
Saving to: ‘concat_v.png’

concat_v.png              100%[===================================>]  17.26M  1.41MB/s    in 14s     

2025-05-07 19:18:35 (1.21 MB/s) - ‘concat_v.png’ saved [18095920/18095920]

┌──(kali㉿kali)-[~]
└─$ zsteg concat_v.png
imagedata           .. file: dBase III DBT, version number 0, next free block index 3368931841, 1st item "\001\001\001\001"
b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"
b1,bgr,lsb,xy       .. <wbStego size=9706075, data="\xB6\xAD\xB6}\xDB\xB2lR\x7F\xDF\x86\xB7c\xFC\xFF\xBF\x02Zr\x8E\xE2Z\x12\xD8q\xE5&MJ-X:\xB5\xBF\xF7\x7F\xDB\xDFI\bm\xDB\xDB\x80m\x00\x00\x00\xB6m\xDB\xDB\xB6\x00\x00\x00\xB6\xB6\x00m\xDB\x12\x12m\xDB\xDB\x00\x00\x00\x00\x00\xB6m\xDB\x00\xB6\x00\x00\x00\xDB\xB6mm\xDB\xB6\xB6\x00\x00\x00\x00\x00m\xDB", even=true, mix=true, controlbyte="[">
b2,r,lsb,xy         .. file: SoftQuad DESC or font file binary
b2,r,msb,xy         .. file: VISX image file
b2,g,lsb,xy         .. file: VISX image file
b2,g,msb,xy         .. file: SoftQuad DESC or font file binary - version 15722
b2,b,msb,xy         .. text: "UfUUUU@UUU"
b4,r,lsb,xy         .. text: "\"\"\"\"\"#4D"
b4,r,msb,xy         .. text: "wwww3333"
b4,g,lsb,xy         .. text: "wewwwwvUS"
b4,g,msb,xy         .. text: "\"\"\"\"DDDD"
b4,b,lsb,xy         .. text: "vdUeVwweDFw"
b4,b,msb,xy         .. text: "UUYYUUUUUUUU"

```
picoCTF{imag3_m4n1pul4t10n_sl4p5}
## Notas Adicionales 

*entramos a la página, nos muestra un GIF,en la terminal le damos un curl al link para checar que tiene el gif, como no muestra nada mas que la imagen, entonces descargamos la imagen y con ayuda de la herramienta zsteg, de esteganografia, mostramos la imagen y nos da la bandera. *
## Referencias 
