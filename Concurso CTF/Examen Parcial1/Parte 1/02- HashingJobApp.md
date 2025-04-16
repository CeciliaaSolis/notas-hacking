
## Descripción


*If you want to hash with the best, beat this test!`nc saturn.picoctf.net 63333`*

## Pistas

*You can use a commandline tool or web app to hash text*
*Press Ctrl and c on your keyboard to close your connection and return to the command prompt.*
## Solución

*Webshell*
```
ceciSolis-picoctf@webshell:~$ nc saturn.picoctf.net 62010
Please md5 hash the text between quotes, excluding the quotes: 'Babe Ruth'
Answer: 
3875acc0c1561d949c39685e96b9a4bb
3875acc0c1561d949c39685e96b9a4bb
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'mold'
Answer: 
0ad9f975892bdc82aa683146c002ffac
0ad9f975892bdc82aa683146c002ffac
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'Helen Keller'
Answer: 
c0aac1554fe46e67f218df124c318054
c0aac1554fe46e67f218df124c318054
Correct.
picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}
```
picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}
## Notas Adicionales 
*Usamos un convertidor de texto a hash md5*
*puede ser en cyberchef o en algun otro sitio web yo utilice md5hashgenerator*

## Referencias 

nc saturn.picoctf.net 63333

https://www.md5hashgenerator.com/es/