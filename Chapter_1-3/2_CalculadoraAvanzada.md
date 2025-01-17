# Calculadora Avanzada

## Operadores.

Los operadores aritméticos en Python son símbolos especiales que se utilizan para realizar operaciones matemáticas básicas sobre números (operandos). Estos operadores nos permiten sumar, restar, multiplicar, dividir y realizar otras operaciones numéricas.  

| Operador | Descripción |
| :------: | :------: |
| + | Suma |
| - | Resta |
| * | Multiplicación |
| / | División (solo resultados en punto flotante) |
| // | división entera (Resultado redondeado hacia abajo) |
| % | Módulo (resto de la división) |
| ** | Exponenciación |

Probemos algunas expresiones formadas con estos operadores en el prompt (sesión interactiva en Python):

```Python
1 + 2 
Resp: 3
```

```Python
1 + 2 + 3
Resp: 6
```

```Python
1 - 2 + 3
Resp: 2
```

Podemos introducir varias operaciones en una misma línea o expresión. El orden en que se efectuan las operaciones es (en principio) de izquierda a derecha. La expresión 1 - 2 + 3, por ejemplo, equivale matemáticamente a ((1 − 2) + 3); por ello decimos que la suma y la resta son operadores ***asociativos por la izquierda***. Podemos representar gráficamente el orden de aplicación de las operaciones utilizando arboles sintácticos. Un arbol sintáctico es una representación gráfica en la que disponemos los operadores y los operandos como nodos y en los que cada operador esta conectado a sus operandos. El arbol sintáctico de la expresión ˂˂1 - 2 + 3˃˃ es éste:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/%C3%A1rbolSint%C3%A1ctico.png)

El ***nodo superior de un árbol recibe el nombre de nodo raíz***. Los ***nodos etiquetados con operadores (representados con círculos) se denominan nodos interiores***. Los ***nodos interiores tienen uno o más nodos hijo o descendientes*** (de los que ellos son sus respectivos nodos padre o ascendientes). Dichos nodos son nodos raíz de otros (sub)árboles sintácticos (¡la definición de árbol sintáctico es auto-referencial!). ***Los valores resultantes de evaluar las expresiones asociadas a dichos (sub)árboles constituyen los operandos de la operación que representa el nodo interior***. Los ***nodos sin descendientes se denominan nodos terminales u hojas (representados con cuadrados) y corresponden a valores numéricos***.

La evaluación de cada operación individual en el árbol sintáctico ˂˂fluye˃˃ de las hojas hacia la raíz (el nodo superior); es decir, en primer lugar se evalua la subexpresión ˂˂1 - 2˃˃, que corresponde al subárbol más profundo. El resultado de la evaluación es −1:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/%C3%A1rbolSint%C3%A1ctico2.png)

A continuación se evalua la subexpresión que suma el resultado de evaluar ˂˂1 - 2˃˃ al valor 3:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/%C3%A1rbolSint%C3%A1ctico3.png)

Así se obtiene el resultado final: el valor 2. Si deseamos calcular (1−(2+3)) podemos hacerlo anadiendo paréntesis a la expresión aritmética:

```Python
1 - (2 + 3)
Resp: -4
```

El árbol sintáctico de esta nueva expresión es:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/%C3%A1rbolSint%C3%A1ctico4.png)

En este nuevo árbol, la primera subexpresión evaluada es la que corresponde al subárbol derecho. Observa que en el árbol sintáctico no aparecen los paréntesis de la expresión. El árbol sintáctico ya indica el orden en que se procesan las diferentes operaciones y no necesita paréntesis. La expresión Python, sin embargo, necesita los paréntesis para indicar ese mismo orden de evaluación.

Los operadores de multiplicación y división son, respectivamente, * y /:

```Python
2 * 3
Resp: 6
```
```Python
4 / 2
Resp: 2
```
```Python
3 * 4 / 2
Resp: 6
```
```Python
12 / 3 * 2
Resp: 8
```

Observa que estos operadores también son asociativos por la izquierda: la expresión ˂˂3 * 4 / 2˃˃ equivale a ((3 · 4) / 2) = 3 · 4 / 2, es decir, tiene el siguiente árbol sintáctico:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/%C3%A1rbolSint%C3%A1ctico5.png)

La expresión 12 / 3 * 2 equivale a ((12/3) · 2) = 12 / 3 · 2, o sea, su árbol sintáctico es:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/%C3%A1rbolSint%C3%A1ctico6.png)

¿Qué pasa si combinamos en una misma expresión operadores de suma o resta con operadores de multiplicación o división? Fíjate en que la regla de aplicación de operadores
de izquierda a derecha no siempre se observa:

```Python
2 * 4 + 5
Resp: 13
```
```Python
2 + 4 * 5
Resp: 22
```

En la segunda expresión, primero se ha efectuado el producto 4 * 5 y el resultado se ha sumado al valor 2. Ocurre que los operadores de multiplicación y división son
prioritarios frente a los de suma y resta. Decimos que la multiplicación y la división tienen mayor nivel de precedencia o prioridad que la suma y la resta. El árbol sintáctico de (2 * 4 + 5) es:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/%C3%A1rbolSint%C3%A1ctico7.png)

El de 2 + 4 * 5 es:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/%C3%A1rbolSint%C3%A1ctico8.png)

Pero, ¡atención!, el cambio de signo tiene mayor prioridad que la multiplicación y la división:

```Python
-2 * 2
Resp: -4
```
```Python
--2 * 2
Resp: 4
```

Los árboles sintácticos correspondientes a estas dos expresiones son, respectivamente:

