
## Descripción
*What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/68/challenge.zip)*

## Pistas

*The `cat` command will let you read a file, but that won't help you here!*

*Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).*

*When committing a file with git, a message can (and should) be included.*

## Solución

*WebShell y Python3 *

```
ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/68/challenge.zip
--2025-02-21 01:51:14--  https://artifacts.picoctf.net/c_titan/68/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.71, 3.160.5.93, 3.160.5.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17738 (17K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                              100%[=======================================================================================>]  17.32K  --.-KB/s    in 0.007s  

2025-02-21 01:51:14 (2.51 MB/s) - 'challenge.zip' saved [17738/17738]

ceciSolis-picoctf@webshell:~$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
  inflating: drop-in/message.txt     
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
   creating: drop-in/.git/objects/25/
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
   creating: drop-in/.git/objects/70/
 extracting: drop-in/.git/objects/70/5ff639b7846418603a3272ab54536e01e3dc43  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
ceciSolis-picoctf@webshell:~$ ls  
challenge.zip  drop-in
ceciSolis-picoctf@webshell:~$ cd  drop-in
ceciSolis-picoctf@webshell:~/drop-in$ git init .
Reinitialized existing Git repository in /home/ceciSolis-picoctf/drop-in/.git/
ceciSolis-picoctf@webshell:~/drop-in$ ls
message.txt
ceciSolis-picoctf@webshell:~/drop-in$ cat message.txt
This is what I was working on, but I'd need to look at my commit history to know why...ceciSolis-picoctf@webshell:~/drop-in$ cd .git
ceciSolis-picoctf@webshell:~/drop-in/.git$ ls
COMMIT_EDITMSG  HEAD  branches  config  description  hooks  index  info  logs  objects  refs
ceciSolis-picoctf@webshell:~/drop-in/.git$ cd COMMIT_EDITMSG
-bash: cd: COMMIT_EDITMSG: Not a directory
ceciSolis-picoctf@webshell:~/drop-in/.git$ cat COMMIT_EDITMSG
picoCTF{t1m3m@ch1n3_b476ca06}
```
picoCTF{t1m3m@ch1n3_b476ca06}

## Solución 2

```

ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/68/challenge.zip 
--2025-02-21 02:01:10--  https://artifacts.picoctf.net/c_titan/68/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.93, 3.160.5.71, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.93|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17738 (17K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                              100%[=======================================================================================>]  17.32K  --.-KB/s    in 0.006s  

2025-02-21 02:01:10 (2.91 MB/s) - 'challenge.zip' saved [17738/17738]

ceciSolis-picoctf@webshell:~$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
  inflating: drop-in/message.txt     
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
   creating: drop-in/.git/objects/25/
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
   creating: drop-in/.git/objects/70/
 extracting: drop-in/.git/objects/70/5ff639b7846418603a3272ab54536e01e3dc43  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
ceciSolis-picoctf@webshell:~$ cd drop-in/
ceciSolis-picoctf@webshell:~/drop-in$ git log

commit 705ff639b7846418603a3272ab54536e01e3dc43 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:36 2024 +0000

    picoCTF{t1m3m@ch1n3_b476ca06}
ceciSolis-picoctf@webshell:~/drop-in$ 
```
picoCTF{t1m3m@ch1n3_b476ca06}
## Notas Adicionales 

*Solo necesitabamos entrar a git, para que mostrarara el ultimo commit y despues mostraria la bandera, la primera solucion la hice con ayuda de cat, aunque no se permitia del todo, la segunda solucion si es más correcta, pero ambas nos dan correctamente la bandera*
## Referencias 
https://artifacts.picoctf.net/c_titan/68/challenge.zip
https://webshell.picoctf.org/
https://github.com/noamgariani11/picoCTF-2024-Writeup/blob/main/General%20Skills/Time-Machine.md
https://primer.picoctf.org/#_git_version_control
