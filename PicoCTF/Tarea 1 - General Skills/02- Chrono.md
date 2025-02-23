
## Descripción

*How to automate tasks to run at intervals on linux servers?Use ssh to connect to this server:*

```
Server: saturn.picoctf.net
Port: 54448
Username: picoplayer 
Password: ENAFb6zfzn
```

## Pistas

*None*

## Solución

*WebShell y Python3 *

```

ceciSolis-picoctf@webshell:~$ ssh picoplayer@saturn.picoctf.net -p 54448
The authenticity of host '[saturn.picoctf.net]:54448 ([13.59.203.175]:54448)' can't be established.
ED25519 key fingerprint is SHA256:dMTscRrUiURy7uMu5eGWwEKdd2FzqLzx6LfWhssWnNQ.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:12: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:54448' (ED25519) to the list of known hosts.
picoplayer@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

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

picoplayer@challenge:~$ cat /etc/crontab
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_1d781160}
picoplayer@challenge:~$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.

```
 picoCTF{Sch3DUL7NG_T45K3_L1NUX_1d781160}
## Notas Adicionales 

*Crontab contiene  tareas que se desean ejecutar, en este caso era la bandera, la que tenia que mostrar*

*Crontab es un archivo de texto, se trata de un archivo con un contenido especial y específicamente diseñado para que sea leído correctamente por Cron*
## Referencias
https://webshell.picoctf.org/
https://www.youtube.com/watch?v=K9H6i73ydMM
https://www.redeszone.net/tutoriales/servidores/cron-crontab-linux-programar-tareas/