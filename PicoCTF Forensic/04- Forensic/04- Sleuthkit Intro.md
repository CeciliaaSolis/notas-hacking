

## Descripción

*Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.[Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz)

Additional details will be available after launching your challenge instance.*
*Access checker program:* `nc saturn.picoctf.net 51756`
## Pistas

*none*
## Solución

*Kali*
```
┌──(kali㉿kali)-[~]
└─$ sudo apt-get install sleuthkit                                    
[sudo] password for kali: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
sleuthkit is already the newest version (4.12.1+dfsg-0kali6).
sleuthkit set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/164/disk.img.gz
--2025-05-08 22:19:21--  https://artifacts.picoctf.net/c/164/disk.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:7200:16:5ec5:2840:93a1, 2600:9000:25ed:8200:16:5ec5:2840:93a1, 2600:9000:25ed:7c00:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:7200:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 29714372 (28M) [application/octet-stream]
Saving to: ‘disk.img.gz’

disk.img.gz               100%[====================================>]  28.34M  4.48MB/s    in 6.9s    

2025-05-08 22:19:28 (4.12 MB/s) - ‘disk.img.gz’ saved [29714372/29714372]

                                                                                                       
┌──(kali㉿kali)-[~]
└─$ gzip -d disk.img.gz 
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 51756
What is the size of the Linux partition in the given disk image?
Length in sectors: 2752
2752
That is not correct. Feel free to try again.
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 51756
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}

```
picoCTF{mm15_f7w!}



## Notas Adicionales 

*Instalamos sleuthkit*
*Descargamos el archivo*
*Descomprimimos el archivo*
*Con mmls  enumeramos el contenido de la tabla de particiones*
*Nos conectamos al servidor que nos dan*
*ponemos el lenght in sectors que son 20752 enter y nos da la bandera.*
## Referencias 
