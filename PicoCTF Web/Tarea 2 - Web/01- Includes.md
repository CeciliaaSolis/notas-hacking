
## Descripción

*Can you get the flag?
Additional details will be available after launching your challenge instance.
Go to this [website](http://saturn.picoctf.net:58241/) and see what you can discover.*

## Pistas

*Is there more code than what the inspector initially shows?*

## Solución

```
http://saturn.picoctf.net:61898/

#CSS
body {
  background-color: lightblue;
}

/*  picoCTF{1nclu51v17y_1of2_  */

#JS
function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_b8f4b022}

```

*picoCTF{1nclu51v17y_1of2_f7w_2of2_b8f4b022}*
## Notas Adicionales 

*Entramos al sitio nos explica sobre que a veces no todo se incluye en el código HTML, si no que existe un apartado llamado includes, donde vienen archivos de otra parte.

Le damos en inspeccionar, luego en fuentes, están 3 archivos, donde se encuentra el style.css y script.js que están incluidos en el HTML, buscamos en cada uno, donde están las partes de la bandera, las juntamos y ya tenemos lista la bandera.*
## Referencias 

http://saturn.picoctf.net:61898/

