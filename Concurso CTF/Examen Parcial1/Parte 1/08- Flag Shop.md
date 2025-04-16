
## Descripción

*There's a flag shop selling stuff, can you buy a flag? [Source](https://jupiter.challenges.picoctf.org/static/64e724ad327f83ad833d9c6baa072b1f/store.c). Connect with `nc jupiter.challenges.picoctf.org 4906`.*
## Pistas

*Two's compliment can do some weird things when numbers get really big!*
## Solución

*Webshell*
```
ceciSolis-picoctf@webshell:~$  nc jupiter.challenges.picoctf.org 4906 
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
1
 Balance: 1100 


Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
123123123

The final cost is: -858338996

Your current balance after transaction: 858340096

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_9c5fac9b}
Welcome to the flag exchange
We sell flags

3. Check Account Balance

4. Buy Flags

5. Exit

 Enter a menu selection
```
picoCTF{m0n3y_bag5_9c5fac9b}
## Notas Adicionales 

*Nos dan un código al revisarlo nos damos cuenta que solo verifica si el numero es mayor a 0  y cuando lo es lo multiplica por mil y por el numero de banderas a comprar, pero si es negativo el saldo aumenta en vez de bajar al momento de comprarla*
*Aqui se va intentando hasta que nos dio la bandera y teniamos bastante dinero.*
## Referencias 

https://jupiter.challenges.picoctf.org/static/64e724ad327f83ad833d9c6baa072b1f/store.c