
## Descripción

*
- [desafío.zip](https://artifacts.picoctf.net/c_atlas/4/challenge.zip)

*`ssh -p 57591 ctf-player@atlas.picoctf.net`Using the password `83dcefb7`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!*
## Pistas


*Have you ever played hot or cold? Binary search is a bit like that.*

*You have a very limited number of guesses. Try larger jumps between numbers!*

*The program will randomly choose a new number each time you connect. You can always try again, but you should start your binary search over from the beginning - try around 500. Can you think of why?*
## Solución

*WebShell y Python3 *

```

ceciSolis-picoctf@webshell:~$ ssh -p 65471 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 400
Higher! Try again.
Enter your guess: 450
Higher! Try again.
Enter your guess: 485
Lower! Try again.
Enter your guess: 460
Higher! Try again.
Enter your guess: 470
Lower! Try again.
Enter your guess: 462
Higher! Try again.
Enter your guess: 465
Higher! Try again.
Enter your guess: 468
Lower! Try again.
Enter your guess: 466
Congratulations! You guessed the correct number: 466
Here's your flag: picoCTF{g00d_gu355_ee8225d0}
Connection to atlas.picoctf.net closed.

```
picoCTF{g00d_gu355_ee8225d0}
## Notas Adicionales 

*Solamente segui la pista de empezar en 500 y segui hasta encontrar el numero correcto *
## Referencias 

https://artifacts.picoctf.net/c_atlas/4/challenge.zip