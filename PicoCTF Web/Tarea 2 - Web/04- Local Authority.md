
## Descripción

*Can you get the flag?Go to this [website](http://saturn.picoctf.net:55696/) and see what you can discover.*

## Pistas

*How is the password checked on this website?*

## Solución

```
#Entramos al url, nos pide un usuario y una contraseña admin y password como campos, nos muestra log in failed , si inspeccionamos, podemos ver que en la fuente, en el archivo secure.js, se cuentra el usuario y la contraseña
que es:
#Secure.js
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}

#Ponemos eso en usuario y contraseña
y nos muestra la bandera
picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}
```

picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}


## Notas Adicionales 

*Solamente tuvimos que inspeccionar y llenar campos con valores que creiamos para despues sacar la bandera.*
## Referencias 

(http://saturn.picoctf.net:55696/
http://saturn.picoctf.net:60768/login.php
http://saturn.picoctf.net:55696/admin.php