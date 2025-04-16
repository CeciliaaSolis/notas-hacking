
## Descripción

*Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?You can access the Cookie Monster [here](http://verbal-sleep.picoctf.net:56241/) and good luck*


## Pistas

*Sometimes, the most important information is hidden in plain sight. Have you checked all parts of the webpage?*

*Cookies aren't just for eating - they're also used in web technologies!*

*Web browsers often have tools that can help you inspect various aspects of a webpage, including things you can't see directly.*
## Solución


```

|   |   |   |   |   |   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|---|---|---|---|---|
|secret_recipe|cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzZDMkZCN0YzfQ%3D%3D|verbal-sleep.picoctf.net|/|2025-04-12T23:29:08.752Z|81||||||Medium|

CyberChef
Input:cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzZDMkZCN0YzfQ==
Recipe: From Base64
Output:picoCTF{c00k1e_m0nster_l0ves_c00kies_6C2FB7F3}
```
picoCTF{c00k1e_m0nster_l0ves_c00kies_6C2FB7F3}
## Notas Adicionales 

*Entramos al url, nos vamos a inspeccionar, aplicaciones, cookies, accedemos al url y vemos un nombre de secret recipe, copiamos el valor, lo llevamos a cyberchef a decodificar en base 64 y nos da la bandera*
## Referencias 

http://verbal-sleep.picoctf.net:56241/
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnRqTURCck1XVmZiVEJ1YzNSbGNsOXNNSFpsYzE5ak1EQnJhV1Z6WHpaRE1rWkNOMFl6ZlE9PQ