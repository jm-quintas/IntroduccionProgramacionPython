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

## Ejecución de programas desde la línea de ordenes Unix.

Una vez has escrito un programa es posible ejecutarlo directamente, sin entrar en el entorno ***Visual Studio Code***. Si invocas al intérprete python seguido del nombre de un fichero desde la línea de ordenes Unix, no se iniciara una sesión con el intérprete interactivo, sino que se ejecutará el programa contenido en el fichero en cuestión. Por ejemplo, si ejecutamos la orden ***python nombre_programa.py*** en la línea de ordenes nos mostrará el resultado del programa ejecutado sin abrir el entorno interactivo.
