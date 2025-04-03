
## Descripción

*Can you get the flag?

Additional details will be available after launching your challenge instance.*

*Go to this [website](http://saturn.picoctf.net:49604/) and see what you can discover.*

## Pistas

*Do you know how to modify cookies?*

## Solución

```
#Entramos al url nos muestra

Online Gradebook
Continue as guest

#Si le damos en inspeccionar,luego aplicacion en cookies, sale admin valor 1 que es true, si le damos click al boton continue as gues, nos manda a otra pagina, le damos en inspeccionar y luego aplicacion en cookies, en admin el admin es 0, le cambiamos el valor a 1 y recargamos y muestra la bandera
|   |   |   |   |   |   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|---|---|---|---|---|
|isAdmin|1|saturn.picoctf.net|/|Sesión|8||||||Medium|
picoCTF{gr4d3_A_c00k13_0d351e23}
```

picoCTF{gr4d3_A_c00k13_0d351e23}

## Notas Adicionales 

*Es modificarle el valor a los administradores, por si esta en 0 que es false, cambiarlo a 1 para que nos de permiso de ver la bandera*
## Referencias 

http://saturn.picoctf.net:49604/
http://saturn.picoctf.net:49604/admin.html
http://saturn.picoctf.net:49604/check.php