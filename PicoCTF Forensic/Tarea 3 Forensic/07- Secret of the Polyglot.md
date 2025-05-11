## Descripción

*The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/98/flag2of2-final.pdf).*
## Pistas

*This problem can be solved by just opening the file in different ways*

## Solución

*Kali*
```
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c_titan/98/flag2of2-final.pdf
--2025-05-11 01:05:18--  https://artifacts.picoctf.net/c_titan/98/flag2of2-final.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:6600:16:5ec5:2840:93a1, 2600:9000:25ed:a400:16:5ec5:2840:93a1, 2600:9000:25ed:2800:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:6600:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3362 (3.3K) [application/octet-stream]
Saving to: ‘flag2of2-final.pdf’

flag2of2-final.pdf        100%[===================================>]   3.28K  --.-KB/s    in 0s      

2025-05-11 01:05:19 (57.8 MB/s) - ‘flag2of2-final.pdf’ saved [3362/3362]

                                                                                                      
┌──(kali㉿kali)-[~]
└─$ open flag2of2-final.pdf 
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ 


```

picoCTF{f1u3n7_1n_pn9_&_pdf_1f991f77}
## Notas Adicionales 

*Descargue el archivo, lo abri venia la mitad de la bandera, como en las pistas decia q podiamos abrir desde otra aplicacion entonces la abri como imagen y me salio el principio de la bandera, solo junte las 2 partes y listo.*
## Referencias 

