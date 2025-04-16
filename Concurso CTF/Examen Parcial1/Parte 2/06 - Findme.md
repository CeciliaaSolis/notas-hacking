
## Descripción

*Help us test the form by submiting the username as `test` and password as `test!`The website running [here](http://saturn.picoctf.net:63704/).*

## Pistas

*any redirections?*
## Solución


```

http://saturn.picoctf.net:63704/
Entramos a la pagina y en la descripcion del reto nos da usuario y contraseña, los ponemos y  nos manda a otra pagina llamada home 
http://saturn.picoctf.net:63704/home
donde nos dice que podemos buscar banderas

#Desde la primera pagina dimos en inspeccionar, luego en red, luego ahora si usuario y contraseña, al darle enter como dice la pista vemos a donde nos direcciona hay dos url:
http://saturn.picoctf.net:53163/next-page/id=cGljb0NURntwcm94aWVzX2Fs
http://saturn.picoctf.net:53163/next-page/id=bF90aGVfd2F5XzI1YmJhZTlhfQ==
que son los de next page, nos damos cuenta que el id es un base 64, lo que hacemos es copiar el id mandarlo a cyberchef 


CyberChef 
Input:bF90aGVfd2F5XzI1YmJhZTlhfQ==
Recipe: Frombase 64
Output: l_the_way_25bbae9a}

Input:cGljb0NURntwcm94aWVzX2Fs
Recipe: Frombase64
Output:picoCTF{proxies_al
Tenemos la bandera solo la juntamos
picoCTF{proxies_all_the_way_25bbae9a}
```
picoCTF{proxies_all_the_way_25bbae9a}
## Notas Adicionales 

## Referencias 

http://saturn.picoctf.net:63704/
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnR3Y205NGFXVnpYMkZzYkY5MGFHVmZkMkY1WHpJMVltSmhaVGxoZlE9PQ