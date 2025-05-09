

## Descripción

*Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: [dds1-alpine.flag.img.gz](https://mercury.picoctf.net/static/a734f18939e0aaea9d27bc7a243a0ed0/dds1-alpine.flag.img.gz)*
## Pistas

*Have you ever used `file` to determine what a file was?*
*Relevant terminal-fu in picoGym: https://play.picoctf.org/practice/challenge/85*
*Mastering this terminal-fu would enable you to find the flag in a single command: https://play.picoctf.org/practice/challenge/48*
*Using your own computer, you could use qemu to boot from this disk!*
## Solución

*Kali*
```
┌──(kali㉿kali)-[~]
└─$ wget https://mercury.picoctf.net/static/a734f18939e0aaea9d27bc7a243a0ed0/dds1-alpine.flag.img.gz
--2025-05-08 14:17:42--  https://mercury.picoctf.net/static/a734f18939e0aaea9d27bc7a243a0ed0/dds1-alpine.flag.img.gz
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 29768910 (28M) [application/octet-stream]
Saving to: ‘dds1-alpine.flag.img.gz’

dds1-alpine.flag.img.gz   100%[===================================>]  28.39M  3.87MB/s    in 18s     

2025-05-08 14:18:00 (1.59 MB/s) - ‘dds1-alpine.flag.img.gz’ saved [29768910/29768910]

                                                                                                      
┌──(kali㉿kali)-[~]
└─$ gunzip -d dds1-alpine.flag.img.gz 
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ srch_strings dds1-alpine.flag.img                                 
RPf1
Missing operating system.
f`f1
|fRfP
Ht[y9Y[
Multiple active partitions.
|XFSBu  f
Operating system load error.
SYSLINUX
PPPP
u%8M
t f=!GPTu
+fRfP
F}+f`f
Boot error
@1,`A1,`
@1,`
(t~k
/os/mnt
@1,`
@1,`@1,`@1,`
@1,`@1,`@1,`
@1,`@1,`@1,`

┌──(kali㉿kali)-[~]
└─$ srch_strings dds1-alpine.flag.img | grep "pico"

ffffffff81399ccf t pirq_pico_get
ffffffff81399cee t pirq_pico_set
ffffffff820adb46 t pico_router_probe
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_a69a712c}
                                                 
```

picoCTF{f0r3ns1c4t0r_n30phyt3_a69a712c}


## Notas Adicionales 

*1 descargamos el archivo*
*2 descomprimimos el archivo*
*3 con srch_strings para buscar todas las strings q tiene el archivo, nos muestra demasiado, entonces*
*4 usamos srch_strings | grep pico y ya nos muestra las busquedas que coinciden y sale la bandera.*
## Referencias 
