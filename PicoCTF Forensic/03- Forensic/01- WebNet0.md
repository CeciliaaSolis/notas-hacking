
## Descripción

*We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.*
## Pistas

*Try using a tool like Wireshark.*
*How can you decrypt the TLS stream?*
## Solución

*Kali*
```
┌──(kali㉿kali)-[~]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
--2025-05-03 01:42:56--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 13163 (13K) [application/octet-stream]
Saving to: ‘capture.pcap.2’

capture.pcap.2            100%[===================================>]  12.85K  --.-KB/s    in 0s      

2025-05-03 01:42:56 (185 MB/s) - ‘capture.pcap.2’ saved [13163/13163]

                                                                                                      
┌──(kali㉿kali)-[~]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key
--2025-05-03 01:43:04--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key.1’

picopico.key.1            100%[===================================>]   1.66K  --.-KB/s    in 0s      

2025-05-03 01:43:05 (26.0 MB/s) - ‘picopico.key.1’ saved [1704/1704]

                                                                                                      
┌──(kali㉿kali)-[~]
└─$ file capture.pcap.1                                                                             
capture.pcap.1: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 65535)
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ wireshark capture.pcap.2                                                                        
Warning: program compiled against libxml 212 using older 209


```

picoCTF{nongshim.shrimp.crackers}

## Notas Adicionales 

*Al abrir wireshark,abrimos apariencia en protocolos buscamos el de la posta TSL y subimos el archivo pipico.key, despues en edit, find next, en la busqueda ponemos details, string y picoCTF enter y nos mostrara el archivo donde se  encuentra la bandera*

*picopico.key nos ayudo abrir esos archivos de tipo tsl ya que estaban con una contraseña que era esa del archivo.*

## Referencias 
https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key