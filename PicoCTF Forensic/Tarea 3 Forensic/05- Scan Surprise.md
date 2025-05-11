## Descripción

*I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/16/challenge.zip)

The same files are accessible via SSH here:`ssh -p 64568 ctf-player@atlas.picoctf.net`Using the password `6abf4a82`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!*
## Pistas

*QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.*

*Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11*

*If you don't have access to a phone, you can also use zbar-tools to convert an image to text*
## Solución

*Kali*
```
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c_atlas/16/challenge.zip              
--2025-05-11 00:43:11--  https://artifacts.picoctf.net/c_atlas/16/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:8c00:16:5ec5:2840:93a1, 2600:9000:25ed:be00:16:5ec5:2840:93a1, 2600:9000:25ed:2600:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:8c00:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 736 [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip             100%[===================================>]     736  --.-KB/s    in 0s      

2025-05-11 00:43:11 (5.44 MB/s) - ‘challenge.zip’ saved [736/736]

                                                                                                      
┌──(kali㉿kali)-[~]
└─$ unzip challenge.zip   
Archive:  challenge.zip
   creating: home/ctf-player/drop-in/
 extracting: home/ctf-player/drop-in/flag.png  
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ cd home/ctf-player/drop-in/flag.png 
cd: not a directory: home/ctf-player/drop-in/flag.png
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ cd home/ctf-player/drop-in/         
                                                                                                      
┌──(kali㉿kali)-[~/home/ctf-player/drop-in]
└─$ ls
flag.png
                                                                                                      
┌──(kali㉿kali)-[~/home/ctf-player/drop-in]
└─$ open flag.png   
```
picoCTF{p33k_@_b00_7843f77c}
## Notas Adicionales 

*Descargue el archivo, como era un zip, use unzip para descomprimirlo, se extrajo todo y nos daba una carpeta que tenia la bandera,entro a la carpeta, hago ls abro la imagen y es un código qr, lo escanee con mi telefono y me dio la bandera.*

## Referencias 

