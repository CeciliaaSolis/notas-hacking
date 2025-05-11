## Descripción


*Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?*
## Pistas


*How can you be sure of the redaction?*
## Solución

*Kali*
```

┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
--2025-05-11 00:28:49--  https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:24db:200:16:5ec5:2840:93a1, 2600:9000:24db:2800:16:5ec5:2840:93a1, 2600:9000:24db:5a00:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:24db:200:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34915 (34K) [application/octet-stream]
Saving to: ‘Financial_Report_for_ABC_Labs.pdf’

Financial_Report_for_ABC_ 100%[===================================>]  34.10K  --.-KB/s    in 0.1s    

2025-05-11 00:28:50 (303 KB/s) - ‘Financial_Report_for_ABC_Labs.pdf’ saved [34915/34915]

                                                                                                      
┌──(kali㉿kali)-[~]
└─$ open Financial_Report_for_ABC_Labs.pdf 


#CONTENIDO DEL ARCHIVO
Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.
Breakdown - Just painted over in MS word.
Cost Benefit Analysis
Credit Debit
This is not the flag, keep looking
Expenses from the
picoCTF{C4n_Y0u_S33_m3_fully}
Redacted document
```
picoCTF{C4n_Y0u_S33_m3_fully}
## Notas Adicionales 

*Descargamos el archivo y lo abrimos, lo seleccionamos todo y los espacios en negro que ocultaban información ,se muestran y vemos que esta la bandera en uno de esos espacios.*
## Referencias 

