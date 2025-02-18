# Estructura de Control.

Los programas que hemos aprendido a construir hasta el momento presentan siempre una misma secuencia de acciones:

1. Se piden datos al usuario (asignando a variables valores obtenidos con ***input***).

2. Se efectuan cálculos con los datos introducidos por el usuario, guardando el resultado en variables (mediante asignaciones).

3. Se muestran por pantalla los resultados almacenados en variables (mediante la sentencia ***print***).

Estos programas se forman como una serie de líneas que se ejecutan una tras otra, desde la primera hasta la última y siguiendo el mismo orden con el que aparecen en el fichero: el ***flujo de ejecución del programa es estrictamente secuencial***.

No obstante, es posible alterar el flujo de ejecución de los programas para hacer que:

1. Tomen decisiones a partir de los datos y/o resultados intermedios y, en función de éstas, ejecuten ciertas sentencias y otras no.

2. Tomen decisiones a partir de los datos y/o resultados intermedios y, en función de éstas, ejecuten ciertas sentencias más de una vez.

***El primer tipo de alteración del flujo de control se efectua con sentencias condicionales o de selección y el segundo tipo con sentencias iterativas o de repetición***. Las sentencias que permiten alterar el flujo de ejecución se engloban en las denominadas estructuras de control de flujo (que abreviamos con el término ***estructuras de control***).

## Sentencias condicionales.

Los lenguajes de programación convencionales presentan una sentencia especial cuyo significado es:

***Al llegar a este punto, ejecuta esta(s) acción(es) sólo si esta condición es cierta***

Este tipo de sentencia se denomina condicional o de selección y en Python es de la siguiente forma:

```Python
if condición:
acción
acción
...
acción
```

Expresado de otra manera:

```Python
if condición:
    # Código a ejecutar si la condición es verdadera
```

En inglés ***if*** significa **si**. En nuestro caso, deseamos detectar la condición ***a no vale 0*** y, sólo en ese caso, ejecutar las últimas líneas del programa:

```Python
a = float(input("Valor de a: "))
b = float(input("Valor de b: "))

if a != 0:
    x = -b/a
    print("Solución: ", x)
```

Analicemos detenidamente las líneas 4, 5 y 6. En la línea 4 aparece la sentencia condicional ***if*** seguida de lo que, según hemos dicho, debe ser una condición. La condición se lee fácilmente si sabemos qué **!=** significa ***es distinto de***. Así pues, la línea 4 se lee si ***a*** es distinto de 0. La línea que empieza con ***if*** debe finalizar obligatoriamente con dos puntos **:**. Fíjate en que las dos siguientes líneas se escriben más a la derecha. Decimos que esta línea presentan mayor indentación o sangrado que la línea que empieza con ***if***. Esta mayor indentación indica que la ejecución de estas dos líneas depende de que se satisfaga la condición ***a*** **!=** 0: sólo cuando ésta es cierta se ejecutan las líneas de mayor sangrado. Así pues, cuando ***a*** valga 0, esas líneas no se ejecutarán , evitando de este modo el error de división por cero.

Veamos qué hace este otro programa:

```Python
a = float(input("Valor de a: "))
b = float(input("Valor de b: "))

if a != 0:
    x = -b/a
    print("Solución: ", x)
if a == 0:
    print("La ecuación no tiene solución")
```
```
Valor de a: 0
Valor de b: 3

La ecuación no tiene solución
```

```
Valor de a: 1
Valor de b: -1
Solución: 1
```

Las líneas 7 y 8 empiezan, nuevamente, con una sentencia condicional. En lugar de **!=**, el operador de comparación utilizado es **==**. La sentencia se lee si ***a*** es igual a 0.

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_4-5/img/Captura%20desde%202025-02-18%2011-20-36.png)

Este tipo de análisis, en el que seguimos el curso del programa línea a línea para una configuración dada de los datos de entrada, recibe el nombre de ***traza de ejecución***. Las ***trazas de ejecución*** son de gran ayuda para comprender qué hace un programa y localizar así posibles errores.

## Sentencias condicionales anidadas.

Vamos a realizar un último refinamiento del programa. De momento, cuando ***a*** es 0 el programa muestra un mensaje que indica que la ecuación no tiene solución. Bueno,
nosotros sabemos que esto no es cierto: sí, además, ***b*** vale 0, entonces la ecuación tiene infinitas soluciones. Para que el programa dé una información correcta vamos a modificarlo de modo que, cuando a sea 0, muestre un mensaje u otro en función del valor de ***b***:

```Python
a = float(input("Valor de a: ")
b = float(input("Valor de b: ")

if a != 0:
    x = -b/a
    print("Solución: ", x)

if a == 0:
    if b != 0:
        print("La ecuación no tiene solución")
    if b == 0:
        print("La ecuación tiene infinitas soluciones")
``` 

Fíjate en la indentación de las líneas. Las líneas 8–11 estan más a la derecha que la línea 7. Ninguna de ellas se ejecutará a menos que la condición de la línea 7 se satisfaga. Más aún, la línea 9 esta más a la derecha que la línea 8, por lo que su ejecución depende del resultado de la condición de dicha línea; y la ejecución de la línea 11 depende de la satisfacción de la condición de la línea 10. Recuerda que en ***los programas Python la indentación determina de qué sentencia depende cada bloque de sentencias***. Las estructuras de control pueden anidarse, es decir, aparecer unas ***dentro*** de otras.

### Tarea 1. Diseña un programa que lea un número flotante por teclado y muestre por pantalla el mensaje "El número es negativo" sólo si el número es menor que cero.

```Python
numero_flotante = float(input("Introduce un número: "))

if numero_flotante < 0:
    print("El número es negativo")

if numero_flotante >= 0:
    print("El número es positivo")
```
```
Introduce un número: -1
El número es negativo
```
```
Introduce un número: 2
El número es positivo
```
