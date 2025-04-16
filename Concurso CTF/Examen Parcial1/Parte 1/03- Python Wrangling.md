
## Descripción

*Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/ende.py) using [this password](https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/pw.txt) to get [the flag](https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/flag.txt.en)?*

## Pistas

*Get the Python script accessible in your shell by entering the following command in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/ende.py`*

*`$ man python`*
## Solución

*Webshell*
```
ceciSolis-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/ende.py
--2025-04-12 22:09:44--  https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/ende.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1328 (1.3K) [application/octet-stream]
Saving to: 'ende.py'

ende.py                      100%[=============================================>]   1.30K  --.-KB/s    in 0s      

2025-04-12 22:09:44 (529 MB/s) - 'ende.py' saved [1328/1328]

ceciSolis-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/pw.txt
--2025-04-12 22:09:59--  https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/pw.txt
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 33 [application/octet-stream]
Saving to: 'pw.txt'

pw.txt                       100%[=============================================>]      33  --.-KB/s    in 0s      

2025-04-12 22:09:59 (26.5 MB/s) - 'pw.txt' saved [33/33]

ceciSolis-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/flag.txt.en
--2025-04-12 22:10:10--  https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/flag.txt.en
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 140 [application/octet-stream]
Saving to: 'flag.txt.en'

flag.txt.en                  100%[=============================================>]     140  --.-KB/s    in 0s      

2025-04-12 22:10:10 (96.3 MB/s) - 'flag.txt.en' saved [140/140]

ceciSolis-picoctf@webshell:~$ python ende.py -h
Usage: ende.py (-e/-d) [file]
Examples:
  To decrypt a file named 'pole.txt', do: '$ python ende.py -d pole.txt'

ceciSolis-picoctf@webshell:~$ python ende.py -d flag.txt.en
Please enter the password:68f88f9368f88f9368f88f9368f88f93
picoCTF{4p0110_1n_7h3_h0us3_68f88f93}
```
picoCTF{4p0110_1n_7h3_h0us3_68f88f93}
## Notas Adicionales 

*Descargamos el archivo,la contraseña y la bandera*
*Despues ejecuntamos el scprit nos dara una pista de lo que debemos poner*
*Lo ingresamos, abrimos el archivo de la contraseña, la pegamos,damos enter y muestra la bandera*
## Referencias 

https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/ende.py
https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/pw.txt
https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/flag.txt.en
