## Descripción

**Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.**
## Pistas

**Remember the flag format is picoCTF{XXXX}
What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)**

## Solucion 1

*Webshell con Python*

`ceciSolis-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 4427 | grep pico`
==`picoCTF{digital_plumb3r_5ea1fbd7}`==

## Notas Adicionales 
Grep: para buscar palabras en un archivo, por eso se usa grep pico es la primera palabra para encontrar la bandera.

## Referencias 
http://www.linfo.org/pipes.htm
https://webshell.picoctf.org/
