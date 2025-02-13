## Descripción

**What is 0x3D (base 16) in decimal (base 10)?**

## Pistas

**Submit your answer in our flag format.
For example, if your answer was '22',
you would submit 'picoCTF{22}' as the flag.**

## Solucion 1

*Webshell con Python*

`ceciSolis-picoctf@webshell:~$ python`    
`Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux`
`Type "help", "copyright", "credits" or "license" for more information.`
>>> `print(int("0X3D",16))`
==`61`==
>>> 

## Solucion 2

*Usando cyberchef  https://gchq.github.io/CyberChef/#recipe=From_Base(16)To_Base(10)&input=MHgzRA

`Input: 0x3D`
`Recipe: From Base 16, To Base 10`
==`Output: 61`==

## Notas Adicionales 
La base 16 es la forma original y la base 10 es la base decimal, por eso nos da un numero decimal.


## Referencias 
https://www.datacamp.com/es/tutorial/python-data-type-conversion
https://webshell.picoctf.org/
https://gchq.github.io/CyberChef/
