## Descripción
**What does this `bDNhcm5fdGgzX3IwcDM1` mean?**
**I think it has something to do with bases.**
## Pistas
**Submit your answer in our flag format. For example,**
**if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.**

## Solucion 1

*Webshell con Python*

`ceciSolis-picoctf@webshell:~$ python`
`Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux`
`Type "help", "copyright", "credits" or "license" for more information.`
`import base64`
	`cadena = base64.b64decode("bDNhcm5fdGgzX3IwcDM1")`
	`cadena`
==`b'l3arn_th3_r0p35'`==
## Solucion 2

Usando cyberchef https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=YkROaGNtNWZkR2d6WDNJd2NETTE

`Input: bDNhcm5fdGgzX3IwcDM1`
`Recipe: From Base64`
==`Output: l3arn_th3_r0p35`==
## Notas Adicionales 
Desde el usuario
```
`CeciSolis-picoctf@webshell:~$ echo "bDNhcm5fdGgzX3IwcDM1" | base64 --decode`
`l3arn_th3_r0p35Sebas115-picoctf@webshell:~$`
```
## Referencias 
https://steemit.com/utopian-io/@otakngoding/how-to-create-encoding-and-decoding-base64-using-python
https://gchq.github.io/CyberChef/
https://webshell.picoctf.org/

