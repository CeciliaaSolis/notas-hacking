
## Descripción

*Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/60915/` ([link](https://jupiter.challenges.picoctf.org/problem/60915/)) or http://jupiter.challenges.picoctf.org:60915*

## Pistas

*What part of the website could tell you where the creator doesn't want you to look?*

## Solución

*Html, Css, Js*
```
#HTMl robots.txt
https://jupiter.challenges.picoctf.org/problem/60915/robots.txt

User-agent: *
Disallow: /8028f.html


#HTML 
https://jupiter.challenges.picoctf.org/problem/60915/8028f.html

picoCTF{ca1cu1at1ng_Mach1n3s_8028f}
```
picoCTF{ca1cu1at1ng_Mach1n3s_8028f}
## Notas Adicionales 

*La palabra robots significa que tenemos que buscar los rastreadores por lo que hay que añadirle al link robots.txt, despues nos dice la extension donde tenemos que buscar la bandera que es /8028f.html, al cargar la pagina, nos muestra la bandera correctamente.*
## Referencias 
https://jupiter.challenges.picoctf.org/problem/60915/
 http://jupiter.challenges.picoctf.org:60915