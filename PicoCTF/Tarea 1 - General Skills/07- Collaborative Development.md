
## Descripción

*My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/71/challenge.zip)*

## Pistas

*`git branch -a` will let you see available branches*

*How can file 'diffs' be brought to the main branch? Don't forget to `git config`!*

*Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.*

## Solución

*WebShell y Python3 *

```

ceciSolis-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/71/challenge.zip
--2025-02-23 04:21:25--  https://artifacts.picoctf.net/c_titan/71/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.71, 3.160.5.42, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24467 (24K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip        100%[=====================>]  23.89K  --.-KB/s    in 0.008s  

2025-02-23 04:21:25 (2.85 MB/s) - 'challenge.zip' saved [24467/24467]

ceciSolis-picoctf@webshell:~$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
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
 extracting: drop-in/.git/refs/heads/main  
   creating: drop-in/.git/refs/heads/feature/
  inflating: drop-in/.git/refs/heads/feature/part-1  
 extracting: drop-in/.git/refs/heads/feature/part-2  
 extracting: drop-in/.git/refs/heads/feature/part-3  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/77/
 extracting: drop-in/.git/objects/77/d6ceca6fe23b57d88cf16f20003e10d6715690  
   creating: drop-in/.git/objects/b9/
 extracting: drop-in/.git/objects/b9/32e8c048154a46d224cd7691c99dc8cb88164a  
   creating: drop-in/.git/objects/6c/
 extracting: drop-in/.git/objects/6c/e09adec311b859780caf89d993c58e34b53fa6  
   creating: drop-in/.git/objects/6e/
 extracting: drop-in/.git/objects/6e/17fb3a35364b4f9bb8bef8b5e6a5af2d3e7dfa  
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/e44dd37ba0c0adc3d78d0b85d699859ec8d75c  
   creating: drop-in/.git/objects/74/
 extracting: drop-in/.git/objects/74/ae5215b93a82ddf3dd37df3d4c6b5aff0a93ed  
   creating: drop-in/.git/objects/7a/
 extracting: drop-in/.git/objects/7a/b4e25c0cd108374b2275fdb1fcdf635e591833  
   creating: drop-in/.git/objects/d1/
 extracting: drop-in/.git/objects/d1/f3407cee4479c075997b497fa290ca636fe258  
   creating: drop-in/.git/objects/b4/
 extracting: drop-in/.git/objects/b4/612c914d8461d1b1a50652cc303b76813ee142  
 extracting: drop-in/.git/objects/b4/5df8ce6725e05ed8f45745793f91c26f6529dc  
   creating: drop-in/.git/objects/59/
 extracting: drop-in/.git/objects/59/d9bf3f55055654fda549be87499374805f28e3  
   creating: drop-in/.git/objects/5c/
 extracting: drop-in/.git/objects/5c/6d493ac583a95117d3a70eb5b10d9d76991c48  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/main  
   creating: drop-in/.git/logs/refs/heads/feature/
  inflating: drop-in/.git/logs/refs/heads/feature/part-1  
  inflating: drop-in/.git/logs/refs/heads/feature/part-2  
  inflating: drop-in/.git/logs/refs/heads/feature/part-3  
  inflating: drop-in/flag.py         
ceciSolis-picoctf@webshell:~$ cd drop-in
ceciSolis-picoctf@webshell:~/drop-in$ git branch -a 
ceciSolis-picoctf@webshell:~/drop-in$ git checkout feature/part-1
Switched to branch 'feature/part-1'
ceciSolis-picoctf@webshell:~/drop-in$ git log
ceciSolis-picoctf@webshell:~/drop-in$ cat flag.py                
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')ceciSolis-picoctf@webshell:~/drop-in$  git log feature/part-2
ceciSolis-picoctf@webshell:~/drop-in$ git checkout feature/part-2
Switched to branch 'feature/part-2'
ceciSolis-picoctf@webshell:~/drop-in$ git log
ceciSolis-picoctf@webshell:~/drop-in$ cat flag.py
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')ceciSolis-picoctf@webshell:~/drop-in$ git checkout feature/part-3
Switched to branch 'feature/part-3'
ceciSolis-picoctf@webshell:~/drop-in$ git log
ceciSolis-picoctf@webshell:~/drop-in$ cat flag.py
print("Printing the flag...")

print("w0rk_4c24302f}")

```

picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_4c24302f}
## Notas Adicionales 
## Referencias 
https://hackmd.io/@mochimamrifai/BkmfAZEUR
https://webshell.picoctf.org/
