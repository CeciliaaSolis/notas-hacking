## Descripción

*A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/a917f567b9cc0f1a730a7801b309955df4d2234a8114326857b9759e9e5d0453/myNetworkTraffic.pcap) and try to get the flag.*
## Pistas

*Filter your packets to narrow down your search.*
*Attacks were done in timely manner.*
*Time is essential*
## Solución

*Kali*
```
ceciSolis-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_verbal_sleep/a917f567b9cc0f1a730a7801b309955df4d2234a8114326857b9759e9e5d0453/myNetworkTraffic.pcap
--2025-05-11 21:40:33--  https://challenge-files.picoctf.net/c_verbal_sleep/a917f567b9cc0f1a730a7801b309955df4d2234a8114326857b9759e9e5d0453/myNetworkTraffic.pcap
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.95, 3.160.5.64, 3.160.5.40, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1452 (1.4K) [application/octet-stream]
Saving to: 'myNetworkTraffic.pcap.1'

myNetworkTraffic.pcap.1                                    100%[=======================================================================================================================================>]   1.42K  --.-KB/s    in 0s      

2025-05-11 21:40:33 (710 MB/s) - 'myNetworkTraffic.pcap.1' saved [1452/1452]

ceciSolis-picoctf@webshell:~$ strings myNetworkTraffic.pcap.1
ezF0X3c0cw==
cGljb0NURg==
bnRfdGg0dA==
Yt8ksMM=
3psv5C4=
YQEFzIU=
YmhfNHJfOQ==
a23/UbI=
TOGSGg4=
bpzQ0R8=
fQ==
nfu4Vww=
J4auZMY=
ePRXDio=
fjIzQwk=
XThGxuE=
ckBkZLk=
CJr4oDk=
BgJLB0c=
XzM0c3lfdA==
NTlmNTBkMw==
dgV9v0s=

CYBERCHEF:
INPUT:cGljb0NURg==

bnRfdGg0dA==

3psv5C4=

YmhfNHJfOQ==

XzM0c3lfdA==

NTlmNTBkMw==

dgV9v0s=

RECIPE:FROMBASE64

OUTPUT:{1t_w4spicoCTFnt_th4tÞ/ä.bh_4r_9_34sy_t59f50d3v}¿K
```
picoCTF1t_w4snt_th4t_34sy_tbh_4r_959f50d3}
## Notas Adicionales 

*Lo que hice fue descargar el archivo, luego con strings para ver que tenia, me di cuenta que parecia algo codificado, me fui a cyberchef puse la lista que me daba y fueron saliendo partes de la bandera, en orden desacomodado, las ordene y obtuve la bandera.*

## Referencias 

https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=ZXpGMFgzYzBjdz09DQoNCmNHbGpiME5VUmc9PQ0KDQpiblJmZEdnMGRBPT0NCg0KM3BzdjVDND0NCg0KWW1oZk5ISmZPUT09DQoNClh6TTBjM2xmZEE9PQ0KDQpOVGxtTlRCa013PT0NCg0KZGdWOXYwcz0&ieol=CRLF&oeol=NEL