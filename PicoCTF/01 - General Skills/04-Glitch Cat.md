## Descripción

**Our flag printing service has started glitching!**
**Additional details will be available after launching your challenge instance.**
## Pistas

°**This challenge launches an instance on demand.**  
**Its current status is: `RUNNING`**
**Instance Time Remaining:**

°**ASCII is one of the most common encodings used in programming**.

°**We know that the glitch output is valid Python, somehow!**
**Press Ctrl and c on your keyboard to close your connection and return to the command prompt.**
## Solucion 1

*Con Kali Linux en Maquina Virtual*

`┌──(kali㉿kali)-[~/Downloads]`
`└─$ nc saturn.picoctf.net 50851`
`'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'`
                                                                             
`┌──(kali㉿kali)-[~/Downloads]`
`└─$ python3`
`Python 3.12.7 (main, Nov  8 2024, 17:55:36) [GCC 14.2.0] on linux`
`Type "help", "copyright", "credits" or "license" for more information.`
>>> `'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'`
==`'picoCTF{gl17ch_m3_n07_9c42a45d}'`==

## Solucion 2

*Usando cyberchef https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=KyBjaHIoMHgzOSkgKyBjaHIoMHg2MykgKyBjaHIoMHgzNCkgKyBjaHIoMHgzMikgKyBjaHIoMHg2MSkgKyBjaHIoMHgzNCkgKyBjaHIoMHgzNSkgKyBjaHIoMHg2NCk&oeol=FF 

`Input:+ chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64)`
`Recipe: From Hex`
==`Output:9c42a45d`==

## Notas Adicionales 


## Referencias 
https://medium.com/@elitere.solutions20/picoctf-glitch-cat-b89b9f50afdb
https://gchq.github.io/CyberChef/

