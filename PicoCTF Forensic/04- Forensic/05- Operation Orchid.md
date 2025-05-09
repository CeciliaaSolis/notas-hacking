

## Descripción

*Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/213/disk.flag.img.gz)*
## Pistas

*none*
## Solución

*Kali*
```
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/213/disk.flag.img.gz
--2025-05-08 22:49:11--  https://artifacts.picoctf.net/c/213/disk.flag.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:6600:16:5ec5:2840:93a1, 2600:9000:25ed:2200:16:5ec5:2840:93a1, 2600:9000:25ed:1c00:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:6600:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 44360922 (42M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz          100%[====================================>]  42.31M  8.27MB/s    in 11s     

2025-05-08 22:49:22 (3.97 MB/s) - ‘disk.flag.img.gz’ saved [44360922/44360922]

                                                                                                       
┌──(kali㉿kali)-[~]
└─$ gunzip disk.flag.img.gz 

                                                                                                       
┌──(kali㉿kali)-[~]
└─$ 
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ ls
Desktop  disk.flag.img
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ file disk.flag.img 
disk.flag.img: DOS/MBR boot sector; partition 1 : ID=0x83, active, start-CHS (0x0,32,33), end-CHS (0xc,223,19), startsector 2048, 204800 sectors; partition 2 : ID=0x82, start-CHS (0xc,223,20), end-CHS (0x19,159,6), startsector 206848, 204800 sectors; partition 3 : ID=0x83, start-CHS (0x19,159,7), end-CHS (0x32,253,11), startsector 411648, 407552 sectors
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ ls /tmp
config-err-mKmtJm
disk.flag.img.gz
ssh-tR2QYuslQahp
systemd-private-6c38861c23c24b0baf37bd831577c830-colord.service-xOFvMU
systemd-private-6c38861c23c24b0baf37bd831577c830-haveged.service-NXorIq
systemd-private-6c38861c23c24b0baf37bd831577c830-ModemManager.service-omPEwK
systemd-private-6c38861c23c24b0baf37bd831577c830-polkit.service-ifS357
systemd-private-6c38861c23c24b0baf37bd831577c830-systemd-logind.service-RjaBAg
systemd-private-6c38861c23c24b0baf37bd831577c830-upower.service-tR6nP5
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ sudo mount disk.flag.img /tmp/foo -o offset=$((411648*512))
[sudo] password for kali: 
mount: /tmp/foo: mount point does not exist.
       dmesg(1) may have more information after failed mount system call.
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ cd tmp/
cd: no such file or directory: tmp/
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ mkdir -p /tmp/foo 
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ sudo mount disk.flag.img /tmp/foo -o offset=$((411648*512))
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ cd /tmp/foo
                                                                                                       
┌──(kali㉿kali)-[/tmp/foo]
└─$ ls     
bin   dev  home  lost+found  mnt  proc  run   srv   sys  usr
boot  etc  lib   media       opt  root  sbin  swap  tmp  var
                                                                                                       
┌──(kali㉿kali)-[/tmp/foo]
└─$ sudo su                                                    
┌──(root㉿kali)-[/tmp/foo]
└─# cd root 
                                                                                                       
┌──(root㉿kali)-[/tmp/foo/root]
└─# ls
flag.txt.enc
                                                                                                       
┌──(root㉿kali)-[/tmp/foo/root]
└─# cat .ash history 
cat: .ash: No such file or directory
cat: history: No such file or directory
                                                                                                       
┌──(root㉿kali)-[/tmp/foo/root]
└─# ls -alps
total 4
1 drwx------  2 root root 1024 Oct  6  2021 ./
1 drwxr-xr-x 22 root root 1024 Oct  6  2021 ../
1 -rw-------  1 root root  202 Oct  6  2021 .ash_history
1 -rw-r--r--  1 root root   64 Oct  6  2021 flag.txt.enc
                                                                                                       
┌──(root㉿kali)-[/tmp/foo/root]
└─# cat .ash_history
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
                                                                                                       
┌──(root㉿kali)-[/tmp/foo/root]
└─# file flag.txt.enc 
flag.txt.enc: openssl enc'd data with salted password
                                                                                                       
┌──(root㉿kali)-[/tmp/foo/root]
└─# openssl aes256 -d -in flag.txt.enc -out descrypt.txt
enter AES-256-CBC decryption password:
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40879FC5A77F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                                                       
┌──(root㉿kali)-[/tmp/foo/root]
└─# cat descrypt.txt 
picoCTF{h4un71ng_p457_5113beab}                                                                                                       


```
picoCTF{h4un71ng_p457_5113beab}                                                         
## Notas Adicionales 

*Descargamos el archivo, lo descomprimimos, hicimos el mmls de particiones,montamos un disco en la carpeta tmp, entramos al root, nos da con un cat ash_history donde esta la contraseña de la flag.txt.enc, la desencriptamos con openssl y la pasamos a otro archivo q llamamos decrypt.txt, le hacemos un cat y esta la bandera.*
## Referencias 
