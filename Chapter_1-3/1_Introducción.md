# Capítulo I.
## Introducción.

## 1.1 Compotadoras.

El diccionario de la Real Academia define computador electrónico como ***Máquina electrónica, analógica o digital, dotada de una memoria de gran capacidad y de métodos de tratamiento de la información, capaz de resolver problemas matemáticos y lógicos mediante la utilización automática de programas informáticos***. La propia definición nos da indicaciones acerca de algunos elementos básicos del computador:

1. La memoria.
2. Algún dispositivo capaz de efectuar cálculos matemáticos y lógicos.

La ***memoria*** es un gran almacenamiento de información. En la memoria almacenamos todo tipo de datos: valores numéricos, textos, imagenes, etc. El dispositivo encargado de efectuar operaciones matemáticas y lógicas, que recibe el nombre de ***Unidad Aritmético-Lógica (UAL)***, es como una calculadora capaz de trabajar con esos datos y producir, a partir de ellos, nuevos datos (el resultado de las operaciones). Otro dispositivo se encarga de transportar la información de la memoria a la UAL, de controlar a la UAL para que efectue las operaciones pertinentes y de depositar los resultados en la memoria: la ***Unidad de Control***. El conjunto que forman la Unidad de Control y la UAL se conoce por ***Unidad Central de Proceso (o CPU, del inglés ˂˂Central Processing Unit˃˃)***.

![](https://github.com/jm-quintas/IntroduccionProgramacionPython/blob/da768d836be47523ff964e2c47899129e90538e6/Chapter_1-3/Memoria_CPU.png)

Como se muestra en la imagen anterior, cada uno de los cajones que conforman la memoria recibe el nombre de celda (de memoria) y el número que lo identifica es su posición o dirección.

## 1.3. Programas y lenguajes de programación.

- **Programas:** es una secuencia de instrucciones. Las secuencias de instrucciones que el ordenador puede ejecutar reciben el nombre de programas en código de máquina, porque el lenguaje de programación en el que están expresadas recibe el nombre de código de máquina.

- **Un lenguaje de programación** es cualquier sistema de notación que permite expresar programas.

### Lenguajes de programación de alto nivel.

Estos lenguajes están diseñados para ser ***más cercanos al lenguaje humano que al código binario*** que las computadoras entienden directamente. Esto significa que son más fáciles de leer, escribir y mantener para los programadores.

- **Características principales:**

1. **Abstracción:** ocultan la complejidad del hardware, permitiendo a los programadores concentrarse en la lógica del programa.
2. **Portabilidad:** el código escrito en un lenguaje de alto nivel puede, en general, ejecutarse en diferentes tipos de computadoras con pocas o ninguna modificación.
3. **Facilidad de uso:** la sintaxis es más cercana al lenguaje natural, lo que facilita la escritura y comprensión del código.

***¿Por qué usar lenguajes de alto nivel?***

- **Mayor productividad:** al ser más fáciles de aprender y usar, los programadores pueden desarrollar software más rápido.
- **Menor probabilidad de errores:** la sintaxis más clara reduce la posibilidad de errores de programación.
- **Mejor mantenimiento:** el código es más fácil de entender y modificar, lo que facilita la evolución del software a lo largo del tiempo.

### Compiladores e intérpretes.

Los lenguajes de alto nivel se traducen automaticamente a código de máquina, pero has de saber que hay dos tipos diferentes de traductores dependiendo de su modo de funcionamiento: ***compiladores*** e ***intérpretes***.  

Un **compilador** lee completamente un programa en un lenguaje de alto nivel y lo traduce en su integridad a un programa de código de maquina equivalente. El programa de código de maquina resultante se puede ejecutar cuantas veces se desee, sin necesidad de volver a traducir el programa original.  

Un **intérprete** actua de un modo distinto, lee un programa escrito en un lenguaje de alto nivel instrucción a instrucción y, para cada una de ellas, efectua una traducción a las instrucciones de código de maquina equivalentes y las ejecuta inmediatamente. No hay un proceso de traducción separado por completo del de ejecución. Cada vez que ejecutamos el programa con un intérprete, se repite el proceso de traducción y ejecución, ya que ambos son simultaneos.

Por regla general, los intérpretes ejecutaran los programas más lentamente, pués al tiempo de ejecución del código de máquina se suma el que consume la traducción
simultanea. Además, un compilador puede examinar el programa de alto nivel abarcando más de una instrucción cada vez, por lo que es capaz de producir mejores traducciones. Entre los lenguajes interpretados podemos citar Python, BASIC, Perl, Tcl, Ruby, Bash, Java o Lisp. Dentro de los lenguajes compilados mencionamos C, C#, Pascal, C++ o Fortran.

## Python.

Existen muchos otros lenguajes de programación, ***¿por qué aprender Python?*** Python presenta una serie de ventajas que lo hacen muy atractivo, tanto para su uso profesional como para el aprendizaje de la programación. Entre las más interesantes desde el punto de vista didáctico tenemos:  

- ***Python es un lenguaje muy expresivo***, es decir, los programas Python son muy compactos: un programa Python suele ser bastante mas corto que su equivalente en lenguajes como C, (Python llega a ser considerado por muchos un lenguaje de programación de muy alto nivel.
  
- ***Python es muy legible***. La sintaxis de Python es muy elegante y permite la escritura de programas cuya lectura resulta mas fácil que si utilizáramos otros lenguajes de programación.

- ***Python ofrece un entorno interactivo*** que facilita la realización de pruebas y ayuda a despejar dudas acerca de ciertas características del lenguaje.

- El ***entorno de ejecución de Python detecta muchos de los errores*** de programación que escapan al control de los compiladores y proporciona información muy rica
para detectarlos y corregirlos.

- ***Python*** puede usarse como lenguaje ***imperativo procedimental*** o como ***lenguaje orientado a objetos***.

- Posee un ***rico juego de estructuras de datos*** que se pueden manipular de modo sencillo.

Python ha sido diseñado por ***Guido van Rossum*** y está en un proceso de continuo desarrollo por una gran comunidad de desarrolladores. Aproximadamente cada seis meses
se hace pública una nueva versión de Python. Una ventaja fundamental de Python es la gratuidad de su intérprete. Puedes descargar el intérprete de la pagina web [](http://www.python.org). El intérprete de Python tiene versiones para prácticamente cualquier plataforma en uso: sistemas PC bajo Linux, sistemas PC bajo Microsoft Windows, sistemas Macintosh de Apple, etc.

