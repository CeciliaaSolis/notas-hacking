
## Descripción

*Can you win in a convincing manner against this chess bot? He won't go easy on you!You can find the challenge [here](http://verbal-sleep.picoctf.net:61344/).*
## Pistas

*Try understanding the code and how the websocket client is interacting with the server*
## Solución


```
#Es un juego de ajedrez donde compites con una maquina que no te dejara ganar

#Inspeccionamos la pagina
#Abre un socket nos permite intercambiar datos entre el cliente y el servidor sin abrir cada vez una nueva conexion.

#En consola mandamos un mensaje 
sendMessage("mate 10")
y nos responde :Haha I think you're gonna drown in 10 moves.
sendMessage("mate 10")
undefined
sendMessage("mate 100000")
undefined
sendMessage("mate -1000")
undefined
sendMessage("eval -100000")
undefined

al ir probando nos va diciendo algunas cosas, con mate no funciona tendriamos que usar eval con numero negativo y ya nos da la bandera.
#Aqui esta la bandera
¿Eh? ¿Cómo puedo estar perdiendo tanto? Renuncio. Aquí está tu bandera: picoCTF{c1i3nt_s1d3_w3b_s0ck3t5_a2a9bbe9}
```
picoCTF{c1i3nt_s1d3_w3b_s0ck3t5_a2a9bbe9}
## Notas Adicionales 

## Referencias 
http://verbal-sleep.picoctf.net:61344/
