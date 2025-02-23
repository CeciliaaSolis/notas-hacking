
## Descripción

*Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.`ssh -p 60072 ctf-player@saturn.picoctf.net`The password is `8a707622`*

## Pistas

*Experiment with different shell syntax*
## Solución

*WebShell y Python3 *

```
ceciSolis-picoctf@webshell:~$ ssh -p 60072 ctf-player@saturn.picoctf.net
ctf-player@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Fri Feb 21 02:33:27 2025 from 127.0.0.1
Special$ ((ls))
((ls)) 
blargh
Special$ ((cd)) < blargh
((cd)) < large 
sh: 1: cannot open large: No such file
Special$ ((cat)) < blargh
((cat)) < large 
sh: 1: cannot open large: No such file
Special$ ((cat)) < blargh/flag.txt
((cat)) < blargh/flag.txt 
picoCTF{5p311ch3ck_15_7h3_w0r57_a60bdf40}Special$ 

```
picoCTF{5p311ch3ck_15_7h3_w0r57_a60bdf40}

## Notas Adicionales 

*Es una sintaxis diferente de la cual tuve que investigar como funcionaba*

*En vez de solo ser cd o ls, se ponian entre parentesis, para buscar el contenido de un archivo, era ((catt)) <directorio/nombrearchivo*

*Asi fue como encontre la bandera.*
## Referencias 

https://webshell.picoctf.org/
https://github.com/snwau/picoCTF-2023-Writeup/blob/main/General%20Skills/Special/Special.md