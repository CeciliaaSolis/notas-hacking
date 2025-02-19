## Descripción
**Can you convert the number 42** 
**(base 10) to binary (base 2)?**
## Pistas
**Submit your answer in our competition's flag format.**
**For example, if your answer was '11111',** 
**you would submit 'picoCTF{11111}' as the flag.**

## Solucion 1

*Webshell con Python*

```
ceciSolis-picoctf@webshell:~$ python
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(42)
'0b101010'
>>> 
```
## Solucion 2

*Usando cyberchef https://gchq.github.io/CyberChef/#recipe=From_Base(10)To_Base(2)&input=NDI*

```
Input: 42
Recipe: From base, To base
Output: 101010

```


## Solución 3
```
ceciSolis-picoctf@webshell:~$ python
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
bin(42)[2:]
'101010'
```


## Notas Adicionales 
Tambien se puede realizar usando primero el decimal y luego que lo convierta a binario

```
Input: 42
Recipe: From Decimal, To Binary
Output: 101010

```
## Referencias 
https://gchq.github.io/CyberChef/
https://webshell.picoctf.org/

