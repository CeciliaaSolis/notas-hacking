
## Descripción

*Can you login to this website?
Additional details will be available after launching your challenge instance.*

## Pistas

*`admin` is the user you want to login as.*

## Solución

```

Indice HTML
<!-- Here's the first part of the
flag: picoCTF{t

CSS
/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */

JS.
/* How can I keep Google from indexing my website? */
http://mercury.picoctf.net:5080/robots.txt
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?

#Seguimos pista
http://mercury.picoctf.net:5080/.htaccess
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.

#Seguimos pista

http://mercury.picoctf.net:5080/.DS_Store
Congrats! You completed the scavenger hunt.
Part 5: _35844447}
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_35844447}
```

picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_35844447}

## Notas Adicionales 

Al darle click en What en el sitio, nos mandaba varias cosas que usaba, entonces le dimos inspeccionar, luego fuentes, en el html encontramos la primera parte, en css la segunda, en l tercera en javascripts nos da una pista si no quiero que google indexe mi sitio web entonces voy a robots.txt,donde se va encontrar la siguiente parte, luego la pista de ahi dice que esta en un servidor apache que es htaccess dond estará la otra bandera, finalmente dice la pista que es donde se almacena un monton de informacion que es el ds_store , juntamos las 5 partes y obtenemos la bandera.
## Referencias 

http://mercury.picoctf.net:5080/robots.txt
http://mercury.picoctf.net:5080/.htaccess
http://mercury.picoctf.net:5080/.DS_Store