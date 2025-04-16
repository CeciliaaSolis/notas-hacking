
## Descripción

*Why search for the flag when I can make a bookmarklet to print it for me?

Additional details will be available after launching your challenge instance.*

## Pistas

*A bookmarklet is a bookmark that runs JavaScript instead of loading a webpage.*
*What happens when you click a bookmarklet?*
*Web browsers have other ways to run JavaScript too.*
## Solución


```
        javascript:(function() {
            var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓÓÇ¡¥Ìí";
            var key = "picoctf";
            var decryptedFlag = "";
            for (var i = 0; i < encryptedFlag.length; i++) {
                decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
            }
            alert(decryptedFlag);
        })();
    

picoCTF{p@g3_turn3r_0c0d211f}
```
picoCTF{p@g3_turn3r_0c0d211f}
## Notas Adicionales 

*Entramos al link de la pagina, nos dio un script de javascript,lo copie, lo lleve a un compilador online de javascript, lo pegue y me dio la bandera*
## Referencias 

https://playcode.io/javascript