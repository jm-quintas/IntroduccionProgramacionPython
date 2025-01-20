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

### Problema 1. ¿Qué resultará de evaluar las siguientes expresiones?

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

En ocasiones deseamos que el ordenador recuerde ciertos valores para usarlos más adelante. Por ejemplo, supongamos que deseamos efectuar el cálculo del perímetro y el área de un círculo de radio 1.298373 m. La fórmula del perímetro es 2πr, donde r es el radio, y la fórmula del área es πr^2. (Apróximaremos el valor de π con 3.14159265359). Podemos realizar ambos cálculos del siguiente modo:

```Python
2 * 3.14159265359 * 1.298373
Resp: 8.157918156839218
```
```Python
3.14159265359 * 1.298373 ** 2
Resp: 5.296010335524904
```
Observa que hemos tenido que introducir dos veces los valores de π y r por lo que, al tener tantos decimales, es muy fácil cometer errores. Para paliar este problema podemos utilizar variables:

```Python
pi = 3.14159265359
r = 1.298373

2 * pi * r
Resp: 8.157899307283296
```
```Python
pi = 3.14159265359
r = 1.298373

pi * r ** 2
Resp: 5.295985861798707
```

En la primera línea hemos creado una variable de nombre pi y valor 3.14159265359. A continuación, hemos creado otra variable, r, y le hemos dado el valor 1.298373. El acto de dar valor a una variable se denomina ***asignación***. Al asignar un valor a una variable que no existía, Python reserva un espacio en la memoria, almacena el valor en él y crea una asociación entre el nombre de la variable y la dirección de memoria de dicho espacio. Podemos representar gráficamente el resultado de estas acciones así:

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/variables.png)

A partir de ese instante, escribir pi es equivalente a escribir 3.14159265359, y escribir r es equivalente a escribir 1.298373. Podemos almacenar el resultado de calcular el perímetro y el área en sendas variables:

```Python
pi = 3.14159265359
r = 1.298373

perimetro = 2 * pi * r
area = pi * r ** 2
```
![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/img/variables2.png)

La memoria se ha reservado correctamente, en ella se ha almacenado el valor correspondiente y la asociación entre la memoria y el nombre de la variable se ha establecido, pero no obtenemos respuesta alguna por pantalla. Debes tener en cuenta que las asignaciones son ***mudas***, es decir, no provocan salida por pantalla. Así pués, para asignar valor a una variable basta ejecutar una sentencia como ésta: ***variable = expresión***. El orden es importante. Hacer ***expresión = variable*** no es equivalente. Una asignación no es una ecuación matemática, sino una acción consistente en (por este orden):
1. Evaluar la expresión a la derecha del símbolo igual (=).
2. Guardar el valor resultante en la variable indicada a la izquierda del símbolo igual.

Se puede asignar valor a una misma variable cuantas veces se quiera. El efecto es que la variable, en cada instante, sólo ***recuerda*** el último valor asignado. . . hasta que se le asigne otro.

```Python
a = 1
2 * a
Resp: 2
```
```Python
a + 2
Resp: 3
```
```Python
a = 2
a * a
Resp: 4
```

El nombre de una variable es su identificador. Hay unas reglas precisas para construir identificadores. Si no se siguen, diremos que el identificador no es valido. Un identificador debe estar formado por letras minúsculas, mayúsculas, dígitos y/o el caracter de subrayado (_), con una restricción: que el primer caracter no sea un dígito. Hay una norma mas: un identificador no puede coincidir con una palabra reservada o palabra clave. Una palabra reservada es una palabra que tiene un significado predefinido y es necesaria para expresar ciertas construcciones del lenguaje. Aquí tienes una lista con todas las **palabras reservadas de Python: and, assert, break, class, continue, def, del, elif, else, except, exec, finally, for, from, global, if, import, in, is, lambda, not, or, pass, print, raise, return, try, while y yield**.

Dado que eres libre de llamar a una variable con el identificador que quieras, hazlo con clase: escoge siempre nombres que guarden relación con los datos del problema. Si, por ejemplo, vas a utilizar una variable para almacenar una distancia, llama a la variable *distancia* y evita nombres que no signifiquen nada; de este modo, los programas serán más legibles.

### Problema 2. Evalua los siguientes polinomios:

- a) x^4 + x^3 + 2x^2 - x, en x = 1.1. Utiliza variables para evitar teclear varias veces el valor de x.

```Python
x = 1.1
polinomio = x ** 4 + x ** 3 + 2 * x ** 2 - x

polinomio
Resp: 4.115100000000002
```

- b) x^4 + x^3 + (1/2)x^2 − x en x = 10. Asegúrate de que el resultado sea un número flotante.

```Python
x = 10
poli = x ** 4 + x ** 3 + 0.5 * x ** 2 - x

poli
Resp: 11040.0
```

## Asignaciones con operador.

Fíjate en la sentencia ***i = i + 1***: aplica un incremento unitario al contenido de la variable ***i***. Incrementar el valor de una variable en una cantidad cualquiera es tan frecuente que existe una forma compacta en Python. El incremento de ***i*** puede denotarse así:

```Python
i += 1
```

No puede haber espacio alguno entre el ***+*** y el ***=***. Todos los operadores aritméticos tienen su asignación con operador asociada.

```Python
z += 2

z *= 2

z /= 2

z -= 2

z %= 2

z **= 2
```

### Problema 3. ¿Qué resultará de ejecutar las siguientes sentencias?

```Python
z = 2
z += 2
Resp: 4
```
```Python
z = 2
z += 2 - 2
Resp: 2
```
```Python
Z = 2
z *= 2
Resp: 4
```
```Python
z = 2
z *= 1 + 1
Resp: 4
```
```Python
z = 2
z /= 2
Resp: 1.0
```
```Python
z = 2
z %= 3
Resp: 2
```
```Python
z = 2
z /= 3 - 1
Resp: 1.0
```
```Python
z = 2
z -= 2 + 1
Resp: -1
```
```Python
z = 2
z -= 2
Resp: 0
```
```Python
z = 2
z **= 3
Resp: 8
```

## El tipo de datos cadena.

Hasta el momento hemos visto que Python puede manipular datos numéricos de dos tipos:
enteros y flotantes. Pero Python también puede manipular otros tipos de datos. Vamos a
estudiar ahora el tipo de datos que se denomina cadena. Una ***cadena es una secuencia
de caracteres (letras, números, espacios, marcas de puntuación, etc.) y en Python se
distingue porque va encerrada entre comillas simples o dobles***. Las cadenas pueden usarse para representar información textual: nombres de personas, nombres de colores, matrículas de coche... Las cadenas también pueden almacenarse en variables.

```Python
nombre = 'pepe'
nombre
Resp: 'pepe'
```
```Python
ciudad = "Maracaibo"
ciudad
Resp: 'Maracaibo'
```

Es posible realizar operaciones con cadenas. Por ejemplo, podemos ***sumar*** cadenas
añadiendo una a otra.

```Python
'a' + 'b'
Resp: 'ab'
```
```Python
nombre = 'pepe'
nombre += 'cano'
nombre
Resp: 'pepecano'
```
```Python
nombre = 'pepe'
nombre + ' ' + 'cano'
Resp: 'pepe cano'
```

Hablando con propiedad, esta operación no se llama suma, sino concatenación. El
símbolo utilizado es +, el mismo que usamos cuando sumamos enteros y/o flotantes; pero aunque el símbolo sea el mismo, ten en cuenta que no es igual sumar números que concatenar cadenas:

```Python
'12' + '12'
Resp: 1212
```
```Python
12 + 12
Resp: 24
```

Sumar o concatenar una cadena y un valor numérico (entero o flotante) produce un error. Y para acabar, hay un operador de repetición de cadenas. El símbolo que lo denota es *, el mismo que hemos usado para multiplicar enteros y/o flotantes. El operador de repetición necesita dos datos: uno de tipo cadena y otro de tipo entero. El resultado es la concatenación de la cadena consigo misma tantas veces como indique el número entero:

```Python
'hola' * 5
Resp: 'holaholaholaholahola'
```

El concepto de comparación entre números te resulta familiar porque lo has estudiado antes en matemáticas. Python extiende el concepto de comparación a otros tipos de datos, como las cadenas. En el caso de los operadores == y != el significado esta claro: dos cadenas son iguales si son iguales carácter a carácter, y distintas en caso contrario. Pero, ¿qué significa que una cadena sea menor que otra? Python utiliza un criterio de comparación de cadenas muy natural: el orden alfabético. En principio, una cadena es menor que otra si la precede al disponerlas en un diccionario. ¿Y cómo se comparan cadenas con caracteres no alfabéticos? Python utiliza los códigos ASCII de los caracteres para decidir su orden alfabético Para conocer el valor numérico que corresponde a un carácter, puedes utilizar la función predefinida ***ord***, a la que le has de pasar el carácter en cuestión como argumento.

```Python
ord('a')
Resp: 97
```

La función inversa (la que pasa un número a su carácter equivalente) es chr.

```Python
chr(97)
Resp: 'a'
```

La tabla ***ASCII*** presenta un problema cuando queremos ordenar palabras: las letras
mayúsculas tienen un valor numérico inferior a las letras minúsculas (por lo que 'Zapata'
precede a 'ajo') y las letras acentuadas son siempre **mayores** que sus equivalentes sin
acentuar ('abanico' es menor que 'ábaco'). Hay formas de configurar el sistema operativo
para que tenga en cuenta los criterios de ordenación propios de cada lengua al efectuar
comparaciones.

### Problema. ¿Qué resultados se muestran al evaluar estas expresiones?

```Python
'abalorico' < 'abecedario'
Resp: True
```
```Python
'abecedario' < 'abecedario'
Resp: False
```

```Python
'abecedario' <= 'abecedario'
Resp: True
```

```Python
'Abecedario' == 'Abecedario'
Resp: True
```

```Python
124 < 13
Resp: False
```

```Python
'124' < '13'
Resp: True
```

## Funciones predefinidas.

Hemos estudiado los operadores aritméticos basicos. Python también proporciona funciones que podemos utilizar en las expresiones. Estas funciones se dice que están predefinidas. La función ***abs***, por ejemplo, calcula el valor absoluto de un número. Podemos usarla como en estas expresiones:  

```Python
abs(-3)
Resp: 3
```
```Python
abs(3)
Resp: 3
```

El número sobre el que se aplica la función se denomina argumento. Observa que el argumento de la función debe ir encerrado entre paréntesis. Existen muchas funciones predefinidas, pero es pronto para aprenderlas todas. Te resumimos algunas que ya puedes utilizar:

- ***float:*** conversión a flotante. Si recibe un número entero como argumento, devuelve el mismo número convertido en un flotante equivalente.

```Python
float(3)
Resp: 3.0
```

La función ***float*** también acepta argumentos de tipo cadena. Cuando se le pasa una cadena, ***float*** la convierte en el número flotante que ésta representa:

```Python
float('3.2')
Resp: 3.2
```
```Python
float('3.2e10')
Resp: 32000000000.0
```

Pero si la cadena no representa un flotante, se produce un error de tipo ValueError, es decir, ***error de valor***. Si ***float*** recibe un argumento flotante, devuelve el mismo valor que se suministra como argumento.

- ***int***: conversión a entero. Si recibe un número flotante como argumento, devuelve el entero que se obtiene eliminando la parte fraccionaria.

```Python
int(2.1)
Resp: 2
```
```Python
int(-2.9)
Resp: -2
```

También la función ***int*** acepta como argumento una cadena:

```Python
int('2')
Resp: 2
```

Si ***int*** recibe un argumento entero, devuelve el argumento tal cual.

- ***str***: conversión a cadena. Recibe un número y devuelve una representación de éste como cadena.

```Python
str(2.1)
Resp: '2.1'
```
```Python
str(234E47)
Resp: '2.34e+49'
```

La función str también puede recibir como argumento una cadena, pero en ese caso devuelve como resultado la misma cadena.

- ***round***: redondeo. Puede usarse con uno o dos argumentos. Si se usa con un sólo argumento, toma un número de punto flotante como entrada y devuelve un entero redondeado al número más cercano.

```Python
round(2.1)
Resp: 2
```
```Python
round(2.9)
Resp: 3
```
```Python
round(-2.9)
Resp: -3
```

Si ***round*** recibe dos argumentos,  éstos deben ir separados por una coma y el segundo indica el número de decimales que deseamos conservar tras el redondeo.

```Python
round(2.1451, 2)
Resp: 2.15
```
```Python
round(2.1451, 3)
Resp: 2.145
```
```Python
round(2.1451, 0)
Resp: 2.0
```

Estas funciones (y las que estudiaremos más adelante) pueden formar parte de expresiones y sus argumentos pueden, a su vez, ser expresiones.

```Python
abs(round(-34.2764, 1))
Resp: 34.3
```

### Problemas.

1. Calcula con una única expresión el valor absoluto del redondeo de −3.2. (El resultado es 3).
```Python
abs(round(-3.2))
Resp: 3
```
2. Convierte (en una unica expresión) a una cadena el resultado de la división 5011/10000 redondeado con 3 decimales.
```Python
str(round(5011/10000, 3))
Resp: '0.501'
```
3. ¿Qué resulta de evaluar estas expresiones?
```Python
str(21) + str(1.2)
Resp: '211.2'
```
```Python
int(str(2) + str(3))
Resp: ValueError: invalid literal for int() with base 10: '21.2'
```
```Python
str(int(12.3)) + '0'
Resp: '120'
```
```Python
int('2' + '3')
Resp: 23
```
```Python
str(2 + 3)
Resp: '5'
```
```Python
str(int(21)) + float(3))
Resp: SyntaxError: unmatched ')'
```

## Funciones definidas en módulos.

Python también proporciona funciones trigonométricas, logaritmos, etc., pero no están directamente disponibles cuando iniciamos una sesión. Antes de utilizarlas hemos de
indicar a Python que vamos a hacerlo. Para ello, importamos cada función de un módulo.

- **El módulo** ***math***.

Empezaremos por importar la función ***seno*** (***sin***, del inglés sinus) del módulo matemático (***math***):

```Python
from math import sin
```
Ahora podemos utilizar la función en nuestros calculos:

```Python
from math import sin
sin(0)
Resp: 0.0
```
```Python
from math import sin
sin(1)
Resp: 0.8414709848078965
```

Observa que el argumento de la función seno debe expresarse en radianes. Inicialmente Python no sabe calcular la función seno. Cuando importamos una función, Python aprende su definición y nos permite utilizarla. Las definiciones de funciones residen en módulos. Las funciones trigonométricas residen en el módulo matemático. Importemos del módulo matemático la función coseno:

```Python
from math import cos
cos(1)
Resp: 0.5403023058681398
```
En una misma sentencia podemos importar más de una función. Basta con separar sus nombres con comas:

```Python
from math import sin, cos
```

Puede resultar tedioso importar un gran número de funciones y variables de un módulo. Python ofrece un atajo: si ***utilizamos un asterisco, se importan todos los elementos*** de un módulo. Para importar todas las funciones del módulo math escribimos:

```Python
from math import *
```

Así de fácil. De todos modos, no resulta muy aconsejable por dos razones:

- Al importar elemento a elemento, el programa gana en legibilidad, pués sabemos de donde proviene cada identificador.

- Si hemos definido una variable con un nombre determinado y dicho nombre coincide con el de una función definida en un módulo, nuestra variable será sustituida por la  función. Si no sabes todos los elementos que define un módulo, es posible que esta coincidencia de nombre tenga lugar, te pase inadvertida inicialmente y te lleves una sorpresa cuando intentes usar la variable.
