
## Descripción

*The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.`ssh -p 50029 ctf-player@mimas.picoctf.net`Use password: `84b12bae`*
## Pistas

*Where can you get some letters?*
## Solución

*Webshell*
```
ceciSolis-picoctf@webshell:~$ ssh -p 50029 ctf-player@mimas.picoctf.net
The authenticity of host '[mimas.picoctf.net]:50029 ([52.15.88.75]:50029)' can't be established.
ED25519 key fingerprint is SHA256:n/hDgUtuTTF85Id7k2fxmHvb6rrLrACHNM6xLZ46AqQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[mimas.picoctf.net]:50029' (ED25519) to the list of known hosts.
ctf-player@mimas.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1016-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

SansAlpha$ .,/,?,~
bash: .,/,?,~: No such file or directory

SansAlpha$ ./*
bash: ./blargh: Is a directory

SansAlpha$ /*/???[!_]64 ~/*/????
/bin/base64: '/home/ctf-player/*/????': No such file or directory

SansAlpha$ /*/???[!_]64 ~/*/????.???
cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV9iMGQ1ZTg1NX0=

SansAlpha$  


Base64
Input:cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV9iMGQ1ZTg1NX0=
Output: picoCTF{7h15_mu171v3r53_15_m4dn355_b0d5e855}

```
picoCTF{7h15_mu171v3r53_15_m4dn355_b0d5e855}
## Notas Adicionales 

*Es un mundo sin alfabeto, con ayuda tenias que ir buscando que significaba cada simbolo, para ir adentrandote a las carpetas liego ya estabas en la bandera pero daba permiso denegado, entonces con ???? pudimos entrar, pero estaba decodifcado en base 64 solo lo convertimos y ya nos dio la bandera*

*Fue dificil como entrabas, hasta que me ayude de una página web donde explicaban paso a paso *
## Referencias 

https://www.base64decode.org/
https://medium.com/@niceselol/picoctf-2024-sansalpha-86bbdb58bde6