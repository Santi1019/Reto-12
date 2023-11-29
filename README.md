# Reto-12

1. 
Consulte que hacen los siguientes métodos de cadenas en Python: termina con, comienza con, isalpha, isalnum, isdigit, isspace, istitle, islower, isupper.



-Desarrollando el primer punto 

termina con

El método termina_con() comprueba si una cadena termina con un determinado subcadena. Si la cadena termina con el subcadena, el método devuelve True, de lo contrario devuelve False.

Por ejemplo:

```
cadena = "Hola mundo"

print(cadena.termina_con("mundo"))  # True
print(cadena.termina_con("hola"))  # False
```
comienza con

El método comienza_con() funciona de forma similar al método termina_con(), pero comprueba si una cadena comienza con un determinado subcadena.

Por ejemplo:

```
cadena = "Hola mundo"

print(cadena.comienza_con("Hola"))  # True
print(cadena.comienza_con("mundo"))  # False
````
isalpha

El método isalpha() comprueba si todos los caracteres de una cadena son letras. Si todos los caracteres de la cadena son letras, el método devuelve True, de lo contrario devuelve False.

Por ejemplo:

```
cadena = "Hola mundo"

print(cadena.isalpha())  # False
cadena = "hola"

print(cadena.isalpha())  # True
```
isalnum

El método isalnum() comprueba si todos los caracteres de una cadena son letras o números. Si todos los caracteres de la cadena son letras o números, el método devuelve True, de lo contrario devuelve False.

Por ejemplo:

```
cadena = "Hola mundo"

print(cadena.isalnum())  # False
cadena = "hola123"

print(cadena.isalnum())  # True
```
isdigit

El método isdigit() comprueba si todos los caracteres de una cadena son dígitos. Si todos los caracteres de la cadena son dígitos, el método devuelve True, de lo contrario devuelve False.

Por ejemplo:

```
cadena = "Hola mundo"

print(cadena.isdigit())  # False
cadena = "12345"

print(cadena.isdigit())  # True
```
isspace

El método isspace() comprueba si todos los caracteres de una cadena son espacios en blanco. Si todos los caracteres de la cadena son espacios en blanco, el método devuelve True, de lo contrario devuelve False.

Por ejemplo:

```
cadena = "Hola mundo"

print(cadena.isspace())  # False
cadena = " "

print(cadena.isspace())  # True
```
istitle

El método istitle() comprueba si todos los caracteres de una cadena son mayúsculas, excepto los primeros caracteres de cada palabra, que deben ser minúsculas. Si todos los caracteres de la cadena cumplen con este criterio, el método devuelve True, de lo contrario devuelve False.

Por ejemplo:

```
cadena = "Hola mundo"

print(cadena.istitle())  # False
cadena = "Hola Mundo"

print(cadena.istitle())  # True
```
islower

El método islower() comprueba si todos los caracteres de una cadena son minúsculas. Si todos los caracteres de la cadena son minúsculas, el método devuelve True, de lo contrario devuelve False.

Por ejemplo:

```
cadena = "Hola mundo"

print(cadena.islower())  # False
cadena = "hola mundo"

print(cadena.islower())  # True
```
isupper

El método isupper() comprueba si todos los caracteres de una cadena son mayúsculas. Si todos los caracteres de la cadena son mayúsculas, el método devuelve True, de lo contrario devuelve False.

```
cadena = "Hola mundo"

print(cadena.isupper())  # False
cadena = "HOLA MUNDO"

print(cadena.isupper())  # True
```



2. Procesar el archivo y extraer:

cantidad de voces
cantidad de consonantes
Listado de las 50 palabras que más se repiten


-Desarrollando el segundo punto
```
import re  # Importa el módulo de expresiones regulares
from collections import Counter  # Importa la clase Counter para contar elementos



def procesar_archivo(archivo):
    # Abre el archivo en modo lectura y codifica su contenido como UTF-8
     
    with open("mbox-short.txt", "r",encoding="utf-8") as archivo:

        contenido = archivo.read()  # Lee todo el contenido del archivo

    # Cuenta la cantidad de vocales y consonantes en el contenido
    vocales = "aeiouáéíóúü"  # Define las vocales
    consonantes = "bcdfghjklmnpqrstvwxyz"  # Define las consonantes
    cantidad_vocales = sum(1 for char in contenido if char.lower() in vocales)
    cantidad_consonantes = sum(1 for char in contenido if char.lower() in consonantes)



    # Tokeniza (divide) el contenido en palabras y las convierte a minúsculas
    palabras = re.findall(r"\b\w+\b", contenido.lower())

    # Cuenta la frecuencia de cada palabra usando Counter
    contador_palabras = Counter(palabras)

    # Obtiene las 50 palabras más comunes
    palabras_comunes = contador_palabras.most_common(50)

    # Muestra los resultados
    print(f"Cantidad de vocales: {cantidad_vocales}")
    print(f"Cantidad de consonantes: {cantidad_consonantes}")
    print("\nPalabras más comunes:")
    for palabra, frecuencia in palabras_comunes:
        print(f"{palabra}: {frecuencia}")

# Reemplaza "nombre_del_archivo.txt" con el nombre de tu archivo
procesar_archivo("mbox-short.txt")

```

