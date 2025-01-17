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

[](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/main/Chapter_1-3/%C3%A1rbolSint%C3%A1ctico.png)
