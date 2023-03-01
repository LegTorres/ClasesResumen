# **CURSO DE PYTHON**

Python es un lenguaje de programación de alto nivel, interpretado cuya filosofía hace hincapié en la legibilidad de su código, se utiliza para desarrollar aplicaciones de todo tipo.​ Fue creado a finales de los años ochenta​ por Guido van Rossum en Stichting Mathematisch Centrum (CWI), en los Países Bajos, como un sucesor del lenguaje de programación ABC.

Se trata de un lenguaje de programación multiparadigma, ya que soporta parcialmente la orientación a objetos, programación imperativa y, en menor medida, programación funcional. Es un lenguaje interpretado, dinámico y multiplataforma.

Administrado por Python Software Foundation, posee una licencia de código abierto, denominada Python Software Foundation License.

**Tabla de Contenido**
- [Estructura Basica de un Programa en Python](#estructura-basica-de-un-programa-en-python)
- [Salida de Datos](#salida-de-datos)
- [Variables y Literales](#variables-y-literales)
- [Entrada de Datos](#entrada-de-datos)
- [Operadores](#operadores)
- [Tipos de Datos](#tipos-de-datos)
- [Condicional IF](#condicional-if)
- [Ciclo FOR](#ciclo-for)
- [Ciclo WHILE](#ciclo-while)
- [Funciones](#funciones)
- [Manejo de Cadenas de Texto](#manejo-de-cadenas-de-texto)
- [Listas](#listas)
- [Diccionarios](#diccionarios)
- [Tuplas](#tuplas)
- [Conjuntos](#conjuntos)
- [Manejo de Ficheros](#manejo-de-ficheros)

## **Estructura Basica de un Programa en Python**
Es buena practica crear una funcion principal denominada `run()` o `main()` que es la que correra nuestro programa, y dentro de ella escribir todo el codigo de nuestra aplicacion.

El entry point o punto de entrada llama la funcion principal de nuestro programa (main() o run()) y a partir de ahi empezara a correr dicha funcion.

~~~py
def run():
   pass


if __name__ == '__main__':
    run()
~~~

## **Salida de Datos**
Mostrar datos en pantalla es muy sencillo en python, y se hace con la funcion `print("Hola Mundo")`. Esta linea escribira un mensaje en pantalla agregandole un salto de linea al final de el texto.  
Podemos especificar otro valor en lugar de un salto de linea al final de la funcion print, agregando el parametro `end="texto al final"` separado del argumento principal separado por una coma.  
Ejemplo:

~~~py
print("Este es un mensaje", end=" ")
print("mostrado en una misma", end=" ")
print("linea")
~~~

Python es capaz de realizar operaciones dentro de la funcion print, para ello solo necesitamos ingresar los valores fuera de las comillas.
Podemos agregar cuantos parametros queramos a una funcion print siempre y cuando vayan separados por comas. Si dichos parametros son cadenas de python los concatenara, separando cada uno por un espacio en blanco. Con la funcion `sep="texto-de-separacion"` podemos reemplazar el espacio en blanco por un texto de nuestra eleccion.

~~~py
print("5", "x", "15", "=", 5*15)
print("salida", "de", "datos", "en", "Python", sep="-")
~~~

## **Variables y Literales**
Un literal es un valor completamente puro o primitivo del lenguaje. Es un elemento cuyo valor se toma de manera literal, como puede ser un numero, una cadena de texto, ect. Por ejemplo, en los casos anteriores, el texto entre comillas dentro de la funcion print se considera un literal.

Para declarar variables en python solo se escribe el nombre de la variable y se le asigna su valor correspondiente.

Python es muy flexible con el tipado de las variables, pues su valor puede ser cambiado por uno de otro tipo sin ningun problema, aunque esta practica no es recomendable pues dificulta la legibilidad de el codigo.

> NOTA: En Python, las constantes no existen. Para guardar un valor constante se utiliza una variable, pero por convencion esta se escribe en mayusculas para indicarle al programador que su valor no debe ser alterado.

> NOTA: Los nombres de las variables NO PUEDEN empezar con un numero, las palabras siempre deben estar en minusculas, y  si estan formadas por varias palabras se separan con un guion bajo (_).

> NOTA:  En python es indistinto utilizar comillas simples(') que comillas dobles("). Si el valor de una variable de texto se escribe entre triple comilla python tomara en cuenta el numero de lineas escritas, incluyendo los saltos de linea.


## **Entrada de Datos**
Para ingresar datos desde la pantalla se utiliza la funcion `input()`, que permite capturar el texto ingresado por medio del teclado.  
Esta funcion devuelve un **string**, por lo que para realizar operaciones con numeros capturados por la funcion input debemos convertirlos al tipo de dato que necesitamos antes.  
Por ejemplo:

~~~py
# Suma de dos numeros
num1 = input("Ingrese el primer numero: ")
num2 = input("Ingrese el segundo numero: ")
print(num1, "+", num2,"=", int(num1) + int(num2))
~~~

Algunas funciones para convertir valores de un tipo de dato en otro son:

|FUNCION |DESCRIPCION                                       |
|--------|--------------------------------------------------|
|int()   |Convierte un valor en un entero                   |
|long()  |Convierte un valor en un entero largo             |
|float() |Convierte un valor en un numero de punto flotante |
|str()   |Convierte un entero o float en cadena de texto    |
|hex()   |Convierte un entero a una cadena hexadecimal      |
|chr()   |Convierte un entero a un caracter                 |
|ord()   |Convierte un caracter en un entero                |
|bin()   |Conmvierte un numero decimal en binario           |

## **Operadores**
Los operadores son símbolos que le indican al intérprete que realice una operación específica, como aritmética, comparación, lógica, etc.  
Algunos tipos de operadores son:

### OPERADORES ARITMETICOS

|OPERADOR| DESCRIPCION                               |
|--------|-------------------------------------------|
|+       | Suma dos numeros                          |
|-       |Resta dos numeros                          |
|*       |Multiplica dos numero                      |
|/       |Divide dos numeros                         |
|%       |Obtiene el modulo de una operacion         |
|**      |Eleva un numero a una determinada potencia |
|//      |Divide dos enteros(dejando un residuo)     |

### OPERADORES LOGICOS

|OPERADOR|DESCRIPCION                                                 |
|--------|------------------------------------------------------------|
|and     |Devuelve True si ambos operandos son True                   |
|or      |Devuelve True si alguno de los operandos es True            |
|not     | Devuelve True si alguno de los operandos False             |
|xor     |Devuelve True unicamente si uno de los dos operandos es True|

### OPERADORES DE COMPARACION O RELACIONALES
       
|OPERADOR |DESCRIPCION       |
|---------|------------------|
|==       |Igual que         |
|!=       |Distindo que      |
|>        |Mayor que         |
|<        |Menor que         |
|>=       |Mayor o igual que |
|<=       |Menor o igual que |

### OPERADORES BITWISE
Los operadores a nivel de bit o bitwise operators son operadores que actúan sobre números enteros pero usando su representación binaria. Recorre ambos números en su representación binaria elemento a elemento, y hace una operación **and**,**or**, **xor**, o **not** con cada uno de ellos. 

|OPERADOR|DESCRIPCION                   |
|--------|------------------------------|
|&       |And bit a bit                 |
|\|      |Or bit a bit                  |
|^       |Xor bit a bit                 |
|~       |Not bit a bit                 |
|>>      |Desplazamiento a la derecha   |
|<<      |Desplazamiento a la izquierda |

En el siguiente ejemplo se estaría haciendo uso del operador **&** comparando el primer elemento de **a** con primer elemento de **b**, sería 1 and 1 por lo que el resultado es 1. Ese valor se almacena en la salida. Continuamos con el segundo 1 and 0 que es 0, tercero 0 and 1 que es 0 y por último 1 and 1 que es 1. Por lo tanto el número resultante es **0b1001**, lo que representa el **9** en decimal.

~~~py
a = 0b1101
b = 0b1011
print(bin(a & b))
# 0b1001
~~~

El operador **>>** y **<<** desplazan todos los bit ***n*** unidades a la derecha o a la izquierda. Por lo tanto es necesario proporcionar dos parámetros, donde el primer es el número que se desplazará o shift y el segundo es el número de posiciones.  
En el siguiente ejemplo tenemos **1000** en binario, por lo que si aplicamos un **>>2**, deberemos mover cada bit 2 unidades a la derecha. Lo que queda por la izquierda se rellena con ceros, y lo que sale por la derecha se descarta. Por lo tanto 1000>>2 será 0010. Es importante notar que Python por defecto elimina los ceros a la izquierda, ya que igual que en el sistema decimal, son irrelevantes.

~~~py
a=0b1000
print(bin(a>>2))
# 0b10
~~~
Si tenemos 0001 y desplazamos <<3, el resultado será 1000.

~~~py
a=0b0001
print(bin(a<<3))
# 0b1000
~~~

> NOTA: Si por ejemplo desplazamos en 4 o en mas unidades nuestra variable a el número de bits que se nos mostrará también se incrementará. Con esto queremos destacar que aunque la entrada sean 4 bits, Python internamente rellena todo lo que está a la izquierda con ceros.

~~~py
a=0b0001
print(bin(a<<10))
# 0b10000000000
~~~

### OPERADORES DE ASIGNACION

|OPERADOR |DESCRIPCION                  |
|---------|-----------------------------|
|=        |Asigna un valor a la variable|
|+=       |Equivale a x = x + valor     |
|-=       |Equivale a x = x - valor     |
|*=       |Equivale a x = x * valor     |
|/=       |Equivale a x = x / valor     |
|%=       |Equivale a x = x % valor     |
|**=      |Equivale a x = x ** valor    |
|//=      |Equivale a x = x // valor    |
|&=       |Equivale a x = x & valor     |
|\|=      |Equivale a x = x \| valor    |
|^=       |Equivale a x = x ^ valor     |
|>>=      |Equivale a x = x >> valor    |
|<<=      |Equivale a x = x << valor    |

### OPERADORES DE PERTENENCIA
Un operador de pertenencia se emplea para identificar pertenencia en alguna secuencia (listas, strings, tuplas).

|OPERADOR |DESCRIPCION                                                           |
|---------|----------------------------------------------------------------------|
|in       |Devuelve True si el valor especificado se encuentra en la secuencia   |
|not in   |evuelve True si el valor especificado no se encuentra en la secuencia |

### OPERADOR DE IDENTIDAD
Un operador de identidad se emplea para comprobar si dos variables emplean la misma ubicación en memoria.

|OPERADOR |DESCRIPCION                                           |
|---------|------------------------------------------------------|
|is       |True si los operandos se refieren al mismo objeto.    |
|is not   |True si los operandos no se refieren al mismo objeto. |

## **Tipos de Datos**
Los 4 tipos de datos basicos que encontraremos en python son:
- Numeros enteros
- Numeros de punto flotantes
- Texto (Cadenas de caracteres)
- Booleanos (True o False)
- Numeros complejos: Los números complejos tienen una parte real y otra imaginaria y cada una de ellas se representa como un float. La parte imaginaria va a estar representada por la letra j en lugar de utilizar la i como en la notación matemática.  
Por ejemplo:

~~~py
# Creando un número complejo
c1 = 4 + 3j
print(c1)
(4+3j)

# sumando dos números complejos
c1 = 2 + 2j
c2 = 1 + 5j
print(c1 + c2)
(3+7j)
~~~

Para conocer el tipo de una variable podemos usar las funciones `type()`que nos devuelve el tipo de el objeto que agreguemos como parametro, y `isinstance()`, que recibe como parametros un objeto, y un tipo, y devolvera True si el objeto es del tipo que se pasa como parametro.

En ocasiones es necesario convertir el tipo de una variable, y para eso contamos con algunas funciones que nos ayudaran a hacerlo. Entre ellas estan:
- **str()**: Devuelve la representación en cadena de caracteres del objeto que se pasa como parámetro.
- **int()**: Devuelve un int a partir de un número o secuencia de caracteres.
- **float()**: Devuelve un float a partir de un número o secuencia de caracteres.
- **comple()**: Devuelve un complex a partir de un número o secuencia de caracteres.

## **Condicional IF**
Un condicional **if**, es una estructura que nos posibilita definir las acciones a ejecutar si se cumple cierta condición y de ese modo modificar la ejecución de tareas en un programa según se necesite.  
La sintaxis del condicional if es la siguiente:

~~~py
#   Programa que nos diga si un numero es igual, menor o mayor que 5.

numero = int(input('Ingrese un numero: '))

if numero > 5:
    print("El numero es mayor que 5")
elif numero == 5:
    print('El numero es igual a 5')
else:
    print('El numero es menor que 5')
~~~
> Es necesario tener en cuenta que el sangrado es muy importante en cualquier estructura de control de python, y en todos los casos la sentencia de condicion debe finalizar con dos puntos (:).

> NOTA: Es opcional encerrar la condicion entre parentesis. Se recomienda en casos donde mas de una condicion esta presente para mejorar la legibilidad.

## **Ciclo WHILE**
Los ciclos **while** son una estructura cíclica, que nos permite ejecutar una o varias líneas de código de manera repetitiva sin necesidad de tener un valor inicial e incluso a veces sin siquiera conocer cuando se va a dar el valor final que esperamos.  
Ejemplo de bucle **while**:

~~~py
# Imrpimir las potencias de 2 entre 1 y 1000.
LIMITE = 1000

contador = 0
potencia_2 = 2 ** contador

while potencia_2 < LIMITE:
    print('2 elevado a ' + str(contador) + ' es igual a: ' + str(2 ** contador))
    contador += 1
    potencia_2 = 2 ** contador

~~~

## **Ciclo FOR**
En Python los bucles **for** funcionan de manera ligeramente diferente a como lo hacen en lenguajes como JavaScript o C. Un bucle for establece la variable iteradora en cada valor de una **lista**, **arreglo** o **cadena** proporcionada y repite el código en el cuerpo del bucle for para cada valor de la variable iteradora.  
Ejemplo:

~~~py
# Imprimir los numeros de un arreglo uno por uno.
for i in [1, 2, 3, 4]:
    print(i) 


# Imprimiendo una a una todas las letras de la palabra 'Fulanito'.
nombre = "Fulanito"
for letra in nombre:
    print(letra)

~~~

Cuando los valores de un arreglo para nuestro bucle for son secuenciales, podemos usar la función `range(inicio, final, paso)`. El argumento **final** establece el numero de iteraciones que nuestro bucle ejecutará. Es preciso tener presente que el bucle siempre llega a la posicion inmediatamente antes del especificado en el parametro de range, por ejemplo range(100) llegaria hasta 99.  
En caso de no especificar el argumento **inicio** Python le asignara el valor de **0**, y nuestro bucle empezará desde esa iteración. Si no se especifica el valor **paso**, será asignado el valor de **1**, por lo que cada iteración irá incrementando de uno en uno por defecto.

~~~py
# Imprimiendo la tabla del 10
for i in range(1,11): 
    print(10 * i)

~~~

Los bucles tambien se pueden interrumpir haciendo uso de las sentencias `break` y `continue`; con la primera 
terminamos la ejecucion del bucle, mientras que con la segunda hacemos que el programa ignore el codigo a continuacion y que salte a la siguiente iteracion sin haberlo ejecutado.

En el siguiente ejemplo hacemos uso de **continue** para que se imprima **i** unicamente cuando los numeros son pares.

~~~py
# Imprimiendo los numeros pares.

for i in range(1001):
    if i % 2 != 0:
        continue

    print(i)
    
~~~

Ahora finalizaremos un bucle de 100 iteraciones cuando llegue al numero 80 con la sentencia **break**.

~~~py
for i in range(0, 100):
    print(i)

    if i == 80:
        break

~~~

> NOTA: La variable que se usa como indice para cada iteracion no necesita ser creada antes de iniciar el bucle.








## **Funciones**
## **Manejo de Cadenas de Texto**
## **Listas**
## **Diccionarios**
## **Tuplas**
## **Conjuntos**
## **Manejo de ficheros**






Informacion complementaria 
https://www.programarya.com/Cursos/Python
