
## Descripción

*The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/13594/` ([link](https://jupiter.challenges.picoctf.org/problem/13594/)) or http://jupiter.challenges.picoctf.org:13594*

## Pistas

*What part of the website could tell you where the creator doesn't want you to look?*

## Solución

*Modificar las cookies*
```
#HTMl robots.txt
https://jupiter.challenges.picoctf.org/problem/60915/robots.txt

User-agent: *
Disallow: /8028f.html
|   |   |   |   |   |   |   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
|admin|False|jupiter.challenges.picoctf.org|/|Sesión|10||||||Medium||

#Se cambia a true
|   |   |   |   |   |   |   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
|admin|False|jupiter.challenges.picoctf.org|/|Sesión|10||||||Medium||

#Recargamos la pagina y sale:
picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}
```
picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}
## Notas Adicionales 

*Al entrar al link, intentamos logearnos, no funciona, entonces vamos a buscar la raiz del problema,lo que haremos es inspeccionar la página, para despues localizar el apartado de localización, buscamos las cookies y estara un apartado de admin, ese apartado esta con valor falso, sim embargo aqui debemos cambiarlo a true, y finalmente recargamos la página, mostrara la bandera.*
## Referencias 
https://jupiter.challenges.picoctf.org/problem/13594/
http://jupiter.challenges.picoctf.org:13594
https://jupiter.challenges.picoctf.org/problem/13594/flag
