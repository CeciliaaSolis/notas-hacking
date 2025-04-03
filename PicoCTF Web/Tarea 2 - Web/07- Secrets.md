
## Descripción

*We have several pages hidden. Can you find the one with the flag?
Additional details will be available after launching your challenge instance.*

*El sitio web se está ejecutando [aquí](http://saturn.picoctf.net:58138/) .*

## Pistas

*folders folders folders*

## Solución

```

#SECRET
<!DOCTYPE html>
<html>
  <head>
    <title></title>
    <link rel="stylesheet" href="hidden/file.css" />
  </head>

  <body>
    <h1>Finally. You almost found me. you are doing well</h1>
    <img src="https://media1.tenor.com/images/0a6aff9f825af62c05adfbd75039cc7b/tenor.gif?itemid=4648337" alt="Something Like That GIF - Andy Parksandrecreation Wtf GIFs" style="max-width: 833px; background-color: rgb(151, 121, 85);" width="833" height="937.125">
  </body>
</html>


#HIDDEN

<!DOCTYPE html>
<html>
  <head>
    <title>LOGIN</title>
    <!-- css -->
    <link href="superhidden/login.css" rel="stylesheet" />
  </head>
  <body>

#SUPERHIDDEN
<!DOCTYPE html>
<html>
  <head>
    <title></title>
    <link rel="stylesheet" href="mycss.css" />
  </head>

  <body>
    <h1>Finally. You found me. But can you see me</h1>
    <h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_790d2615}</h3>
  </body>
</html>

```

picoCTF{succ3ss_@h3n1c@10n_790d2615}

## Notas Adicionales 

*Como la pista dice que son varios folders entonces, inspeccionamos el primer url nos dice que hay algo en /secrets
lo buscamos y luego nos dice hidden, le seguimos y luego nos muestra en el html  superhidden, lo buscamos y en ese html se encuentra la bandera*

## Referencias 

http://saturn.picoctf.net:58138/
http://saturn.picoctf.net:58138/secret/
http://saturn.picoctf.net:58138/secret/hidden/
http://saturn.picoctf.net:58138/secret/hidden/superhidden/