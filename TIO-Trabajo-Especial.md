# Python
Python es un lenguaje de programación interpretado cuya filosofía hace hincapié en una sintaxis que favorezca un código legible.
Se trata de un lenguaje de programación multiparadigma, ya que soporta orientación a objetos, programación imperativa y, en menor medida, programación funcional. Es un lenguaje interpretado, usa tipado dinámico y es multiplataforma.

---

### Iteraciones
#### Asignación multiple

Python permite realizar más de una asignación a la misma variable. Una nueva asignación hace que la variable existente se refiera a un nuevo valor y deje de referirse al viejo valor.

    dato = 5
    print dato,
    dato = 7
    print dato

La salida de este programa es **5 7**, ya que la primera vez que se muestra dato su valor es **5**, y la segunda vez su valor es **7**. La coma al final de la primera sentencia **print** impide que se muestre una nueva línea en ese punto, por eso ambos valores aparecen en la misma línea.

#### Actualización de variables

Una de las formas más comunes de asignación múltiple es la actualización, donde el nuevo valor de la variable depende del anterior.

    y = y + 1

Esto significa “tome el valor actual de **y**, súmele uno, y después actualice **y** con el nuevo valor.”

#### Sentencia while

    def cuenta_atras(n):
    while n > 0:
        print n
        n = n-1
    print "comenzar”

El flujo de ejecución de una sentencia **while** es el siguiente:

1. Evalúa la condición, devolviendo False o True.
2.	Si la condición es falsa, se sale de la sentencia while y continúa la ejecución con la siguiente sentencia.
3.	Si la condición es verdadera, ejecuta cada una de las sentencias en el cuerpo y regresa al paso 1


#### Conteo de dígitos

La siguiente función cuenta el número de dígitos en un entero positivo expresado en formato decimal:

    def num_digitos(n):
    contador = 0
    while n:
        contador = contador + 1
        n = n / 10
    return contador

Una llamada a **num_digitos** regresará **3**. 

#### Asignación abreviada

Incrementar una variable es tan común que Python provee una sintaxis abreviada para ello:

    >>> contador = 0
    >>> contador += 1
    >>>  contador
    1
    >>> contador += 1
    >>> contador
    2
    >>>
    
#### Tablas
Aunque una tabla logarítmica ya no es tan útil como antes, todavía constituye un buen ejemplo de iteración. El siguiente programa muestra una secuencia de valores en la columna izquierda y 2 elevado a cada uno de esos valores en la columna derecha:
    
    x = 1
    while x < 13:
        print x, '\t', 2**x
        x += 1

#### Tablas de dos dimensiones
Una tabla de dos dimensiones es una tabla en la que usted elige una fila y una columna y lee el valor de la intersección. Una tabla de multiplicar es un buen ejemplo. Supongamos que desea mostrar una tabla de multiplicar para los valores del 1 al 6.

    i = 1
    while i <= 6:
        print 2 * i, '   ',
        i += 1
    print

La salida del programa es:

    2      4      6      8      10     12

#### Encapsulamiento y generalización

El encapsulamiento es el proceso de envolver segmentos de código en una función, permitiéndole aprovechar todos los beneficios de las funciones.

    def muestra_multiplos(n):
        i = 1
        while i <= 6:
            print n * i, '\t',
            i += 1
       print

Si hacemos una llamada a esta función con el número 2 como argumento obtenemos, como antes, la misma salida. Con el número 3 como argumento la salida es:

    3      6      9      12     15     18

 ---

### Funciones

En el contexto de la programación una función es una secuencia de sentencias que ejecuta una operación deseada y tiene un nombre. Esta operación se especifica en una definición de función. La sintaxis para una definición de función en Python es:

    def NOMBRE( LISTA DE PARAMETROS ):
        SENTENCIAS

#### La función print()
En Python, para mostrar texto o variables hay que utilizar la función **print()**.
El texto a mostrar se escribe como argumento de la función:

    print("Hola")
    Hola

Las cadenas se pueden delimitar tanto por comillas dobles (") como por comillas simples (').

    print('Hola')
    Hola

#### Flujo de ejecución
Con el fin de asegurar que una función se defina antes de su primer uso usted tiene que saber el orden en el que las sentencias se ejecutan, este orden de ejecución se denomina flujo de ejecución.
La ejecución siempre empieza con la primera sentencia del programa. Las sentencias se ejecutan una a una, desde arriba hacia abajo.


#### Parámetros, argumentos y la sentencia import
La mayoría de las funciones requieren argumentos, los valores que controlan la manera en que la funciones trabajan. Por ejemplo, si usted quiere encontrar el valor absoluto de un número, tiene que indicar cuál es el número. Python tienen una función integrada en su biblioteca de funciones para calcular el valor absoluto:

    >>> abs(5)
    5
    >>> abs(-5)
    5

En este ejemplo los argumentos de la función **abs** son 5 y -5.

Algunas funciones necesitan más de un argumento. Por ejemplo la función de biblioteca **pow** toma dos argumentos, la base y el exponente. Dentro de la función, los valores que se pasan se asignan a variables llamadas parámetros.

    >>> pow(2, 3)
    8
    >>> pow(7, 4)
    2401

La línea de comandos de Python nos proporciona una forma apropiada de probar nuestras funciones. Podemos usar la sentencia **import** para traer las funciones a la sesión del intérprete de Python. Para saber cómo funciona considere que la función muestra_doble está definida en un guión llamado cap03.py. Podemos probarla interactivamente importándola en nuestra sesión de la línea de comandos de Python:

    >>> from cap03 import *
    >>> muestra_doble('Basura')
    Basura Basura
    >>> muestra_doble(5)
    5 5
    >>> muestra_doble(3.14159)
    3.14159 3.14159

#### Composición
Asi como las funciones matemáticas, las funciones de Python pueden componerse, esto es, puede usar el resultado de una función como entrada de otra.
    
    >>> muestra_doble(abs(-7))
    7 7
    >>> muestra_doble(max(3, 1, abs(-11), 7))
    11 11

**abs(-7)** produce 7, el cual es ahora el argumento de la función **muestra\_doble**. En el segundo ejemplo tenemos dos niveles de composición puesto que primero se evalúa **abs(-11)** que produce 11, y luego se evalúa **max(3, 1, 11, 7)** que da como resultado 11; finalmente la función **muestra\_doble(11)** muestra el resultado.

---
#### Modo interactivo 
El intérprete de Python estándar incluye un modo interactivo en el cual se escriben las instrucciones en una especie de intérprete de comandos: las expresiones pueden ser introducidas una a una, pudiendo verse el resultado de su evaluación inmediatamente, lo que da la posibilidad de probar porciones de código en el modo interactivo antes de integrarlo como parte de un programa. Esto resulta útil tanto para las personas que se están familiarizando con el lenguaje como para los programadores más avanzados

---

Repositorio [GitHub](https://github.com/GastonIglesias/Trabajo-Especial-TIO)




    









































 
