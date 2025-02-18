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
Valor de b: 2

La ecuación no tiene solución
```

Las líneas 7 y 8 empiezan, nuevamente, con una sentencia condicional. En lugar de **!=**, el operador de comparación utilizado es **==**. La sentencia se lee ˂˂si a es igual a 0.
