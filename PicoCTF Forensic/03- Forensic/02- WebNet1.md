
## Descripción

*We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.*
## Pistas

*Try using a tool like Wireshark.*
*How can you decrypt the TLS stream?*

## Solución

*Kali*
```
┌──(kali㉿kali)-[~]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
--2025-05-03 01:44:27--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘capture.pcap.3’

capture.pcap.3            100%[===================================>]  90.36K   234KB/s    in 0.4s    

2025-05-03 01:44:28 (234 KB/s) - ‘capture.pcap.3’ saved [92525/92525]

                                                                                                      
┌──(kali㉿kali)-[~]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
--2025-05-03 01:44:53--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key.2’

picopico.key.2            100%[===================================>]   1.66K  --.-KB/s    in 0s      

2025-05-03 01:44:53 (14.7 MB/s) - ‘picopico.key.2’ saved [1704/1704]
                                                                                                    
┌──(kali㉿kali)-[~]
└─$ file capture.pcap.3
capture.pcap.3: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 65535)
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ wireshark capture.pcap.3                                                                        
Warning: program compiled against libxml 212 using older 209

																							
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ strings  vulture.jpg -n15
picoCTF{honey.roasted.peanuts}
 )/'%'/9339GDG]]}
 )/'%'/9339GDG]]}
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
                                                 
```

picoCTF{honey.roasted.peanuts}

## Notas Adicionales 

*Al abrir wireshark,abrimos apariencia en protocolos buscamos el de la posta TSL y subimos el archivo pipico.key, despues en edit, find next, en la busqueda ponemos details, string y picoCTF enter y nos mostrara el archivo donde se  encuentra algo que parece la bandera pero no lo es, entonces vemos que esta cargando una imagen en el htpp, le damos en file, exportobject en http, en image la guardamos y le dimos un strings para ver que contenia la imagen y aqui ya muestra la bandera.*
## Referencias 

https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key