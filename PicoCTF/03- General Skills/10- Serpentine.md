
## Descripción

*Find the flag in the Python script![Download Python script](https://artifacts.picoctf.net/c/36/serpentine.py)*

## Pistas

*Try running the script and see what happens*

*In the webshell, try examining the script with a text editor like `nano`*

*To exit `nano`, press Ctrl and x and follow the on-screen prompts.*

*The `str_xor` function does not need to be reverse engineered for this challenge.*

## Solución

*WebShell, Nano, Python3*
```
ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/36/serpentine.py
--2025-02-20 03:04:00--  https://artifacts.picoctf.net/c/36/serpentine.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.128, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2550 (2.5K) [application/octet-stream]
Saving to: 'serpentine.py'

serpentine.py        100%[=====================>]   2.49K  --.-KB/s    in 0s      

2025-02-20 03:04:00 (1.91 GB/s) - 'serpentine.py' saved [2550/2550]

ceciSolis-picoctf@webshell:~$ nano serpentine.py 

ceciSolis-picoctf@webshell:~$ python3 serpentine.py 

    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~

Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b

Oops! I must have misplaced the print_flag function! Check my source code!


picoCTF{7h3_r04d_l355_7r4v3l3d_aa2340b2}
```
picoCTF{7h3_r04d_l355_7r4v3l3d_aa2340b2}
## Notas Adicionales 

*En nano serpentine, se modifco para que al poner b, llamara la funcion donde estaba la bandera, ya que por eso no la imprimiia, se modifica, se guarda y ahora si se ejecuta y muestra la bandera*
## Referencias 
https://artifacts.picoctf.net/c/36/serpentine.py
https://cybernotes.uk/picoctf-serpentine/
https://webshell.picoctf.org/
