## Descripción

*We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.*
## Pistas

*Try using a tool like Wireshark*
*What are streams?*
## Solución

*Kali*
```
┌──(kali㉿kali)-[~]
└─$ wget  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
--2025-04-01 16:23:10--  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 239455 (234K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap              100%[===================================>] 233.84K   895KB/s    in 0.3s    

2025-04-01 16:23:11 (895 KB/s) - ‘capture.pcap’ saved [239455/239455]

#Abrimos Wireshark
abrimos la imagen capture.pcap
buscamos algun UPD damos ctrl follow y UPD streams
buscamos de una en una y encontramos la bandera
# Aqui se encuentra udp.stream eq 6
picoCTF{StaT31355_636f6e6e}
```

picoCTF{StaT31355_636f6e6e}

## Notas Adicionales 

*PCAP:Nos permite capturar paquetes de la capa 2 y 7 del modelo OSI*

*Wireshark: Capturar los paquetes*

## Referencias 

https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap

