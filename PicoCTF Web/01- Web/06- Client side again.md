
## Descripción

*Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/60786/` ([link](https://jupiter.challenges.picoctf.org/problem/60786/)) or http://jupiter.challenges.picoctf.org:60786*

## Pistas

*What is obfuscation?*
## Solución

*Inspeccionar*
```
#FUENTES
<html>
    <head>
        <title>Secure Login Portal V2.0</title>
    </head>
    <body background="barbed_wire.jpeg">
        <!-- standard MD5 implementation -->
        <script type="text/javascript" src="md5.js"></script>
        <script type="text/javascript">
            var _0x5a46 = ['f49bf}', '_again_e', 'this', 'Password\x20Verified', 'Incorrect\x20password', 'getElementById', 'value', 'substring', 'picoCTF{', 'not_this'];
            (function(_0x4bd822, _0x2bd6f7) {
                var _0xb4bdb3 = function(_0x1d68f6) {
                    while (--_0x1d68f6) {
                        _0x4bd822['push'](_0x4bd822['shift']());
                    }
                };
                _0xb4bdb3(++_0x2bd6f7);
            }(_0x5a46, 0x1b3));
            var _0x4b5b = function(_0x2d8f05, _0x4b81bb) {
                _0x2d8f05 = _0x2d8f05 - 0x0;
                var _0x4d74cb = _0x5a46[_0x2d8f05];
                return _0x4d74cb;
            };
            function verify() {
                checkpass = document[_0x4b5b('0x0')]('pass')[_0x4b5b('0x1')];
                split = 0x4;
                if (checkpass[_0x4b5b('0x2')](0x0, split * 0x2) == _0x4b5b('0x3')) {
                    if (checkpass[_0x4b5b('0x2')](0x7, 0x9) == '{n') {
                        if (checkpass[_0x4b5b('0x2')](split * 0x2, split * 0x2 * 0x2) == _0x4b5b('0x4')) {
                            if (checkpass[_0x4b5b('0x2')](0x3, 0x6) == 'oCT') {
                                if (checkpass[_0x4b5b('0x2')](split * 0x3 * 0x2, split * 0x4 * 0x2) == _0x4b5b('0x5')) {
                                    if (checkpass['substring'](0x6, 0xb) == 'F{not') {
                                        if (checkpass[_0x4b5b('0x2')](split * 0x2 * 0x2, split * 0x3 * 0x2) == _0x4b5b('0x6')) {
                                            if (checkpass[_0x4b5b('0x2')](0xc, 0x10) == _0x4b5b('0x7')) {
                                                alert(_0x4b5b('0x8'));
                                            }
                                        }
                                    }
                                }
                            }
                        }
                    }
                } else {
                    alert(_0x4b5b('0x9'));
                }
            }
        </script>
        <div style="position:relative; padding:5px;top:50px; left:38%; width:350px; height:140px; background-color:gray">
            <div style="text-align:center">
                <p>New and Improved Login</p>
                <p>Enter valid credentials to proceed</p>
                <form action="index.html" method="post">
                    <input type="password" id="pass" size="8"/>
                    <br/>
                    <input type="submit" value="verify" onclick="verify(); return false;"/>
                </form>
            </div>
        </div>
    </body>
</html>

#CONSOLE
_0x4b5b('0x1') -> VALUE
 _0x4b5b('0x3') -> picoCTF{
 (0x7, 0x9) -> '{n'
 _0x4b5b('0x4') -> not_this
 (0x3, 0x6) ->  'oCT'
 _0x4b5b('0x5') -> f49bf}
 (0x6, 0xb) -> 'F{not'
 _0x4b5b('0x6') -> _again_e
 

picoCTF{not_this_again_ef49bf}
```
picoCTF{not_this_again_ef49bf}
## Notas Adicionales 

*Abrimos el link despues vemos que necesitamos logear,como no tenemos la credencial valida, entonces nos vamos a inspeccionar, vamos a fuente, vemos el codigo un poco desordenado en la izquierda inferior damos clic a {} para que muestre el código con estilo, despues nos damos cuenta que es similar al dont use client, vemos que hay splits, sin embargo estan en otro formato, lo que hacemos es seguir la pista el formato en el que estan en ofuscacion que es para proteger los datos que no esten a simple vista, entonces en  la misma consola, podemos revertirlos, para encontrar la bandera,vamos uno por uno hasta que obtenemos todas las partes de la bandera y simplemente las unimos.*

## Referencias 
https://jupiter.challenges.picoctf.org/problem/60786/ 
http://jupiter.challenges.picoctf.org:60786
https://digital.ai/es/glossary/what-is-code-obfuscation/