
## Descripción

*I found this cipher in an old book. Can you figure out what it says? Connect with `nc jupiter.challenges.picoctf.org 5726`.*
## Pistas

*There are tools that make this easy.*

*Perhaps looking at history will help*
## Solución


```

ceciSolis-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 5726.
nc: port number invalid: 5726.
ceciSolis-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 5726 
Encrypted message:
Ne iy nytkwpsznyg nth it mtsztcy vjzprj zfzjy rkhpibj nrkitt ltc tnnygy ysee itd tte cxjltk

Ifrosr tnj noawde uk siyyzre, yse Bnretèwp Cousex mls hjpn xjtnbjytki xatd eisjd

Iz bls lfwskqj azycihzeej yz Brftsk ip Volpnèxj ls oy hay tcimnyarqj dkxnrogpd os 1553 my Mnzvgs Mazytszf Merqlsu ny hox moup Wa inqrg ipl. Ynr. Gotgat Gltzndtg Gplrfdo 

Ltc tnj tmvqpmkseaznzn uk ehox nivmpr g ylbrj ts ltcmki my yqtdosr tnj wocjc hgqq ol fy oxitngwj arusahje fuw ln guaaxjytrd catizm tzxbkw zf vqlckx hizm ceyupcz yz tnj fpvjc hgqqpohzCZK{m311a50_0x_a1rn3x3_h1ah3x6kp60egf}

Ehk ktryy herq-ooizxetypd jjdcxnatoty ol f aordllvmlbkytc inahkw socjgex, bls sfoe gwzuti 1467 my Rjzn Hfetoxea Gqmexyt.

Tnj Gimjyèrk Htpnjc iy ysexjqoxj dosjeisjd cgqwej yse Gqmexyt Doxn ox Fwbkwei Inahkw.

Tn 1508, Ptsatsps Zwttnjxiax tnbjytki ehk xz-cgqwej ylbaql rkhea (g rltxni ol xsilypd gqahggpty) ysaz bzuri wazjc bk f nroytcgq nosuznkse ol yse Bnretèwp Cousex.

Gplrfdo’y xpcuso butvlky lpvjlrki tn 1555 gx l cuseitzltoty ol yse lncsz. Yse rthex mllbjd ol yse gqahggpty fce tth snnqtki cemzwaxqj, bay ehk fwpnfmezx lnj yse osoed qptzjcs gwp mocpd hd xegsd ol f xnkrznoh vee usrgxp, wnnnh ify bk itfljcety hizm paim noxwpsvtydkse



It is interesting how in history people often receive credit for things they did not create

During the course of history, the Vigenère Cipher has been reinvented many times

It was falsely attributed to Blaise de Vigenère as it was originally described in 1553 by Giovan Battista Bellaso in his book La cifra del. Sig. Giovan Battista Bellaso 

For the implementation of this cipher a table is formed by sliding the lower half of an ordinary alphabet for an apparently random number of places with respect to the upper halfpicoCTF{b311a50_0r_v1gn3r3_c1ph3r6fe60eaa}
```
picoCTF{b311a50_0r_v1gn3r3_c1ph3r6fe60eaa}
## Notas Adicionales 


*Me conecte a donde me decia, me salio un texto que no se entendia, busque donde podia ver que tipo de codigo era en esta pagina:https://www.dcode.fr/cipher-identifier,  y me salio que era de tipo vigenere, entre a otra pagina que fue; https://www.guballa.de/vigenere-solver  para decodificarlo y me mostro todo el texto en ingles y la bandera ahi estaba.*

*El cifrado Vigenère es un método de cifrado polialfabético que utiliza una clave para desplazar cada letra del mensaje en una posición diferente, basándose en un cifrado César diferente para cada letra  A diferencia del cifrado César, que utiliza un solo desplazamiento, el cifrado Vigenère utiliza una clave para determinar el desplazamiento de cada letra, lo que lo hace más seguro.*
## Referencias 

https://www.google.com/search?q=vigenere+cipher+que+es&sca_esv=244132eb41020ebb&rlz=1C1GCEU_esMX1161MX1161&sxsrf=AHTn8zrRvPMIQJCsrjOZTTwsrqR5tIcQfA%3A1747008396770&ei=jDshaM_oLsbjwN4PxMqEwAI&ved=0ahUKEwjP3qK30ZyNAxXGMdAFHUQlASgQ4dUDCBA&uact=5&oq=vigenere+cipher+que+es&gs_lp=Egxnd3Mtd2l6LXNlcnAiFnZpZ2VuZXJlIGNpcGhlciBxdWUgZXMyCBAAGIAEGMsBMgYQABgWGB4yBRAAGO8FMgUQABjvBTIFEAAY7wUyBRAAGO8FMgUQABjvBUiFDFCcAVjnCnABeACQAQCYAeQCoAG9B6oBBzAuMy4xLjG4AQPIAQD4AQGYAgWgAtkGwgIKEAAYsAMY1gQYR8ICDRAAGIAEGLADGEMYigXCAgoQABiABBhDGIoFmAMAiAYBkAYKkgcHMS4yLjEuMaAH7RqyBwcwLjIuMS4xuAfNBg&sclient=gws-wiz-serp