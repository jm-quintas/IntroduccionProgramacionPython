# Programas.

En este tema aprenderemos a introducir secuencias de expresiones y asignaciones en un fichero de texto y pedir a Python que las ejecute todas, una tras otra. Denominaremos programa al contenido del fichero de texto. Puedes generar los ficheros con cualquier editor de texto. Nosotros utilizaremos un entorno de programación: el entorno ***Visual Studio Code***. Un entorno de programación es un conjunto de herramientas que facilitan el trabajo del programador.

Puedes introducir expresiones en el entorno interactivo de ***Visual Studio Code***, del mismo modo que hemos hecho al ejecutar el intérprete python desde un terminal. No nos demoremos más y escribamos nuestro primer programa. En el ***menú Archivo*** hay una opción llamada ***Nuevo archivo***. Luego se abrirá una ventana donde editaremos el ***nombre*** del archivo y en la opción ***Guardar como*** guardaremos con extensión ***.py***.

Observemos el siguiente programa:

```Python
from math import pi

radio = 1
perimetro = 2 * pi * radio

perimetro
```

La opción ***Ejecutar*** hubicado en el ***icono play*** te permite ejecutar el programa: selecciónala. ¿Qué ocurre? Nada. Aunque el programa se ha ejecutado, no vemos el resultado por ninguna parte. Analicemos el programa paso a paso. La primera línea de ***miprograma.py*** no produce salida alguna: se limita a ***importar la variable pi***. La segunda línea esta en blanco. Las líneas en blanco sólo sirven para hacer más legible el programa separando diferentes partes del mismo. La tercera ***define una variable llamada radio y le asigna el valor 1***, y ya vimos que las asignaciones no producen un resultado visible por pantalla. La cuarta línea también es una asignación. La quinta línea esta en blanco y la última es una expresión (aunque muy sencilla).

la evaluación de expresiones no produce salida por pantalla en un programa. Entonces ¿cómo veremos los resultados que producen nuestros programas? Hemos de aprender a utilizar una nueva sentencia: ***print*** (en inglés, ***imprimir***). En principio, se usa de este modo: ***print*** (expresión). Escribe en pantalla el resultado de evaluar la expresión. Modificamos el programa para que se lea así:

```Python
from math import pi

radio = 1
perimetro = 2 * pi * radio

print(perimetro)
```
```
Resp: 6.283185307179586
```

Si ejecutas ahora el programa aparecerá el resultado en la términal del cuadro inferior. En ese cuadro aparece la salida de toda sentencia ***print***.

### Problema. Diseña un programa que, a partir del valor del lado de un cuadrado (3 metros), muestre el valor de su perímetro (en metros) y el de su área (en metros cuadrados).

```Python
lado = 3

perimetro = 4 * lado
area = lado * lado

print('El perimetro es:', perimetro, 'metros')
print('El área es:', area, 'metros cuadrados')
```
```
Resp: El perimetro es: 12 metros
Resp: El área es: 9 metros cuadrados
```

Una sentencia ***print*** puede mostrar más de un resultado en una misma línea: basta con separar con comas todos los valores que deseamos mostrar. Cada una de las comas
se traduce en un espacio de separación.

### Problema. Diseña un programa que, a partir del valor de la base y de la altura de un triángulo (3 y 5 metros, respectivamente), muestre el valor de su área (en metros cuadrados).

```Python
base = 3
altura = 5

area_triangulo = (1/2) * base * altura

print(f'El área del triángulo es: {area_triangulo} metros cuadrados')
```
```
Resp: El área del triángulo es: 7.5 metros cuadrados
```
### Problema. Diseña un programa que, a partir del valor de los dos lados de un rectángulo (4 y 6 metros, respectivamente), muestre el valor de su perímetro (en metros) y el de su área (en metros cuadrados).

```Python
lado_menor = 4
lado_mayor = 6

perimetro = 2*lado_menor + 2*lado_mayor
area = lado_menor * lado_mayor

print(f'El perímetro es: {perimetro} metros.')
print(f'El área es: {area} metros cuadrado.')
```
```
Resp: El perímetro es: 20 metros.
Resp: El área es: 24 metros cuadrado.
```

Como se observa en el ejemplo anterior, dentro de la sentencia ***print*** se puede utilizar una ***f-string*** que es una cadena literal que tiene como prefijo la letra **"f"**. Estas cadenas pueden contener campos que se pueden evaluar en tiempo de ejecución. Estos campos se encuentran entre ***llaves {}***.

## Ejecución de programas desde la línea de ordenes Unix.

Una vez has escrito un programa es posible ejecutarlo directamente, sin entrar en el entorno ***Visual Studio Code***. Si invocas al intérprete python seguido del nombre de un fichero desde la línea de ordenes Unix, no se iniciara una sesión con el intérprete interactivo, sino que se ejecutará el programa contenido en el fichero en cuestión. Por ejemplo, si ejecutamos la orden ***python nombre_programa.py*** en la línea de ordenes nos mostrará el resultado del programa ejecutado sin abrir el entorno interactivo. A continuación volverá aparecer el ***prompt*** del intérprete de ordenes Unix pidiendonos nuevas órdenes.

## Entrada / Salida.

Los programas que hemos visto en la sección anterior adolecen de un serio inconveniente: cada vez que quieras obtener resultados para unos datos diferentes deberas editar el fichero de texto que contiene el programa. Por ejemplo, el siguiente programa calcula el volumen de una esfera a partir de su radio, que es de un metro:

```Python
from math import pi

radio = 1
volumen = (4/3) * pi * radio**3

print(volumen)
```
```
Resp: 4.1887902047863905
```

Si deseas calcular ahora el volumen de una esfera de 3 metros de radio, debes editar el fichero que contiene el programa, yendo a la tercera línea y cambiandola para que el programa pase a ser éste:

```Python
from math import pi

radio = 3
volumen = (4/3) * pi * radio**3

print(volumen)
```
```
Resp: 113.09733552923254
```

Y si ahora quieres calcular el volumen para otro radio, vuelta a empezar: abre el fichero con el editor de texto, ve a la tercera línea, modifica el valor del radio y guarda el fichero.

### Lectura de datos de teclado.

Vamos a aprender a hacer que nuestro programa, cuando se ejecute, pida el valor del radio para el que vamos a efectuar los cálculos sin necesidad de editar el fichero de
programa. Hay una función predefinida, ***input***, que hace lo siguiente: detiene la ejecución del programa y espera a que el usuario escriba un texto (el valor del radio, por ejemplo) y pulse la tecla de retorno de carro; en ese momento prosigue la ejecución y la función devuelve una cadena con el texto que tecleó el usuario.

Si deseas que el radio sea un valor flotante, debes transformar la cadena devuelta por ***input*** en un dato de tipo flotante llamando a la función ***float***. La función ***float*** recibirá como argumento la cadena que devuelve ***input*** y proporcionará un número en coma flotante. (Recuerda, para cuando lo necesites, que existe otra función de conversión, ***int***, que devuelve un entero en lugar de un flotante.) Por otra parte, ***input*** es una función y, por tanto, el uso de los paréntesis que siguen a su nombre es obligatorio, incluso cuando no tenga argumentos.

He aquí el nuevo programa:
```Python
from math import pi

texto_leido = input()
radio = float(texto_leido)

volumen = (4/3) * pi * radio**3

print(volumen)
```
```
3
Resp: 113.09733552923254
```

Esta otra versión es más breve:
```Python
from math import pi

radio = float(input())
volumen = (4/3) * pi * radio**3

print(volumen)
```
```
4
Resp: 268.082573106329
```

Al ejecutar el programa desde la línea de órdenes Unix, el ordenador parece quedar bloqueado. No lo esta: en realidad Python está solicitando una entrada de teclado y espera que se la proporcione el usuario. Si tecleas, por ejemplo, el número 3 y pulsas la tecla  de retorno de carro, Python responde imprimiendo en pantalla el valor 113.097335529. Puedes volver a ejecutar el programa y, en lugar de teclear el número 3, teclear cualquier otro valor; Python nos responderá con el valor del volumen de la esfera para un radio igual al valor que hayas tecleado. Pero el programa no es muy elegante, pués deja al ordenador bloqueado hasta que el usuario teclee una cantidad y no informa de qué es exactamente esa cantidad. Vamos a hacer que el programa indique, mediante un mensaje, qué dato desea que se teclee. La función ***input*** acepta un argumento: una cadena con el mensaje que debe mostrar. Modifica el programa para que quede así:

```Python
from math import pi

radio = float(input('Dame el radio:'))

volumen = (4/3) * pi * radio**3

print(volumen)
```
```
Dame el radio: 3
Resp: 113.09733552923254
```

Ahora, cada vez que lo ejecutes, mostrará por pantalla el mensaje ***Dame el radio:*** y detendrá su ejecución hasta que introduzcas un número y pulses el retorno de carro.

### Problema. Diseña un programa que pida el valor del lado de un cuadrado y muestre el valor de su perímetro y el de su área.

```Python
lado = float(input('Dame un valor para el lado: '))

perimetro_cuadrado = 4 * lado
area_cuadrado = round(lado**2, 2)

print(f'El perímetro del cuadrado es: {perimetro_cuadrado} metros')
print(f'El área del cuadrado es: {area_cuadrado} metros al cuadrado')
```
```
Dame un valor para el lado: 1.1
El perímetro del cuadrado es: 4.4 metros
El área del cuadrado es: 1.21 metros al cuadrado
```

### Problema. Diseña un programa que pida el valor de los dos lados de un rectángulo y muestre el valor de su perímetro y el de su área.

```Python
lado_menor = float(input('Dame un valor para el lado menor: '))
lado_mayor = float(input('Dame un valor para el lado mayor: '))

perimetro_rectangulo = 2*lado_menor + 2*lado_mayor
area_rectangulo = (lado_menor*lado_mayor)

print(f'El perímetro del rectángulo es: {perimetro_rectangulo} metros')
print(f'El área del rectángulo es: {area_rectangulo} metros al cuadrado')
```
```
Dame un valor para el lado menor: 1
Dame un valor para el lado mayor: 5
El perímetro del rectángulo es: 12.0 metros
El área del rectángulo es: 5.0 metros al cuadrado
```

### Programa. Diseña un programa que pida el valor de la base y la altura de un triángulo y muestre el valor de su área.

```Python
base = float(input('Dame un valor de la base: '))
altura = float(input('Dame un valor para la altura '))

area_triangulo = (1/2)*base*altura

print(f'El área del triángulo es: {area_triangulo} metros al cuadrado')
```
```
Dame un valor de la base: 10
Dame un valor para la altura: 100
El área del triángulo es: 500.0 metros al cuadrado
```

## Más sobre la sentencia ***print***.

Las cadenas pueden usarse también para mostrar textos por pantalla en cualquier momento a través de sentencias ***print***.

```Python
from math import pi

print('Programa para el cálculo del volumen de una esfera.')

radio = float(input('Dame el un valor para el radio: '))

volumen_esfera = (4/3)*pi*radio**3

print(f'El volumen de la esfera es: {volumen_esfera} metros cubicos')
print('Gracias por utilizar este programa')
```
```
Programa para el cálculo del volumen de una esfera.
Dame el un valor para el radio: 2
El volumen de la esfera es: 33.510321638291124 metros cubicos
Gracias por utilizar este programa
```

#### Problema. El área A de un triángulo se puede calcular a partir del valor de dos de sus lados, a y b, y del ángulo θ que estos forman entre sí con la fórmula A = (1/2) ab sin(θ). Diseña un programa que pida al usuario el valor de los dos lados (en metros), el ángulo que estos forman (en grados), y muestre el valor del área. Ten en cuenta que la función *sin* de Python trabaja en radianes, así que el ángulo que leas en grados deberas pasarlo a radianes sabiendo que π radianes son 180 grados. Prueba que has hecho bien el programa introduciendo los siguientes datos: a = 1, b = 2, θ = 30; el resultado es 0.5.

