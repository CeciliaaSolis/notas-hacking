
## Descripción

*In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values)*

## Pistas

*Bits are expensive, I used only a little bit over 100 to save money*


## Solución

```
┌──(kali㉿kali)-[~  
└─$ wget [https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values](https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values)  
--2025-05-22 14:19:45--  [https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values](https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values)  
Resolving [mercury.picoctf.net](http://mercury.picoctf.net/) ([mercury.picoctf.net](http://mercury.picoctf.net/))... 18.189.209.142  
Connecting to [mercury.picoctf.net](http://mercury.picoctf.net/) ([mercury.picoctf.net](http://mercury.picoctf.net/))|18.189.209.142|:443... connected.  
HTTP request sent, awaiting response... 200 OK  
Length: 205 [application/octet-stream]  
Saving to: ‘values’  
  
values                  100%[============================>]     205  --.-KB/s    in 0s        
  
2025-05-22 14:19:45 (377 MB/s) - ‘values’ saved [205/205]  
  
                                                                                               
┌──(kali㉿kali)-[~]  
└─$ ls                                          
values  
                                                                                               
┌──(kali㉿kali)-[~]  
└─$ cat values                                  
Decrypt my super sick RSA:  
c: 240986837130071017759137533082982207147971245672412893755780400885108149004760496  
n: 831416828080417866340504968188990032810316193533653516022175784399720141076262857  

e: 65537

  

┌──(kali㉿kali)-[~]  
└─$ python

  

>>> c = 240986837130071017759137533082982207147971245672412893755780400885108149004760496

>>> n = 831416828080417866340504968188990032810316193533653516022175784399720141076262857  
>>> e = 65537  
>>> d = pow(e, -1, tn)  
>>> m = pow(c, d, n)  
>>> m  
13016382529449106065927291425342535437996222135352905256639592405461024281868413

>>> bytes.fromhex(hex(m)[2:]).decode()  
'picoCTF{sma11_N_n0_g0od_23540368}'
```

## Notas Adicionales 

*descargamos, vemos lo que contiene, en python declaramos las variables, insertamos la formula ahora como nos dio un numero hexadecimal lo decodificamos y nos dio la bandera.*

## Referencias 
