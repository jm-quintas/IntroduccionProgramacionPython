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

la evaluación de expresiones no produce salida por pantalla en un programa. Entonces ¿cómo veremos los resultados que producen nuestros programas? Hemos de aprender a utilizar una nueva sentencia: ***print*** (en inglés, ***imprimir***). En principio, se usa de este modo: ***print*** (expresión).

