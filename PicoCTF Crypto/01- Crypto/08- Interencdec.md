
## Descripción

*Can you get the real meaning from this file.Download the file [here](https://artifacts.picoctf.net/c_titan/108/enc_flag).*
## Pistas

*Engaging in various decoding processes is of utmost importance*
## Solución


```
ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/108/enc_flag
--2025-05-12 00:58:15--  https://artifacts.picoctf.net/c_titan/108/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.16, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 73 [application/octet-stream]
Saving to: 'enc_flag'

enc_flag                                                   100%[========================================================================================================================================>]      73  --.-KB/s    in 0s      

2025-05-12 00:58:16 (21.1 MB/s) - 'enc_flag' saved [73/73]

ceciSolis-picoctf@webshell:~$ cat enc_flag
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyZzBOMm8yYXpZNWZRPT0nCg==
ceciSolis-picoctf@webshell:~$ echo "YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyZzBOMm8yYXpZNWZRPT0nCg==" | base64 --decode  
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ=='
ceciSolis-picoctf@webshell:~$ echo "d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ==" | base64 --decode
wpjvJAM{jhlzhy_k3jy9wa3k_h47j6k69}


```
picoCTF{caesar_d3cr9pt3d_a47c6d69}
## Notas Adicionales 

*Descargamos el archivo, le hice un cat para ver que tenia, como tenia == supuse que era base 64 lo decodifique me salio otro base 64 y luego una vez mas decodifique, me salio ya la estructura de la bandera,pero ya no era base64, entonces me fui a una pagina que ya habia estado utilizando para decodificar la ingrese y me mostro la bandera.*

*El cifrado César (o código César ) es un cifrado [de sustitución monoalfabético](https://www.dcode.fr/monoalphabetic-substitution) , donde cada letra es sustituida por otra letra situada un poco más lejos en el alfabeto (por lo tanto desplazada pero siempre igual para el mensaje cifrado dado).

La distancia de desplazamiento se elige mediante un número llamado desplazamiento, que puede ser hacia la derecha (A a B) o hacia la izquierda (B a A).

Por cada desplazamiento hacia la derecha (de +N), hay un desplazamiento equivalente hacia la izquierda (de 26-N) porque el alfabeto gira sobre sí mismo, por lo que al código César a veces se le denomina [cifrado de rotación](https://www.dcode.fr/rot-cipher) .*
## Referencias 

https://www.dcode.fr/caesar-cipher
