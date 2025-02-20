
## Descripción

*Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)*

## Pistas

*On the webshell, use `ls` to see if both files are in the directory you are in*

*The `str_xor` function does not need to be reverse engineered for this challenge*
## Solución

```
ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/code.py
--2025-02-20 01:39:19--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.43, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py              100%[=====================>]   1.25K  --.-KB/s    in 0s      

2025-02-20 01:39:20 (88.1 MB/s) - 'code.py' saved [1278/1278]

ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/codebook.txt
--2025-02-20 01:39:34--  https://artifacts.picoctf.net/c/3/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.92, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt         100%[=====================>]      27  --.-KB/s    in 0s      

2025-02-20 01:39:34 (1.89 MB/s) - 'codebook.txt' saved [27/27]

ceciSolis-picoctf@webshell:~$ ls
code.py  codebook.txt
ceciSolis-picoctf@webshell:~$ python3 code.py
picoCTF{c0d3b00k_455157_197a982c}
```
picoCTF{c0d3b00k_455157_197a982c}
## Notas Adicionales 
## Referencias 
https://artifacts.picoctf.net/c/3/code.py
https://artifacts.picoctf.net/c/3/codebook.txt
https://medium.com/@matus.vaclav1/
https://webshell.picoctf.org/
