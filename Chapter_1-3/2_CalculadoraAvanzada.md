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

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/%C3%A1rbolSint%C3%A1ctico.png)

El ***nodo superior de un árbol recibe el nombre de nodo raíz***. Los ***nodos etiquetados con operadores (representados con círculos) se denominan nodos interiores***. Los ***nodos interiores tienen uno o más nodos hijo o descendientes*** (de los que ellos son sus respectivos nodos padre o ascendientes). Dichos nodos son nodos raíz de otros (sub)árboles sintácticos (¡la definición de árbol sintáctico es auto-referencial!). ***Los valores resultantes de evaluar las expresiones asociadas a dichos (sub)árboles constituyen los operandos de la operación que representa el nodo interior***. Los ***nodos sin descendientes se denominan nodos terminales u hojas (representados con cuadrados) y corresponden a valores numéricos***.

La evaluación de cada operación individual en el árbol sintáctico ˂˂fluye˃˃ de las hojas hacia la raíz (el nodo superior); es decir, en primer lugar se evalua la subexpresión ˂˂1 - 2˃˃, que corresponde al subárbol más profundo. El resultado de la evaluación es −1:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/%C3%A1rbolSint%C3%A1ctico2.png)

A continuación se evalua la subexpresión que suma el resultado de evaluar ˂˂1 - 2˃˃ al valor 3:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/%C3%A1rbolSint%C3%A1ctico3.png)

Así se obtiene el resultado final: el valor 2. Si deseamos calcular (1−(2+3)) podemos hacerlo anadiendo paréntesis a la expresión aritmética:

```Python
1 - (2 + 3)
Resp: -4
```

El árbol sintáctico de esta nueva expresión es:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/%C3%A1rbolSint%C3%A1ctico4.png)

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

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/%C3%A1rbolSint%C3%A1ctico5.png)

La expresión 12 / 3 * 2 equivale a ((12/3) · 2) = 12 / 3 · 2, o sea, su árbol sintáctico es:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/%C3%A1rbolSint%C3%A1ctico6.png)

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

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/%C3%A1rbolSint%C3%A1ctico7.png)

El de 2 + 4 * 5 es:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/%C3%A1rbolSint%C3%A1ctico8.png)

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

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/%C3%A1rbolSint%C3%A1ctico9.png)

Si los operadores siguen unas reglas de precedencia que determinan su orden de aplicación, ¿qué hacer cuando deseamos un orden de aplicación distinto? Usar paréntesis,
como hacemos con la notación matemática convencional. La expresión 2 * (4 + 5), por ejemplo, presenta este arbol sintáctico:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/%20%C3%A1rbolSint%C3%A1ctico_10.png)

```Python
2 * (4 + 5)
Resp: 18
```

Existen más operadores en Python. Tenemos, por ejemplo, el operador módulo, que se denota con el símbolo de porcentaje % (aunque nada tiene que ver con el cálculo de porcentajes). El operador módulo devuelve el resto de la división entera entre dos operandos.

```Python
27 % 5
Resp: 2
```
```Python
27 % 5
Resp: 0
```

El operador % también es asociativo por la izquierda y su prioridad es la misma que la de la multiplicación o la división. El último operador que vamos a estudiar es la exponenciación, que se denota con dos asteriscos juntos, no separados por ningún espacio en blanco: **. Lo que en notación matemática convencional expresamos como 2^3 se expresa en Python con 2 ** 3.

```Python
2 ** 3
Resp: 8
```

Pero, ¡ojo!, la exponenciación es asociativa por la derecha. La expresión 2 ** 3 ** 2 equivale a 2^(3^2) = 2^9 = 512, su árbol sintáctico es:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/%C3%A1rbolSint%C3%A1ctico_11.png)

Por otra parte, la exponenciación tiene mayor precedencia que cualquiera de los otros operadores presentados.

La tabla 2.1 resume las características de los operadores Python: su aridad (número de operandos), asociatividad y precedencia.

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/tabla%202.1.png)

## Tipos de datos.

### Enteros y flotantes.

Cada valor utilizado por Python es de un tipo determinado. Hasta el momento sólo hemos utilizado datos de tipo entero, es decir, sin decimales. Cuando se efectua una operación, Python tiene en cuenta el tipo de los operandos a la hora de producir el resultado. Si los dos operandos son de tipo entero, el resultado también es de tipo entero, así que la división entera entre los enteros 3 y 2 produce el valor entero 1. Si deseamos obtener resultados de tipo real, deberemos usar operandos reales. Los
operandos reales deben llevar, en principio, una parte decimal, aunque ésta sea nula.

```Python
3.0 / 2.0
Resp: 1.5
```

Hay diferencias entre enteros y reales en Python más allá de que los primeros no tengan decimales y los segundos sí. El número 3 y el número 3.0, por ejemplo, son indistinguibles en matemáticas, pero sí son diferentes en Python. ¿Qué diferencias hay? 
- Los enteros suelen ocupar menos memoria.
- Las operaciones entre enteros son, generalmente, más rápidas.

Hemos de precisar algo respecto a la denominación de los números con decimales: el término ***reales*** no es adecuado, ya que induce a pensar en los números reales de las matemáticas. En matemáticas, los números reales pueden presentar infinitos decimales, y eso es imposible en un computador. Al trabajar con computadores tendremos que conformarnos con meras aproximaciones a los números reales. Recuerda que todo en el computador son secuencias de ceros y unos. Deberemos, pués, representar internamente con ellos las aproximaciones a los números reales. Para facilitar el intercambio de datos, todos los computadores convencionales utilizan una misma codificación, es decir, representan del mismo modo las aproximaciones a los números reales. Esta codificación se conoce como ***IEEE Standard 754 floating point*** (que se puede traducir por ***Estandar IEEE 754 para coma flotante***), así que llamaremos números en formato de coma flotante o simplemente flotantes a los números con decimales que podemos representar con el ordenador.  

Un número flotante debe especificarse siguiendo ciertas reglas. En principio, consta de dos partes: mantisa y exponente. El exponente se separa de la mantisa con la letra
˂˂e˃˃ (o ˂˂E˃˃). Por ejemplo, el número flotante 2e3 (o 2E3) tiene mantisa 2 y exponente 3, y representa al número 2 · 10^3, es decir, 2000. El exponente puede ser negativo: 3.2e-3 es 3.2·10^−3 , o sea, 0.0032. Ten en cuenta que si un número flotante no lleva exponente debe llevar parte fraccionaria. Un par de reglas mas: si la parte entera del número es nula, el flotante puede empezar directamente con un punto, y si la parte fraccionaria es nula, puede acabar con un punto. Veamos un par de ejemplos: el número 0.1 se puede escribir también como .1; por otra parte, el número 2.0 puede escribirse como 2., es decir, en ambos casos el cero es opcional. Es posible mezclar en una misma expresión datos de tipos distintos.

```Python
3.5 / 2
Resp: 1.5
```
Python sigue una regla sencilla: si hay datos de tipos distintos, el resultado es del tipo ***más general***. Los ***flotantes son de tipo más general*** que los enteros.

## Problema 1. ¿Qué resultará de evaluar las siguientes expresiones?

```Python
1 / 2 / 4.0
Resp: 1.125
```
```Python
1 / 2.0 / 4.0
Resp: 1.125
```
```Python
4 ** .5
Resp: 2.0
```
```Python
4.0 ** (1/2)
Resp: 2.0
```
```Python
4.0 ** (1.0 / 2) + 1 / 2.0
Resp: 4.0
```
```Python
3e3 / 10
Resp: 300.0
```

## Valores lógicos.
Desde la versión 2.3, Python ofrece un tipo de datos especial que permite expresar sólo dos valores: cierto y falso. El ***valor cierto se expresa con True*** y el ***valor falso con False***. Son los valores lógicos o booleanos. Este último nombre deriva del nombre de un matemático, Boole, que desarrolló un sistema algebraico basado en estos dos valores y tres operaciones: la conjunción, la disyunción y la negación. Python ofrece soporte para estas operaciones con los operadores lógicos.

### Operadores lógicos y de comparación.

Hay tres operadores lógicos en Python: la ***y lógica o conjunción (and)***, la ***o lógica o disyunción (or)*** y el ***no lógico o negación (not)***.
El operador **and** da como resultado el valor cierto si y sólo si son ciertos sus dos operandos. Esta es su tabla de verdad:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/TablaVerdad_and.png)

El operador **or** proporciona True si cualquiera de sus operandos es True, y False sólo cuando ambos operandos son Falses. Esta es su tabla de verdad:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/TablaVerdad_or.png)

El operador **not** es unario, y proporciona el valor True si su operando es False y viceversa. He aquí su tabla de verdad:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/TablaVerdad_not.png)

Podemos combinar valores lógicos y operadores lógicos para formar expresiones lógicas.

```Python
True and False
Resp: False
```

```Python
not True
Resp: False
```

```Python
True and True or False
Resp: True
```

Precedencia de los operadores lógicos:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/TablaPrecedencia_OpLogicos.png)

Hay una familia de operadores que devuelven valores booleanos. Entre ellos tenemos a los operadores de comparación, que estudiamos en este apartado. Uno de ellos es el operador de igualdad, que devuelve True si los valores comparados son iguales. El operador de igualdad se denota con dos iguales seguidos: ==.

```Python
2 == 3
Resp: False
```
```Python
2 == 2
Resp: True
```
```Python
2 == 1+1
Resp: True
```

Observa la última expresión evaluada: es posible combinar operadores de comparación y operadores aritméticos. No sólo eso, también podemos combinar en una misma expresión
operadores lógicos, aritméticos y de comparación:

```Python
True or (2 == 1 + 2)) == True
Resp: True
```

Presentamos todos los operadores de comparaciÓn en la tabla 2.3 y te mostramos algunos ejemplos de uso.

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/OperadoresComparaci%C3%B3n.png)

```Python
2 < 1
Resp: False
```
```Python
5 > 1
Resp: True
```
```Python
5 >= 1
Resp: True
```
```Python
1 != 0
Resp: True
```

Es hora de que presentemos una tabla completa (tabla 2.4) con todos los operadores que conocemos para comparar entre sí la precedencia de cada uno de ellos cuando aparece
combinado con otros.

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/OperadoresL%C3%B3gicosComparaci%C3%B3n.png)

Cuando aparece una sucesión de comparadores como, por ejemplo, 2 < 3 < 4, Python la evalúa igual qué (2 < 3) and (3 < 4). Esta solución permite expresar condiciones complejas de modo sencillo y, en casos como el de este ejemplo, se lee del mismo modo que se leería con la notación matemática habitual, lo cual parece deseable.

```Python
True == True != False
Resp: True
```
```Python
1 < 2 < 3 < 4 < 5
Resp: True
```
```Python
(1 < 2 < 3) and (4 < 5)
Resp: True
```
```Python
(1 < 2 < 4) and (3 < 5)
Resp: True
```

## Variables y asignaciones.
