## Descripción

*Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:15931/](http://mercury.picoctf.net:15931/)*
## Pistas

*Maybe you have more than 2 choices*
*Check out tools like Burpsuite to modify your requests and look at the responses*


## Solución

*Shell*
```
ceciSolis-picoctf@webshell:~$ HEAD http://mercury.picoctf.net:15931/index.php?
200 OK
Content-Type: text/html; charset=UTF-8
Client-Date: Thu, 27 Mar 2025 00:15:52 GMT
Client-Peer: 18.189.209.142:15931
Client-Response-Num: 1
Flag: picoCTF{r3j3ct_th3_du4l1ty_82880908}
```

 picoCTF{r3j3ct_th3_du4l1ty_82880908}
## Notas Adicionales 

en la pagina hay dos colores rojo y azul, uno nos manda get y otro post, entonces al checarlo con curl no muestra la llave, pero al mostrar HEAD que es el encabezado y ya por eso nos muestra la bandera.
Existen más formas de hacerla, otra forma es utilizando kali y burpsite, donde solamente ponemos el link damos click en rojo y luego azul, cambiamos post por head y nos dará de la misma manera la bandera.
## Referencias 
http://mercury.picoctf.net:15931/index.php?
http://mercury.picoctf.net:15931/index.php

