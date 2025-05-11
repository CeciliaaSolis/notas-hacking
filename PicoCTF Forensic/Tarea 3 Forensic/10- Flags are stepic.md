## Descripción

*A group of underground hackers might be using this legit site to communicate. Use your forensic techniques to uncover their messageTry it [here](http://standard-pizzas.picoctf.net:64773/)!*

## Pistas

*In the country that doesn't exist, the flag persists*

## Solución

*Kali*
```
┌──(kali㉿kali)-[~]
└─$ file upz.png      
upz.png: PNG image data, 14173 x 10630, 8-bit/color RGBA, non-interlaced

																									┌──(root㉿kali)-[~]
└─# sudo apt install stepic       
Installing:                     
  stepic
                                                                                                      
Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 1756
  Download size: 10.1 kB
  Space needed: 50.2 kB / 61.4 GB available

Get:1 http://kali.download/kali kali-rolling/main amd64 stepic all 0.5.0-2 [10.1 kB]
Fetched 10.1 kB in 2s (5,364 B/s)  
Selecting previously unselected package stepic.
(Reading database ... 400785 files and directories currently installed.)
Preparing to unpack .../stepic_0.5.0-2_all.deb ...
Unpacking stepic (0.5.0-2) ...
Setting up stepic (0.5.0-2) ...
Processing triggers for doc-base (0.11.2) ...
Processing 41 changed doc-base files, 1 added doc-base file...
Processing triggers for man-db (2.13.0-1) ...
Processing triggers for kali-menu (2024.4.0) ...



┌──(kali㉿kali)-[~]
└─$ stepic -d -i  upz.png -o flag.txt
/usr/lib/python3/dist-packages/PIL/Image.py:3368: DecompressionBombWarning: Image size (150658990 pixels) exceeds limit of 89478485 pixels, could be decompression bomb DOS attack.
  warnings.warn(
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ cat flag.txt
picoCTF{fl4g_h45_fl4g1a2a9157}                                                                                                      
┌──(kali㉿kali)-[~]
└─$ 


```
picoCTF{fl4g_h45_fl4g1a2a9157}    
## Notas Adicionales 

*Checamos la pagina web y en las banderas se mostraba algo que pesaba mas que los demas, entonces descargue la imagen, le hice un file, para observar si era realmente imagen,despues intente hacer un zsteg y no funciono,buscamos mas herramientas de esteganografia y encontre que stepic funcionaba mejor y que si ayudaria en esta imagen, lo descargue la libreria, le di stepic -d -i  el nombre de la imagen -o nombre donde quiero que se guarden los datos, le di enter busque si habia un archivo con el nombre y le hice cat y me mostro la bandera. *
## Referencias 

https://www.youtube.com/watch?time_continue=596&v=qwGyg0SKpf0&embeds_referring_euri=https%3A%2F%2Fwww.google.com%2Fsearch%3Fq%3Dare%2Bflags%2Bstepics%26rlz%3D1C1GCEU_esMX1161MX1161%26oq%3Dare%2Bflags%2Bstepics%26gs_lcrp%3DEgZjaHJvbWUyBggAEEUYOT&source_ve_path=Mjg2NjIsMjM4NTE