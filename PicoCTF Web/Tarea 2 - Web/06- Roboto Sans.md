
## Descripción

*The flag is somewhere on this web application not necessarily on the website. Find it.
Additional details will be available after launching your challenge instance.*
*Check [this](http://saturn.picoctf.net:57137/) out.*

## Pistas

*None*

## Solución

```

#Entramos al url, nos dice que esta en la aplicacion web, mas no en el sitio al que nos muestra, buscamos robots.txt para ver si hay una pista
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/

#La pista la pasamos a cyberchef, para que la decodifique

Input: ZmxhZzEudHh0;
	   anMvbXlmaWxlLnR4dA==
	   oiho.bsvdaslejg

Recipe:From Base64
Output:flag1.txtjs/myfile.txt¢(hnËÝjÉ^

#Escribimos lo que nos dio el cyberchef y si nos da la bandera.
http://saturn.picoctf.net:57883/js/myfile.txt

picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}
```


picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}
## Notas Adicionales 


## Referencias 

http://saturn.picoctf.net:57137/
http://saturn.picoctf.net:57883/robots.txt
http://saturn.picoctf.net:57883/js/myfile.txt
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Wm14aFp6RXVkSGgwOw0KDQoNCmFuTXZiWGxtYVd4bExuUjRkQT09DQoNCg0Kb2loby5ic3ZkYXNsZWpnDQo&ieol=CRLF&oeol=VT