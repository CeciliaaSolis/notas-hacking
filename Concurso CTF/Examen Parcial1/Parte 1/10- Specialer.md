
## Descripción

*Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer.`ssh -p 49533 ctf-player@saturn.picoctf.net`. The password is `483e80d4`*
## Pistas

*What programs do you have access to?*
## Solución

*Webshell*
```
ceciSolis-picoctf@webshell:~$ ssh -p 49533 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:49533 ([13.59.203.175]:49533)' can't be established.
ED25519 key fingerprint is SHA256:lMXKIC17ONzyUJx7ZYBY5VSwoxCz20uq5/Nm+IhXKew.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:24: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:49533' (ED25519) to the list of known hosts.
ctf-player@saturn.picoctf.net's password: 

Specialer$ echo *
abra ala sim
Specialer$ echo /
/
Specialer$ echo */*
abra/cadabra.txt abra/cadaniel.txt ala/kazam.txt ala/mode.txt sim/city.txt sim/salabim.txt
Specialer$ echo "$(<$ala/kazam.txt)"
-bash: /kazam.txt: No such file or directory

Specialer$ echo "$(</home/ctf-player/ala/kazam.txt)"
return 0 picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_d5ef8b71}
```
picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_d5ef8b71}
## Notas Adicionales 


*Busque como podemos ver los archivos con echo y nos decia que:Google "mostrar el contenido del archivo en un script de shell"  
 **echo "$(<nombre de archivo)"** )*
 eso e hice al de kazam y nos dio la bandera.
## Referencias 

