
## Descripción

*Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/17682/` ([link](https://jupiter.challenges.picoctf.org/problem/17682/)) or http://jupiter.challenges.picoctf.org:17682*

## Pistas

*Never trust the client*

## Solución

*Fuente de código *
```
<script type="text/javascript">
  function verify() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == '706c') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_b') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == '5}') {
                  alert("Password Verified")
                  }
                }
              }
      
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }
    
  }
</script>

picoCTF{no_clients_plz_b706c5}
```
picoCTF{no_clients_plz_b706c5}
## Notas Adicionales 

*Al entrar al link, nos pide una contraseña entonces no la tenemos, entramos a inspeccionar el codigo, nos localizamos en fuentes y esta un script con la bandera, sin embargo esta en desorden para ordenarla, solo necesitamos seguir el orden del nombre del split, es split, split 2, split 3, juntamos del 1 al 8 y la bandera estara completa.*
## Referencias 
https://jupiter.challenges.picoctf.org/problem/17682/
http://jupiter.challenges.picoctf.org:17682