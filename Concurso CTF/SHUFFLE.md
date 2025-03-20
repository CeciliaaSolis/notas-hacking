
def revertir_desorden(texto):

    texto = list(texto)  # Convertimos la cadena en una lista para poder modificarla

    resultado = [''] * len(texto)  # Lista vacía para la cadena restaurada

    # Iteramos sobre la cadena en bloques de 3 caracteres

    for i in range(0, len(texto), 3):

        if i+2 < len(texto):  # Aseguramos que el bloque tenga 3 caracteres

            # Restauramos el orden de los caracteres

            resultado[i+2] = texto[i]  # i+2 -> i

            resultado[i] = texto[i+1]  # i -> i+1

            resultado[i+1] = texto[i+2]  # i+1 -> i+2

    return ''.join(resultado)  # Unimos la lista en una cadena

  

# Texto desordenado

texto_desordenado = "4}ea9a5fev_g_lfetdmlbc8rFs{oTCpci"

  

invierte= "}e49aafe5_gvlf_tdelbm8rcs{FTCocip"

# Primero, invertimos la cadena (porque se menciona que fue invertida)

texto_invertido = invierte[::-1]  # Revertir el texto

  

# Ahora, aplicamos la función para restaurar la bandera

bandera = revertir_desorden(texto_desordenado)

print("Flag:", bandera)

  

print(texto_invertido)



picoCTF{scr8mbledt_flvg_5efaa94e}
