
## Descripción

*How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 50069`*
## Pistas

*None*

## Solución

*WebShell y Python3 *

```
ceciSolis-picoctf@webshell:~$ nc titan.picoctf.net 50069

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 00100000
Binary Number 2: 00001111

Question 1/6:
Operation 1: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00101111
Correct!

Question 2/6:
Operation 2: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 111100000
Correct!

Question 3/6:
Operation 3: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00000000
Correct!

Question 4/6:
Operation 4: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 101111
Correct!

Question 5/6:
Operation 5: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 1000000
Correct!

Question 6/6:
Operation 6: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 00000111 
Correct!
Enter the results of the last operation in hexadecimal: 0x7
Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}

```
picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}

## Notas Adicionales 

*Utilice una calculadora de operaciones binarias, para mostrar los resultados*
## Referencias 
https://webshell.picoctf.org/
https://www.rapidtables.com/calc/math/binary-calculator.html?num1=15&op=10&num2=1