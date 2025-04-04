
## Descripción

*Using a Secure Shell (SSH) is going to be pretty important.Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `57947` to get the flag?You'll also need the password `f3b61b38`. If asked, accept the fingerprint with `yes`.If your device doesn't have a shell, you can use: [https://webshell.picoctf.org](https://webshell.picoctf.org/)If you're not sure what a shell is, check out our Primer: [https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell)*

## Pistas

*[https://linux.die.net/man/1/ssh](https://linux.die.net/man/1/ssh)
You can try logging in 'as' someone with `<user>`@titan.picoctf.net
How could you specify the port?
Remember, passwords are hidden when typed into the shell*

## Solución

*WebShell*
```
ceciSolis-picoctf@webshell:~$ ssh ctf-player@titan.picoctf.net -p 57947
The authenticity of host '[titan.picoctf.net]:57947 ([3.139.174.234]:57947)' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:57947' (ED25519) to the list of known hosts.
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_3e293eea}
Connection to titan.picoctf.net closed.
ceciSolis-picoctf@webshell:~$ exit
logout
```
picoCTF{s3cur3_c0nn3ct10n_3e293eea}
## Notas Adicionales 

## Referencias 
https://webshell.picoctf.org/

