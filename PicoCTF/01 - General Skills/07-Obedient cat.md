## Descripción

This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag).

## Pistas

°**Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.**

°**To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag`**

° **$ man cat**
## Solucion 1

*Webshell con Python*

`ceciSolis-picoctf@webshell:~$  wget https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag`
`--2025-02-12 01:28:58--  https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag`
`Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142`
`Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.`
`HTTP request sent, awaiting response... 200 OK`
`Length: 34 [application/octet-stream]`
`Saving to: 'flag.1'`

`flag.1                                                    100%[=======================================================================================================================================>]      34  --.-KB/s    in 0s`      

`2025-02-12 01:28:58 (13.0 MB/s) - 'flag.1' saved [34/34]`

`ceciSolis-picoctf@webshell:~$ cat flag.1`
==`picoCTF{s4n1ty_v3r1f13d_2aa22101}`==

## Notas Adicionales 

Me ayude de una pagina web ya que no entendia lo que era cat
Cat: os permite leer,mostrar, unir y crear archivos
En este caso nos permitio mostrar el archivo que estaba en la URL.

## Referencias 
https://webshell.picoctf.org/
https://ctftime.org/writeup/28148

