
## Descripción

*To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.*

## Pistas

*I hear python can convert things.*

*It might help to have multiple windows open.*

## Solución

*WebShell and CyberChef*

```
ceciSolis-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 29221
Let us see how data is stored
falcon
Please give the 01100110 01100001 01101100 01100011 01101111 01101110 as a word.
...
you have 45 seconds.....
Input:
falcon
Please give me the  143 157 155 160 165 164 145 162 as a word.
Input:
computer
Please give me the 616e696d6174696f6e as a word.
Input:
animation
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_00a975ff}
```

*CyberChef*
```
Input: 01100110 01100001 01101100 01100011 01101111 01101110
Recipe: From Binary
Output: falcon 

Input: 143 157 155 160 165 164 145 162
Recipe: From Octal
Output: computer

Input: 616e696d6174696f6e
Recipe: From Hex
Output: animation
```
==picoCTF{learning_about_converting_values_00a975ff}==
## Notas Adicionales

*Primero estaba en binario la palabra, después en octal y finalmente en hexadecimal*

*Si te tardabas mas de 45 segundos se reiniciaba el juego*

## Referencias
https://webshell.picoctf.org/

https://gchq.github.io/CyberChef/#recipe=From_Binary('Space',8)&input=MDExMDAxMTAgMDExMDAwMDEgMDExMDExMDAgMDExMDAwMTEgMDExMDExMTEgMDExMDExMTA

https://gchq.github.io/CyberChef/#recipe=From_Octal('Space')&input=MTQzIDE1NyAxNTUgMTYwIDE2NSAxNjQgMTQ1IDE2Mg

https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=IDYxNmU2OTZkNjE3NDY5NmY2ZQ



