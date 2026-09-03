Definir el alfabeto de 26 letras (A-Z).
Recorrer el mensaje cifrado carácter por carácter.
Si el carácter es un espacio u otro símbolo no alfabético, dejarlo igual.
Si es una letra, encontrar su posición en el alfabeto.
Retroceder 1 posición (el inverso de +1). Si la letra es "A", dar la vuelta circular a "Z".
Guardar la letra resultante.
Repetir hasta terminar el mensaje y devolver el resultado.

INICIO

    DEFINIR alfabeto = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    DEFINIR desplazamiento = 1

    FUNCION descifrar_letra(letra)
        SI letra ES espacio U OTRO SÍMBOLO NO ALFABÉTICO ENTONCES
            RETORNAR letra SIN CAMBIOS
        FIN SI
        posicion = posición_de(letra, alfabeto)
        nueva_posicion = (posicion - desplazamiento + 26) MOD 26
        RETORNAR alfabeto[nueva_posicion]
    FIN FUNCION

    FUNCION descifrar_mensaje(mensaje)
        resultado = ""
        PARA cada caracter EN mensaje
            resultado = resultado + descifrar_letra(caracter)
        FIN PARA
        RETORNAR resultado
    FIN FUNCION

    LEER mensaje_cifrado
    MOSTRAR descifrar_mensaje(mensaje_cifrado)

FIN

