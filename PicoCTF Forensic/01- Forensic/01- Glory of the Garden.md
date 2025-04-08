## Descripción

*This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.*
## Pistas

*What is a hex editor?*


## Solución

*WebShell*
```
ceciSolis-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg
--2025-04-01 19:55:00--  https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295192 (2.2M) [application/octet-stream]
Saving to: 'garden.jpg'

garden.jpg                   100%[=============================================>]   2.19M  1.83MB/s    in 1.2s    

2025-04-01 19:55:01 (1.83 MB/s) - 'garden.jpg' saved [2295192/2295192]

ceciSolis-picoctf@webshell:~$ strings garden.jpg
7im     b
8;5x
%zR}
Tw1<Oi
yg9S
F7v]
m o5Xex#
V8L;
<]zV&
ZqKvu
7g4js'
wae:uc(>YwG
6       `A
xhS~
wM=GV
gDau%~
,~J|
u)(])F
={~5
h--@3
cZi-
M(.I
]hWP&
jc#k
=7g&
mjx/
s\]|."Ue
\qZf
Here is a flag "picoCTF{more_than_m33ts_the_3y33dd2eEF5}"
```

picoCTF{more_than_m33ts_the_3y33dd2eEF5}
## Notas Adicionales 

*Si intentamos ver el contenido de la imagen, con cat, nos saldrá todo el hexadecimal, pero es más tardado, entonces, con para ver cadenas en un archivo binario, usamos strings, para que imprima todos los ascci que puedan imprimirse, nos muestra todas las cadenas y al final sale la bandera. si no quiero ver todo puedo filtrar con grep *


## Referencias 
https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg
