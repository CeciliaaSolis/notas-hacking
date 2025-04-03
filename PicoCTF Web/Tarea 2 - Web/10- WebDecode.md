
## Descripción

*Do you know how to use the web inspector?
Additional details will be available after launching your challenge instance.
Start searching [here](http://titan.picoctf.net:54220/) to find the flag*

## Pistas

*Use the web inspector on other files included by the web page.*

*The flag may or may not be encoded*
## Solución

```

|   |   |
|---|---|
||<!DOCTYPE html>|
||<html lang="en">|
||<head>|
||<meta charset="utf-8"/>|
||<meta content="IE=edge" http-equiv="X-UA-Compatible"/>|
||<meta content="width=device-width, initial-scale=1.0" name="viewport"/>|
||<link href="[style.css](http://titan.picoctf.net:59413/style.css)" rel="stylesheet"/>|
||<link href="[img/favicon.png](http://titan.picoctf.net:59413/img/favicon.png)" rel="shortcut icon" type="image/x-icon"/>|
||<!-- font (google) -->|
||<link href="[https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,400;0,700;1,400&amp;display=swap](https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,400;0,700;1,400&display=swap)" rel="stylesheet"/>|
||<title>|
||About me|
||</title>|
||</head>|
||<body>|
||<header>|
||<nav>|
||<div class="logo-container">|
||<a href="[index.html](http://titan.picoctf.net:59413/index.html)">|
||<img alt="logo" src="[img/binding_dark.gif](http://titan.picoctf.net:59413/img/binding_dark.gif)"/>|
||</a>|
||</div>|
||<div class="navigation-container">|
||<ul>|
||<li>|
||<a href="[index.html](http://titan.picoctf.net:59413/index.html)">|
||Home|
||</a>|
||</li>|
||<li>|
||<a href="[about.html](http://titan.picoctf.net:59413/about.html)">|
||About|
||</a>|
||</li>|
||<li>|
||<a href="[contact.html](http://titan.picoctf.net:59413/contact.html)">|
||Contact|
||</a>|
||</li>|
||</ul>|
||</div>|
||</nav>|
||</header>|
||<section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfZGYwZGE3Mjd9">|
||<h1>|
||Try inspecting the page!! You might find it there|
||</h1>|
||<!-- .about-container -->|
||</section>|
||<!-- .about -->|
||<section class="why">|
||<footer>|
||<div class="bottombar">|
||Copyright © 2023 Your_Name. All rights reserved.|
||</div>|
||</footer>|
||</section>|
||</body>|
||</html>|

#HACER ESTO
notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfZGYwZGE3Mjd9">
*Es base64, entonces con ayuda de Cyberchef lo convertimos*

Input:cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfZGYwZGE3Mjd9
Recipe: From Base64
Output:picoCTF{web_succ3ssfully_d3c0ded_df0da727}

```
picoCTF{web_succ3ssfully_d3c0ded_df0da727}
## Notas Adicionales 

*Entramos a la pagina, nos dice que tenemos que navegar, entramos a index.html, luego about.html y dice que debemos inspeccionar esa parte y si efectivamente vemos que hay algo que no se muestra y lo convertimos en cyberchef y esta la bandera, solo estaba en otra forma en base64*
## Referencias 

http://titan.picoctf.net:54220/
http://titan.picoctf.net:59413/about.html
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnQzWldKZmMzVmpZek56YzJaMWJHeDVYMlF6WXpCa1pXUmZaR1l3WkdFM01qZDk