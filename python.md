# **CURSO DE PYTHON**

Python es un lenguaje de programación de alto nivel, interpretado cuya filosofía hace hincapié en la legibilidad de su código, se utiliza para desarrollar aplicaciones de todo tipo.​ Fue creado a finales de los años ochenta​ por Guido van Rossum en Stichting Mathematisch Centrum (CWI), en los Países Bajos, como un sucesor del lenguaje de programación ABC.

Se trata de un lenguaje de programación multiparadigma, ya que soporta parcialmente la orientación a objetos, programación imperativa y, en menor medida, programación funcional. Es un lenguaje interpretado, dinámico y multiplataforma.

Administrado por Python Software Foundation, posee una licencia de código abierto, denominada Python Software Foundation License.

**TABLA DE CONTENIDO**

**Conceptos Básicos de Python**
- [Estructura Basica de un Programa en Python](#estructura-basica-de-un-programa-en-python)
- [Salida de Datos](#salida-de-datos)
- [Variables y Literales](#variables-y-literales)
- [Entrada de Datos](#entrada-de-datos)
- [Operadores](#operadores)
- [Tipos de Datos](#tipos-de-datos)
- [Condicional IF](#condicional-if)
- [Ciclo WHILE](#ciclo-while)
- [Ciclo FOR](#ciclo-for)
- [Listas y Matrices](#listas-y-matrices)
- [Tuplas](#tuplas)
- [Diccionarios](#diccionarios)
- [Conjuntos (Sets y Frozensets)](#conjuntos-set-y-frozenset)
- [Funciones](#funciones)
- [Uso de \*args y \*\*kwargs en Funciones](#uso-de-args-y-kwargs-en-funciones)
- [Manejo de Cadenas de Texto](#manejo-de-cadenas-de-texto)
- [Manejo de Datos Numericos](#manejo-de-datos-numericos)
- [Numeros Aleatorios]()
- [Manejo de Ficheros](#manejo-de-ficheros)

**Programacion Orientada a Objetos**
- [Clases y Objetos](#clases-y-objetos)
- [Herencia](#herencia)
- [Encapsulamiento](#encapsulamiento)
- [Polimorfismo](#polimorfismo)
- [Abstraccion](#abstraccion)

**Conceptos Avanzados**
- [Manejo de Excepciones](#manejo-de-excepciones)
- [Funciones Lambda](#funciones-lambda)
- [Funciones Map y Filter](#funciones-map-y-filter)
- [Modulos y Paquetes](#modulos-y-paquetes)
- [Interfaces Graficas con Tkinter](#interfaces-graficas-con-tkinter)
- [Decoradores](#decoradores)

**Manejo de Bases de Datos**
- [SQLite](#sqlite)

# CONCEPTOS BASICOS DE PYTHON

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
# (4+3j)

# sumando dos números complejos
c1 = 2 + 2j
c2 = 1 + 5j
print(c1 + c2)
# (3+7j)
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

Otro ejemplo utilizando la sentencia **continue** es el siguiente donde verificamos si un numero ingresado es primo o no:

~~~py
contador = 0
numero = int(input('Ingresa un numero: '))

for i in range(1, numero + 1):
    if i == 1 or i == numero:
        continue
    if numero % i == 0:
        contador += 1

if contador == 0:
    print('Es primo')
else:
    print('No es primo')

~~~

Ahora finalizaremos un bucle de 100 iteraciones cuando llegue al numero 80 con la sentencia **break**.

~~~py
for i in range(0, 100):
    print(i)

    if i == 80:
        break

~~~

> NOTA: La variable que se usa como indice para cada iteracion (por convencion se usa la letra **i**) no necesita ser creada antes de iniciar el bucle.

## **Listas y Matrices**

### ***Listas***
Las **listas** (conocidos en otros lenguajes de programacion como **arrays o vectores**) pertenecen a un conjunto llamado **estructuras de datos**, que nos permiten guardar varios valores dentro de una misma variable. Estas listas son similares a **matrices** (o arrays) que se encuentran en otros lenguajes. Sin embargo, en Python se manejan como variables con muchos elementos.  
En Python, los elementos de una lista no tienen porque ser del mismo tipo.

Declaracion de una lista:  

~~~py
# Creando una lista vacia
listaVacia = []

# Creando una lista con sus valores
lista = [1, 2, "Hola", True, 2.25]
~~~

Para imprimir la lista completa no necesitamos escribir los corchetes.  
Ejemplo:

~~~py
palabras = ['Hola', 'Como', 'Estas']

print(palabras)
~~~

~~~
RESULTADO:

['Hola', 'Como', 'Estas']
~~~

> Para acceder a un elemento especifico de la lista lo hacemos escribiendo el indice dentro de los corchetes.

Por ejemplo:
~~~py
numeros = [1, 2, 3, 4, 5]

# Imprimiendo el numero almacenado en el indice 2.
print(numeros[2])
~~~

Para manipular los elementos dentro de las listas podemos usar las siguientes funciones:
- `.append()`:  
Agrega un elemento que usemos como parametro al final de la lista.
- `.pop()`:  
Elimina un elemento dentro de la lista. Recibe como parametro el indice del elemento a eliminar.
- `.remove()`:  
Remueve el primer elemento que encuentre dentro de la lista que coincida con el valor que hayamos pasado como parametro. 

Agregando elementos con la funcion `append()` y concatenado listas:

~~~py
numeros = []
# Agregando un elemento al final de la lista.
numeros.append(10)

# Concatenado una lista con otra existente
numeros =  mumeros + [15, 20, 25, 30]
~~~

Eliminando elementos de la lista:

~~~py
palabras = ['Hola', 'Como', 'Estas', 'Este', 'Dia', '?', '?']

# Eliminando el ultimo simbolo de interrogacion.
palabras.pop(6)

# Eliminando la palabra Hola.
palabras.remove('Hola')
~~~

Para recorrer una lista puedes hacerlo de dos maneras; la primera es por medio de un **ciclo for**, y la segunda por medio de un **ciclo while**

~~~py
edades = [20, 41, 6, 18, 23]

# Recorriendo los elementos
for edad in edades:
    print(edad)

# Recorriendo los índices
for i in range(len(edaded)):
    print(edaded[i])

#Recorriendo la lista con while conociendo su longitud con la funcion len().
indice = 0

while indice < len(edaded):
    print(edades[indice])
    indice += 1
    
~~~

Si queremos imprimir los elementos de la lista en orden inverso lo podemos hacer de la siguiente manera:

~~~py
numero = [1, 2, 3, 4, 5]

print(numero[::-1])
~~~

### ***Matrices***
Las **Matrices**, tambien conocidas como **tablas** o **listas de listas** son listas bidimendionales cuyos datos estan almacenados en filas y columnas. Basicamente es una lista cuyos items son en si otras listas. Cada elemento de la lista madre es una **fila**, y los elementos dentro de esta fila son las columnas.  

Por ejemplo, si queremos una matriz en la cual la primera fila almacene los valores de 8, 14 y -6, la segunda 12, 7, 4, y la terrcera -11, 3, 21, su declaracion seria de la siguiente manera:

~~~py
M1 = [
    [8,14,-6],
    [12,7,4],
    [-11,3,21]
]

## Imprimiendo la matriz.
print(M1)

# RESULTADO:
# 
# [[8, 14, -6], [12, 7, 4], [-11, 3, 21]]

~~~

Para acceder a un elemento dentro de una matriz lo hacemos por medio de sus indices, al igual que en una lista, pero utilizando doble indice; el primer de ellos hace referencia al elemento de la lista matriz(fila), y el segundo al elemento dentro de la lista hija(columna).

~~~py
personas = [
    ['Maria', 'Jose'],
    [21, 33]
]

# Accediendo al nombre de Maria, fila 0, columna 0.
print(personas[0][0])

# Accediendo al ultimo elemento de la fila 0, en este caso Jose.
print(personas[0][-1])
~~~
Para recorrer una matriz, al igual que con las listas podemos recurrir a los ciclos **for** y **while** de manera anidada.  
Por ejemplo:

~~~py
personas = [
    ['Maria', 'Jose'],
    [21, 33]
]

# Recorriendo la totalidad de nuestra tabla
for fila in personas:
    for columna in fila:
        print(columna)


# Recorriendo los indices de cada lista dentro de la tabla:
for i in range(len(personas)):
    for j in range(len(personas[i])):
        print(personas[i][j])

# Haciendo uso del ciclo While:
fila = 0
while fila < len(personas):
    columna = 0
    while columna < len(personas[fila]):
        print(personas[fila][columna])
        columna += 1
    fila += 1
~~~

Podemos modificar el contenido de las matrices utilizando los mismos metodos de las listas simples, lo unicon que debemos hacer es especificar la fila en la que deseamos hacer la modificacion a traves de su indice.  
Para el caso anterior podemos usar el siguiente ejemplo:

~~~py
nombre = 'Jesus'
edad = 33

personas[0].append(nombre)
personas[1].append(edad)
~~~

## **Tuplas**
Las **tuplas** son unas estructuras similares a las listas, pero a diferencia de estas que son dinamicas, las tuplas son estaticas, por lo que no podemos modificar su contenido una vez que se hayan declarado. Debido a que su contenido no se puede cambiar. Por lo general las tuplas se utilizan para representar conceptos del mundo real. Las tuplas al igual que las listas pueden ser anidadas, y contener otras tuplas en su interior.
Para declarar una tupla se encierra los elementos que la conformaran entre parentesis separados por comas.  
Ejemplo:

~~~py
tupla_simple = (1,2,3)

tupla_anidada = (1, 2, (a, b, c), 3)
~~~
> NOTA: Las tuplas tambien pueden declararse sin necesidad de los corchetes, pero siempre separando sus elementos por comas.

Podemos convertir listas en tuplas con la funcion `tuple()` y tambien convertir tuplas en listas por medio del metodo `list()`. Una vez convertida en una lista podemos modificar sus valores.

~~~py
tupla = 1,2,3,4,5

# Imprimiendo el tipo de dato de la variable tupla.
print(tupla)
print(type(tupla))

# Convirtiendo la tupla en una lista
tupla = list(tupla)
tupla.append(6)
print(tupla)
print(type(tupla))
~~~

Para acceder a los elementos de una tupla se hace igual que a los de una lista, y de la misma forma se puede usar ciclos **for y while** para recorrerlos.

Algunos metodos utiles para trabajar con tuplas son los siguientes:  

- `cont()`:  
Cuenta el número de veces que el objeto pasado como parámetro se ha encontrado en la lista.

~~~py
tupla = (1, 1, 1, 3, 5)

# Imprimiendo cuantas veces se encuentra el numero uno dentro de la tupla.
print(tupla.count(1)) 

# Resultado: # 3
~~~

Los valores individuales de una tupla pueden ser recuperados asignando la tupla a las variables respectivas. Esto se llama **desempaquetar la tupla**.  
Ejemplo:

~~~py
persona = ("Fulano", "De Tal", 33)

# Desempaquetando la tupla en tres variables.
nombre, apellido, edad = persona

print('Nombre: ', nombre, ', Apellido: ', apellido, ', Edad: ', edad)

# Resultado:
# Nombre:  Fulano , Apellido:  De Tal , Edad:  33
~~~

## **Diccionarios**
Los **diccionarios** son unas **estructuras de datos de llaves y valores** y a diferencia de las listas no vamos a acceder a los elementos a traves de su indice, sino a traves de sus llaves.

Para declarar un diccionario es muy similar a como se declara una lista, pero los elementos se colocan dentro de **llaves** en lugar de entre corchetes, y cada elemento esta constituido por una **clave** y un **valor**, que van separados por dos puntos, y cada elemento del diccionario debe separarse por **comas**.  
Para acceder a un elemento de un diccionario se hace a traves de la clave, y este va entre corchetes, como las listas. Tambien puede usarse el metodo **.get()** para obtener el valor de un elemento del diccionario. Este recibe como parametro el nombre de la clave.

Ejemplo:

~~~py
usuario = {
    'nombre' : "Fulano",
    'edad' : 32,
    'nacionalidad' : "EE.UU.",
}

# Obteniendo el valor asociado a la clave nombre:
print(usuario["nombre"]) 
print(usuario.get("nombre"))
~~~

> No es necesario respetar la identacion cuando se trabaja con diccionarios, pero si es una buena practica hacerlo para que el codigo sea mas facil de leer. 

Se puede recorrer un diccionario con un ciclo for. Para ayudarnos podemos usar una serie de metodos que nos permiten obtener los elementos de un diccionario. Estos metodos son:

- **.keys()**:  
Este metodo nos devuelve las llaves del diccionario.
- **.values()**:  
Nos devuelve los valores del diccionario. 
- **.items()**:  
Nos devuelve tanto las claves como los valores de un diccionario.

por ejemplo:
~~~py
# Imprimiendo las llaves del diccionario
for llave in diccionario.keys():
    print(llave)

# Imprimiendo los valores del diccionario
for valor in diccionario.values():
    print(valor)

# Imprimiendo ambos con el metodo .items
for llave, valor in diccionario.items():
    print(llave)
    print(valor)

# Accediendo a los elementos del diccionario de forma tradicional.
for llave in diccionario:
    print(llave, ": ", diccionario[llave], sep='')
~~~   

## **Conjuntos (Set y Frozenset)**

### ***Set***
Tambien conocidos como **sets** son un conjunto es una colección de elementos **no ordenada** que no se repiten. Estas características hacen que los principales usos de esta clase sean conocer si un elemento pertenece o no a una colección y eliminar duplicados de un tipo secuencial (list, tuple o str).

Además, esta clase también implementa las típicas operaciones matemáticas sobre conjuntos: unión, intersección, diferencia. Su contenido puede ser mutable, por lo tanto podemos agregar, modificar o eliminar elementos. Podemos agregar elementos de cualquier tipo, entre ellos tuplas, pero no podemos almacenar ni **listas** ni **diccionarios**.

Para declarar un conjunto lo hacemos encerrando los valores entre **llaves** al igual que con un diccionario, pero a diferencia de este ultimo no se utiliza una clave.  
Ejemplo de declaracion de un conjunto:

~~~py
conjunto = {'Python', 'Go', ('C', 'C++', 'C#'), 'JavaScript'}

print(conjunto)

# RESULTADO:
#
# {('C', 'C++', 'C#'), 'Python', 'JavaScript', 'Go'}
~~~

> NOTA: Los elementos repetidos seran eliminados al momento de crear el conjunto.

Los elementos que se pueden añadir a un conjunto deben ser de tipo hashable. Un objeto es hashable si tiene un valor de hash que no cambia durante todo su ciclo de vida. En principio, los objetos que son instancias de clases definidas por el usuario son hashables. También lo son la mayoría de tipos inmutables definidos por Python.

Se puede convertir diferentes tipos de datos en conjuntos con la funcion `set()`. Tambien se usa la funcion set() para crear conjuntos vacios, ya que al utilizar los signos de llaves sin nada en su interior estamos creando un diccionario vacio y no un conjunto.

~~~py
palabra = "hola a todos"

mi_set = set(palabra)

conjunto_vacio = set()

print(mi_set)

# Resultado:
#
# {'d', 'o', 'l', 'a', ' ', 's', 'h', 't'}
~~~

Dado que los conjuntos son colecciones desordenadas, en ellos no se guarda la posición en la que son insertados los elementos como ocurre en los tipos list o tuple. Es por ello que no se puede acceder a los elementos a través de un índice. Sin embargo, sí se puede acceder y/o recorrer todos los elementos de un conjunto usando un bucle **for**:

~~~py
conjunto = {'Python', 'Go', ('C', 'C++', 'C#'), 'JavaScript'}

for e in conjunto:
    print(e)

# RESULTADO:
#
# Go
# Python
# JavaScript
# ('C', 'C++', 'C#')
~~~

Para saber si un elemento esta dentro de un conjunto se utiliza el operador `in`. Este devolvera **True** o **False** si el elemento esta o no en el conjunto.

Ejemplo:

~~~py
conjunto = {'Python', 'Go', ('C', 'C++', 'C#'), 'JavaScript'}

print('Python' in conjunto)
print('Pearl' in conjunto)

# RESULTADO:
#
# True
# False

~~~

### ***Frozenset***
La principal diferencia es que set es mutable, por lo que después de ser creado, se pueden añadir y/o eliminar elementos del conjunto, como veremos en secciones posteriores. Por su parte, frozenset es inmutable y su contenido no puede ser modificado una vez que ha sido inicializado.
Para declarar un frozenset lo hacemos con la funcion frozenset() pasando una lista de calores como parametro.  
Por ejemplo:

~~~py
fs = frozenset([1, 2, 3])
print(fs)       

# RESULTADO:
# 
# frozenset({1, 2, 3})
~~~

El único modo en Python de tener un conjunto de conjuntos es utilizando objetos de tipo frozenset como elementos del propio conjunto.  
Ejemplo:

~~~py
mi_frozenset1 = frozenset([1, 2])
mi_frozenset2 = frozenset([3, 4])
mi_set = {mi_frozenset1, mi_frozenset2}
print(mi_set)

# RESULTADO:
# 
# {frozenset({3, 4}), frozenset({1, 2})}
~~~

### ***Metodos***
Algunos metodos para trabajar con conjuntos son los siguientes:

- `.add()`:  
Añade un elemento a un conjunto, simpre y cuando dicho elemento no exista ya en el conjunto.
-`.update()`:  
Añade un elemento al conjunto. Puede tomar como argumento una lista, tupla, string, conjunto o cualquier objeto de tipo iterable.
- `.discard()`:  
Elimina el elemento que hayamos pasado como parametro.
- `.remove()`:  
Tambien elimina el elemento del conjunto, pero a diferencia de discard(), si el elemento no existe lanza la excepcion **KeyError**.
- `.pop()`:  
Devuelve un elemento aleatorio del conjunto y lo elimina. Si el conjunto esta vacio devuelve un **KeyError**.
- `.clear()`:  
Elimina todos los elementos del conjunto.

~~~py
numeros = {1, 2, 3, 4, 5, 6}
print(numeros)

# Agregando elementos al conjunto.
numeros.add(7)
print(numeros)

# Agregando elementos al conjunto con el metodo .update()
numeros.update([8,9,10,11,12])
numeros.update((13, 14, 15))
print(numeros)

# Eliminando elementos del conjunto con .discard(), .remove() y .pop().
numeros.discard(11)
numeros.remove(12)
print(numeros)

print(numeros.pop())
print('numero eliminado con pop', numeros)

# RESULTADO:
#
# {1, 2, 3, 4, 5, 6}
# {1, 2, 3, 4, 5, 6, 7}
# {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15}
# {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 13, 14, 15}
# 1
# numero eliminado con pop {2, 3, 4, 5, 6, 7, 8, 9, 10, 13, 14, 15}
~~~

## **Funciones**
Las funciones son un conjunto de procedimiento encapsulados en un bloque, usualmente reciben parámetros, cuyos valores se utilizan para efectuar operaciones y **opcionalmente** retornar un valor.

Una función pueden tener cualquier cantidad de parametros. Si una función tiene más de un parámetro cada uno de ellos debe ir separado por una coma.

Una funcion puede devolver un valor con la instruccion **return**. El codigo escrito despues del return no se ejecutara. En caso de que una funcion devuelva mas de un valor estos deben ir separados por **comas**. Tambien pueden escribirse diversos valores a retornar entre condicionales.

Para declarar una funcion se escribe la palabra reservada **def** delante del nombre de la funcion seguido de parentesis entre los cuales se escribira los argumentos y finalizando con dos puntos. Es importante respetar las identaciones al igual que con las demas estructuras en Python.  
Ejemplo:

~~~py
def caracter(n):
    if n == 0:
        return 'a'

    return 'x' 
~~~

> NOTA: Una función puede llamar a otra dentro de sí misma o incluso puede ser enviada como argumento de otra.

Es posible hacer uso de la sentencia return sin devolver ningun valor, en ese caso se utiliza para interrumpir la ejecucion de la funcion en ese punto.

~~~py
def procedimiento(n, nombre):
    if(n == 0):
        print("hola", nombre)
        return
    print("adiós", nombre)
~~~

Para dejar un espacio en una funcion o en una estructura de control que no quieres programar en este momento puedes escribir la palabra reservada `pass` que le hara saber a python que escribiras ese codigo despues.

~~~py
def miFuncion():
    pass
~~~

## **Uso de \*args y \*\*kwargs en Funciones**
Las palabras **\*args (Argumentos Arbitrarios)** y **\*\*kwargs (Key Words Arguments)** nos permiten pasar un numero variable de argunmentos a una funcion.  
Tanto \*args como \*\*kwargs son nombres utilizados por convencion entre los programadores, pero el uso de estos nombres no es obligatorio. Los que si es necsario respetar es el simbolo de asteriscos simples o dobles delante del nombre del argumento.

Ejemplo de **\*args**:

~~~py
# Creando una funcion que devuelva el numero mayor de una lista

def maximo(*args):
    maximo = args[0]
    for numero in args[1:]:
        if numero > maximo:
            maximo = numero
    return maximo


print(maximo(1, 2, 3, 4, 5))

# La funcion devolvera el numero 5
~~~

Este tipo de argumentos son muy utiles cuando, por ejemplo, tenemos argumentos que dependen de otros argumentos para que nuestra funcion se comporte de una manera o de otra.  
Por ejemplo, si queremos un programa que nos descargue un archivo de audio o video podriamos especificar los argumentos con base en tipo de archivo que queremos descargar. 

~~~py
def descargaArchivos(tipo, *args):
    # Comprobando el numero de argumentos arbitrarios
    numArgs = len(args)
    if tipo == "video":
        if numArgs == 0:
            print(f"Formato: {tipo}.")
        elif numArgs == 1:
            print(f"Formato: {tipo}. Resolucion: {args[0]}.")
        elif numArgs == 2:
            print(f"Formato: {tipo}. Resolucion: {args[0]}. FPS: {args[1]}.")
    elif tipo == "audio":
        print(f"Formato: {tipo}.")
    else:
        print(f"El formato {tipo} no es valido.")

    
descargaArchivos("video")
descargaArchivos("video", 720)
descargaArchivos("video", 1080, 60)
descargaArchivos("audio")
descargaArchivos("imagen")
~~~

~~~
RESULTADO EN PANTALLA:

Formato: video
Formato: video. Resolucion: 720
Formato: video. Resolucion: 1080 FPS: 60
Formato: audio
El formato imagen no es valido
~~~

> NOTA: La diferencia entre usar una lista de argumentos y la sentencia \*args es mas bien una cuestion de notacion. Ambas funcionaran de manera muy parecida pero en el caso de la lista debera encerrarse los elementos dentro de corchetes al momento de llamar la funcion.  
Ejemplo:

~~~py
def maximo(numeros):
    maximo = numeros[0]
    for numero in numeros[1:]:
        if numero > maximo:
            maximo = numero
    return maximo


print(maximo([1, 2, 3, 4, 5]))
~~~

> NOTA: Los argumentos \*args se pueden manejar como una **lista**

Los argumentos **\*\*kwargs** tambien conocidos como argumentos de palabras clave funcionan de manera muy similar a los argumentos arbitrarios, pero a diferencia de los anteriores estos permiten colocar los argumentos de la funcion de manera desordenada, accediendo al ellos por medio de una palabra clave.   
Por ejemplo:

~~~py
def imprimirKwargs(**kwargs):
    print("\n")
    print("Los atributos del personaje son los siguientes: ")
    for clave, valor in kwargs.items():
        print(f"{clave} ---> {valor}")


imprimirKwargs(nombre="Leonidas", clase="Guerrero", Raza="Humano", clan="Espartano")
~~~

~~~
RESULTADO EN PANTALLA:

Los atributos del personaje son los siguientes: 
nombre ---> Leonidas
clase ---> Guerrero
Raza ---> Humano
clan ---> Espartano
~~~

> NOTA: Los argumentos \*\*kwargs se pueden manejar como un **diccionario**

Los diferentes tipos de argumentos (Obligatorios, \*args y \*\*kwargs) se pueden combinar en una misma funcion. Esto es algo muy comun en las diferentes librerias de python.  
Ejemplo:

~~~py
def crearPersonaje(nombre, *args, **kwargs):
    descripcion = f"{nombre.upper()} \n\n"
    descripcion += "DESCRIPCION\n\n"
    for clave, valor in kwargs.items():
        descripcion += f"- {clave} ---> {valor}\n"
    descripcion += "\n\nHABILIDADES\n\n"
    for skill in args:
        descripcion += f"- {skill}\n"
    return descripcion


personaje = crearPersonaje("Dandelion", "Ataque Fuerte", "Bola de Fuego", "Magia Oscura", clase="mago", raza="No Muerto", mascota="Serpiente")

print(personaje)
~~~

~~~
RESULTADO EN PANTALLA:

DANDELION 

DESCRIPCION

- clase ---> mago
- raza ---> No Muerto
- mascota ---> Serpiente


HABILIDADES

- Ataque Fuerte
- Bola de Fuego
- Magia Oscura
~~~

## **Manejo de Cadenas de Texto**
Algunas funciones útiles para manipular cadenas de texto son las siguientes: 

|Funcion          | Hace                                                                          |
|-----------------|-------------------------------------------------------------------------------|
|`.upper()`       | Cambia todo el texto a mayusculas.                                            |
|`.capitalize()`  | Cambia la primera letra a mayuscula.                                          |
|`.lower()`       | Cambia toda el texto a minuscula.                                             |
|`.strip()`       | Elimina los espacios entre caracteres.                                        |
|`.replace(x, y)` | Reemplaza **x** por **y**.                                                    |
|`len(x)`         | Devuelve la longitud de x.                                                    |
|`.split(sep='')` | Divide una cadena en una lista de palabras separandolas por el valor de sep.  |
|`x.join(a)`      | Retorna un string de todos los elementos de un iterable, separados por **x**. |
|`a.isnumeric()`  | Retorna True si **a** el contenido de un String es numerico                   |

> NOTA sobre `.split(sep='')`: Si no se pasa el argumento `sep`, o el valor de este es `None` la cadena se dividira en cada una de sus palabras separadas por espacios, y estos se eliminaran, ademas de cualquier caracter que se imprima en blanco como `\n, \t` o `\r` Ademas, si se especifica el argumento sep, los delimitadores que aparezcan juntos no se agrupan. En su lugar, se crea como token una **cadena vacía** `''`.  
Ademas podemos utilizar el argumento `maxsplit` para establecer un limite a el numero de divisiones a realizar.

~~~py
# Dividiendo dos veces la cadena saludo usando como punto de 
# division un espacio en blanco, lo que produce
# una lista con tres secciones.
saludo = 'Hola que tal como estas este dia?' 

palabras = saludo.split(sep=' ', maxsplit=2)
print(palabras)

# RESULTADO:
#
# ['Hola', 'que', 'tal como estas este dia?']


~~~

Las cadenas de texto se pueden manipular de manera similar a las listas a traves de sus indices. Para eso lo hacemmos de la siguiente manera:

|Nomenclatura         | Hace                                                           |
|---------------------|----------------------------------------------------------------|
|`cadena[indice]`     | Caracter en la posicion indice.                                |
|`a[x:y]`             | Caracteres de **a** desde indice **x** hasta indice **y - 1**. |
|`a[x:y:z]`           | **z** determina cuantas iteraciones intercalara.               | 
|`a[::-z]`            | Orden de caracteres invertidos cada **z** iteraciones.         | 

> NOTA sobre `a[x:y]`:  La cadena se detiene justo en el caracter inmediatamente antes del indice **y**, y no sera incluido, por lo tanto, si queremos tomar en cuenta ese caracter tenemos que incrementar en **1** el valor de **y**. De esta forma, en una cadena de 5 elementos, si queremos que la operacion devuelva hasta el caracter final(en este caso, el caracter en el indice `4`) tendremos que especificar el numero `5`.  
Se puede obviar **x** y **y** y dejar un espacio vacio.

> NOTA sobre `a[x:y:z]`: A manera de ejemplola en la variable `cadena = 'ABCDEFGHIJ'` la funcion `cadena[0:10:2]` nos devolveria `'ACEGI'` ya que iria imprimiendo los caracteres de la cadena de dos en dos.

> NOTA sobre `a[::-z]`: Al ser un numero negativo empezara a recorrer la cadena desde el ultimo elemento, y dependiendo de el numero que especifiquemos tomara el caracter en la iteracion correspondiente. Por ejemplo, si tenemos la cadena `numeros='012345'` la funcion `print(numeros[::-2])` devolvera `531`. Al igual que con los numeros positivos podemos establecer un inicio y fin con los dos primeros valores entre dos puntos, pero el caracter ubicado en el indice del  segundo valor, si es espe en 

~~~py
# Programa que verifique si una palabra es palindromo
palabra = input('Escribe una palabra: ')

palabra = palabra.replace(' ', '')
palabra = palabra.lower()

if palabra == palabra[::-1]:
    print('La palabra ' + palabra + ' es un palindromo.')
else:
    print('La palabra ' + palabra + ' NO es un palindromo.')    
~~~

Para concatenar cadenas de texto podemos utilizar el operador `+`. Y podemos repetir una cadena un determinado numero de veces usando el operador `*`
~~~py
palabra = 'Hola ' * 5
print(palabra)

# RESULTADO:
#
# Hola Hola Hola Hola Hola 
~~~

Si se escribe el contenido de una variable de texto entre triple comilla python tomara en cuenta el numero de lineas que se escriba, incluyendo los saltos de linea.  
Por ejemplo:

~~~py
palabra = """
    Esta es una cadena de texto
    formada por multiples lineas
    !!!!!
"""

print(palabra)

# RESULTADO:

# Esta es una cadena de texto
# formada por multiples lineas
# !!!!!
~~~


## **Manejo de Datos Numericos**
Ademas de los operadores para asignar o comparar valores numericos existen muchas funciones que nos facilitan el trabajar con enteros o decimales. Algunas de las funciones y nomenclaturas son:

|Funcion            | Hace                                                     |
|-------------------|----------------------------------------------------------|
|`round(a, b)`      | Reduce a **b** la cantidad de numeros decimales de **a** |
|`x:.nf`            | Establece **n** decimales a un valor float **x**         |

## **Numeros Aleatorios**
Para hacer operaciones con numeros aleatorios necesitamos importar el modulo `random`. Una vex=z importado podemos hacer uso de sus metodos. Algunas de sus funciones son:

- `random.randinit(x, y)`:  
Genera un numero aleatorio entre un random entre los valores que pasemos como argumentos.
- `random.choice(a)`:  
Retorna un elemento aleatorio extraido de una secuencia pasada como argumento. Si esa secuencia esta vacia, la funcion genera un `IndexError`

Ejemplos de uso modulo random:

~~~py
import random 

# Generando un numero entero aleatorio entre 1 y 100.
numero_aleatorio = random.randint(1, 100) 
numero_elegido = int(input('Elige un numero entre 1 y 100: '))

while numero_elegido != numero_aleatorio:
    if numero_elegido < numero_aleatorio:
        print('Busca un numero mas grande')
    else:
        print('Busca un numero menor')
    numero_elegido = int(input('Elige otro numero: '))

print('El numero a adivinar era: '+ str(numero_aleatorio) + '. Ganaste!')
~~~

Ejemplo de una generador de contraseñasa aleatorias.

~~~py
# Programa que genere una contraseña con caracteres aleatorios de una lista.
import random

LETRAS = [
    'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'Ñ', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'X', 'Y', 'Z', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'ñ', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'x', 'y', 'z', '1', '2', '3', '4', '5', '6', '7', '8', '9', '0', '*', '+', '-', '/', '@', '_', '?', '!', '[', '{', '(', ')', '}', ']', ',', ';', '.', '>', '<', '~', '°', '^', '&', '$', '#', '"'
]

contrasena = []

for i in range(15):
    contrasena.append(random.choice(LETRAS) )
    
# Pasando la lista a un string.
contrasena = ''.join(contrasena)
~~~

## **Manejo de ficheros**
La lectura y escritura de informacion en archivos usando Python es bastante sencilla, y podemos hacerlo a travez del uso de las siguientes funciones :

- `open(nombre-ruta,  modo, encoding='utf-8')`:  
Permite abrir un archivo existente o crear uno en caso de que no existiese. Luego podremos leerlo o incluso escribir en el. Es indispensable abrir el fichero con esta funcion para poder trabajar con el.  
El primer parametro es el nombre del archivo a abrir. El segundo es el modo en el que vamos a abrir el archivo. El tercer parametro nos permite especificar que codificacion de caracteres usaremos en nuestro archivo. Es necesario para no tener problemas con simbolos de algunos idiomas que python pueda que no identifique correctamente, como los tildes por ejemplo.  
El argumento para especificar el modo de apertura puede ser:
    - `r`:  
    Abre el archivo en modo de solo lectura. Es decir, no lo podremos modificar, solo obtener y usar sin contenido sin realizar cambio alguno. Si el archivo no existe, el programa fallará.
    - `r+`:  
    Abre el archivo en modo lectura y escritura. Pudiendo así no solo obtener y usar su contenido, sino modificarlo si se desea.
    - `w`:  
    Abre el archivo en solo modo escritura. Va a sustituir el archivo original si existe antes o crear uno nuevo si no existe y el contenido original que tenga ese archivo se perderá una vez escribas en él.
    - `a`:  
    Abre el archivo para escritura, pero permitiendo agregar contenido al existente. Esto quiere decir que el contenido original se conserva y lo que escribas se agregará al final del archivo. Si el archivo no existe, se crea uno nuevo.
    - `a`+:  
    Abre el archivo en modo de escritura para agregar contenido y lectura, permitiendo así agregar contenido al final y leerlo también.
    - `x`: Permite crear el archivo.
    - `t`: (Text mode), para trabajar con ficheros de texto.
    - `b`: (Bytes), para archivos como fotos
- `archivo.read()`:  
Lee todo el fichero
- `archivo.readline()`:  
Lee la primera linea de un fichero. Este metodo mantiene el cursor que al ser llamada la funcion se desplaza al principio de la siguiente linea, por tanto, si lo llamamos una segunda vez leera la segunda linea y al finalizar se trasladara al principio de la tercera y asi suscesivamente cada vez que lo llamemos.
- `archivo.readlines()`:  
Lee todo el documento y cada linea la guarda en una posicion de una lista. Al igual que el metodo readline, este lee el fichero desde la posicion del cursor.
- `archivo.write(texto)`:  
Permite escribir el texto que pasemos como argumento al metodo. Este texto se agregara al final del documento. Esta funcion no agrega saltos de linea.
- `archivo.writelines(lista)`:  
Escribe cualquier el contenido de una lista o cualquier otro iterador al archivo.
- `print(texto, file=nombre-archivo)`:  
Podemos usarla para imprimir valores en un archivo por medio del parámetro `file`, en el que especificamos el nombre o la ruta de nuestro fichero. Esto nos brinda la ventaja de su funcionamiento habitual (saltos de línea, espacios y demás).
- `archivo.readable()`:  
Nos devuelve True o False dependiendo si un fichero es legible o no.
- `archivo.writable()`:  
Nos devuelve True o False dependiendo si un fichero puede ser escrito o no.
- `archivo.seek(x)`:  
Desplaza el cursor **x** caracteres.
- `archivo.close()`:  
Cierra nuestro archivo liberando memoria. Esto es INDISPENSABLE realizarlo siempre que hemos abierto un fichero

Ejemplos de lectura de ficheros.

~~~py
# Abrimos el fichero y leemos su contenido.
fichero = open('./fichero.txt', 'r', encoding='utf-8')

# Leyendo todo el documento y almacenando su contenido en una lista.
lineas = fichero.readlines()
print(lineas)

# Cerrando el fichero.
fichero.close()
~~~

Ejemplo de escritura de ficheros:

~~~py
# Abrimos el fichero en modo de escritura conservando su contenido.
fichero = open('./fichero.txt', 'a', encoding='utf-8')

listaContenido = [
    'Primera linea de nuestro archivo',
    'Segunda linea',
    'Tercera linea'
]

# Si quisieramos evitar la necesidad de ir agregando un salto de linea 
# a cada elemento de la lista podriamos hacerlo con la siguiente fincion lambda.
listaContenido = map(lambda line: line + '\n', listaContenido)

# Escribiendo el contenido de la lista en el fichero.
fichero.writelines(listaContenido)

# Cerrando el fichero.
fichero.close()
~~~

Ejemplo de un programa que modifique la ruta de los archivos en una lista de reproduccion de Windows para poder ser utilizada en Linux.

~~~py
import sys

def changePath(archivoOrigen, nuevaRuta, nombreArchivoDestino):

    print('CONVIRTIENDO LISTA DE REPRODUCCION')

    archivo = open(archivoOrigen, "r", encoding='utf-8')
    contenido = archivo.read()

    nuevoArchivo = open(nombreArchivoDestino, 'a', encoding='utf-8')
    
    lineas=contenido.split(sep='\n')

    for numeroDeLinea in range(len(lineas)):
        
        linea = str(lineas[numeroDeLinea])

        if linea[0] != '#':
            carpetas = linea.split(sep="\\")
            carpetas[0] = nuevaRuta

            nuevaLinea = ""
            for nivelDirectorio in range(len(carpetas)):
                nuevaLinea = nuevaLinea + "/" + str(carpetas[nivelDirectorio])

            linea = nuevaLinea
     
        print(linea)
        nuevoArchivo.write(linea + '\n')

    archivo.close()
    nuevoArchivo.close()
    print('\n Listo!: ' + str(len(lineas)) + ' Lineas Procesadas')


def removeFirstSlash(ruta):

    if ruta[0] == '/':
        ruta = ruta[1:]
        return ruta


def main():

    origen = sys.argv[1]
    ruta =  removeFirstSlash(sys.argv[2])
    destino = sys.argv[3]

    changePath(origen, ruta,destino)


if __name__ == '__main__':
    main()


~~~


# PROGRAMACION ORIENTADA A OBJETOS
La programacion orientada a objetos es un paradigma de programacion que consiste en imitar los objetos de la vida real, con sus propiedades y comportamientos en los lenguajes de programacion. Este paradigma de programacion nos permite generar codigo mas modular, reutilizar el codigo creado, lo que simplifica el proceso de desarrollo.
Un objeto se forma principalmente por dos elementos, que son:
- Datos: Describen el estado o las caracteristicas de un objeto. A estos les llamamos **propiedades** o **atributos**.
- Codigo: Ejecuta ciertas funcionalidades o comportamientos de dicho objeto. A estos les llamaremos **metodos**.

Los pilares de la programacion orientada a objetos son los siguientes:
- Herencia.
- Polimorfismo.
- Encapsulacion.
- Abstraccion.

## **Clases y Objetos**
Una **clase** es el modelo para un grupo de objetos. La clase define los metodos y atributos comunes de todos los objetos que perteneces a una misma clase. A un objeto que pertenece a una clase se le llama **instancia**.

Para declarar una clase lo hacemos escribiendo la palabra reservada `class` seguida del nombre de la clase. Por convencion se suele escribir el nombre de las clases con letrta inicial mayuscula.

Despues de haber creado la clase es importante definir los atributos de la clase por medio del metodo `__init__(self, [args...])`, que es el constructor de nuestra clase y es elencargado de inicializar nuestro objeto con los atributos que le asignemos por medio de los argumentos. El argumento `self`(nombre dado por convencion) hace referencia a la instancia actual de la clase(al objeto que estamos creando en ese momento.), y debe escribirse como primer parametro en cada metodo que creemos en nuestras clases. Este metodo se ejecuta en el instante en que creamos nuestro objeto.

Para crear un objeto de una clase simplemente le asignamos el nombre como a cualquier variable agignandole como valor el nombre de la clase con el valor de sus atributos entre parentesis.

Ejemplo de creacion de una clase y de su constructor y sus instancias.

~~~py
# Declaracion de la clase
class Camiseta:
    # Definimos el constructor
    def __init__(self, talla, color, precio, marca):
        self.talla = talla
        self.color = color
        self.precio = precio
        self.marca = marca
        self.rebajada = False

    def aplicarDescuento(self, porcentaje):
        self.precio = self.precio - self.precio * porcentaje/100
        if porcentaje < 100:
            self.rebajada = True
        

    def infoProducto(self):
        info = f'Descripcion de la camiseta\nMarca: {self.marca}\nPrecio: {self.precio}\nTalla: {self.talla}\nColor: {self.color}\n'
        if self.rebajada:
            info += 'ESTE PRODUCTO ESTA REBAJADO.'
        return info


# Creando dos objetos de la clase camiseta.
camisetaNike = Camiseta('L', 'Azul', 20.00, 'Nike')
camisetaPuma = Camiseta('XL', 'Roja', 30.00, 'Puma')


print(camisetaNike.color)
print(camisetaNike.precio)

print('Precio de camiseta Puma sin descuento: ', camisetaPuma.precio, camisetaPuma.infoProducto())
camisetaPuma.aplicarDescuento(50)
print('Precio de camiseta Puma con descuento: ', camisetaPuma.precio, camisetaPuma.infoProducto())
~~~

En python se pueden usar clases anidadas, conocidas como clases internas o **Inner Class**, por su termino en ingles, y esta consiste en declarar una clase en el cuerpo de otra clase. Si un objeto se crea utilizando una clase, se puede usar el objeto dentro de la clase raiz.

Una clase puede tener más de una clase interna, pero en general se evitan las clases internas.
Al usar clases internas, puedes hacer que tu código sea aún más orientado a objetos. Un solo objeto puede contener varios sub-objetos. Podemos usarlos para agregar más estructura a nuestros programas.
~~~py
class Humano:

    def __init__(self):
        self.nombre = 'Ivan'
        self.cabeza = self.crearCabeza()
    def crearCabeza(self):
        return Humano.Cabeza(self)

    class Cabeza:

        def __init__(self, humano):
            self.humano = humano
        def hablar(self):
            return 'talking...', self.humano.nombre
 
 
ivan = Humano() #Instanciamos
ivan.nombre
#'Ivan'

ivan.cabeza.hablar()
#('hablando...', 'Ivan')
~~~

## **Herencia**
La herencia es un mecanismo o funcionalidad que nos permite que una clase reciba las caracteristicas de otra clase ademas de tener los suyos propios.

La nomenclatura de la herencia es la siguiente:
- **Superclase**:  
Es la clase padre, de la cual se heredan las caracteristicas. Suele ser mas general y sirve de base para otras clases.
- **Subclase**:  
Es la clase hijo. Estas es la que recibe la herencia y amplia los metodos y atributos de la superclase con los suyos propios. Suele ser una clase mas concreta o especifica.

Existen dos diferentes tipos de herencia. Entre ellos estan:
- **Herencia Simple**:  
Es la forma mas basica de herencia que existe, y consiste en que una clase hereda de una superclase.
- **Herencia Jerarquica**:  
Se produce cuando multiples subclases heredan de una unica superclase.
- **Herencia Multiple**:  
Es cuando una subclase hereda de dos o mas superclases al mismo tiempo.
- **Herencia Multinivel**:  
Es cuando una subclase hereda de una superclase, a su vez, esta superclase hereda de otra superclase.

Para crear una subclase debemos escribir el nombre de la superclase entre parentesis detras del nombre de la clase hija. El metodo init de la subclase debe hacer referencia al constructor de la superclase por medio del metodo `super().__init__(propiedades, ...)`(no debe incluir la palabra `self`), y luego de esto, lo ampliamos con sus propios metodos. Por ejemplo:

~~~py
class Persona:
    def __init__(self, nombre, edad, DNI):
        self.nombre = nombre
        self.edad = edad
        self.DNI = DNI

    
    def presentarse(self):
        print(f"Hola! mi nombre es {self.nombre}, y tengo {self.edad}.")


class Trabajador(Persona):
    def __init__(self, nombre, edad, DNI, sueldo, cargo, empresa):
        super().__init__(nombre, edad, DNI)
        self.sueldo = sueldo
        self.cargo = cargo
        self.empresa = empresa


    def calcularSueldoAnual(self):
        return 12 * self.sueldo + 2000


class Estudiante(Persona):
    def __init__(self, nombre, edad, DNI, universidad, curso, asignaturas):
        super().__init__(nombre, edad, DNI)
        self.universidad = universidad
        self.curso = curso
        self.asignaturas = asignaturas


    def describirse(self):
        print(f"Hola, soy {self.nombre}. Tengo {self.edad} y estudio en la universidad {self.universidad}. Estoy en el curso de {self.curso}")


#=============================================#
##########  Instanciando las clases  ##########
#=============================================#

trabajador = Trabajador('Fulano', 33, '765432-1', 2000, 'Administrador', 'Ikea')
trabajador.presentarse()
print(trabajador.calcularSueldoAnual())

estudiante = Estudiante("Sutano", 25, 123456-7, "Universidad Nacional", "Programacion", ['Programacion', 'Matematica', 'Ciencias Naturales'])
estudiante.describirse()
print(estudiante.asignaturas)
~~~

> NOTA: Para que una subclase herede de multiples superclases basta con colocar entre parentesis todas las superclases separadas por comas.


## **Encapsulamiento**
En Python, todos los metodos y atributos son publicos, por lo que el encapsulamiento realmente no existe. Aun asi, hay convenciones para tratar de indicar a los desarrolladores que dichos atributos o metodos se deben tratar como protegidos o privados. Las convenciones son las siguientes:
- `_atributoOMetodo`: 
Un guion al principio del nombre nos indica de que el atributo o metodo debe ser tratado como protegido.
- `__atributoOMetodo`:  
Un doble gion al principio del nombre nos indica de que el atributo o metodo debe ser tratado como privado.

El encapsulamiento permite regular el acceso a los metodos y atributos de una clase, por lo que en cierta manera enmascara la complegidad de una clase. 

Para los metodos y los atributos tenemos los siguientes **modificadores de acceso**:
- **Publicos**:  
Son accesibles desde cualquier punto del codigo, tanto dentro como fuera de la clase, subclase, etc.
- **Protegidos**:  
Son accesibles desde la misma clase, las subclases y clases dentro del mismo paquete.
- **Privados**:  
Son accesibles unicamente dentro de la misma clase.

Las utilidades del encapsulamiento son que nos permiten ocultar metodos y atributos fuera de la propia clase. Podemos regular la modificacion de los atributos(privados) evitando que se accedan a ellos directamente. Crearemos metodos(publicos) para modificar los atributos de un objeto, y enmascara la complejidad de algunos metodos haciendolos privados y utilizarlos desde metodos publicos.

~~~py
class Circulo:
    def __init__(self, radio):
        self.__radio = radio
        self.__pi = 3.1415

    
    def calcularPerimetro(self):
        return 2 * self.__pi * self.__radio


    def calcularArea(self):
        return self.__pi * self.__radio ** 2
    
    # Creando un metodo publico para acceder a la propiedad privada __pi.
    def getPi(self):
        return self.__pi


    # Creando un metodo publico para actualizar el valor de la propiedad privada __radio
    def setRadio(self, nuevoValor):
        if type(nuevoValor) == int or type(nuevoValor) == float:
            if nuevoValor > 0:
                self.__radio = nuevoValor
                print(f'El radio se ha modificado. Su nuevo valor es: {nuevoValor}')
            else:
                print('El radio no puede ser negativo.')
        else:
            print('El radio tiene que ser un valor de tipo entero o float positivo')


c1 = Circulo(2.5)
print(c1.calcularArea())
print(c1.calcularPerimetro())
print(f'La constante  PI tiene el valor de: {c1.getPi()}')

c1.setRadio(34)
c1.setRadio(-23)
c1.setRadio("Hola, que tal")
~~~

En el caso anterior, al querer llamar a la propiedad `__pi` de la clase `Circulo` nos da un error(`AttributeError`), diciendonos que el atributo no existe, pero esto no es porque Python soporte oficialmente el encapsulamiento, sino porque al escribir el nombre de un atributo o metodo con dos guiones bajos al principio python cambia la nomenclatura de el atributo o metodo. Por lo tanto: `__nombreDelAtributoMetodo` Equivale a: `_NombreDeLaClase__nombreDelAtributoMetodo`. Asi que, en el caso anterior, si quisieramos acceder a un metodo o atributo privado de la clase `Circulo` a traves del objeto `c1`, podriamos hacerlo usando la nomenclatura `c1._Circulo__pi`.
Python hace lo anterior para evitar que nombres de metodos o atributos de clases distintas coliciones.

Crear metodos publicos para acceder o modificar propiedades privadas es una manera de evitar el acceso incorrecto a los metodos. De esta forma podemos validar  que no se usen valores que no correspondan con los esperados.


## **Polimorfismo**
El polimorfismo es una herramienta que nos permite redefinir metodos que se heredan de una clase padre. De este modo, si tenemos un metodo de una superclases de la cual heredan una o mas subclases, en cada una de estas subclases, bajo el mismo nombre, podremos modificar o definir de nuevo el codigo que se ejecuta en esos metodos.

Ejemplo de polimorfismo:

~~~py
class Empleado:
    def __init__(self, nombre, sueldoMensual):
        self.nombre = nombre
        self.sueldoMensual = sueldoMensual


    def calcularSueldoAnual(self):
        sueldo = 12 * self.sueldoMensual * (1 + 1/100)
        print(f'El sueldo anual de {self.nombre}, empleado Normal es de: ${sueldo}')


class Contable(Empleado):
    def __init__(self, nombre, sueldoMensual):
        super().__init__(nombre, sueldoMensual)


    # Haciendo uso del polimorfismo, aumentando el bono a un 4%.
    def calcularSueldoAnual(self):
        sueldo = 12 * self.sueldoMensual * (1 + 4/100)
        print(f'El sueldo anual de {self.nombre}, empleado Contable es de: ${sueldo}')


class Publicista(Empleado):
    def __init__(self, nombre, sueldoMensual):
        super().__init__(nombre, sueldoMensual)


    def calcularSueldoAnual(self):
        sueldo = 12 * self.sueldoMensual * (1 + 5/100)
        print(f'El sueldo anual de {self.nombre}, Publicista es de: ${sueldo}')


class Becario(Empleado):
    def __init__(self, nombre, sueldoMensual):
        super().__init__(nombre, sueldoMensual)


    def calcularSueldoAnual(self):
        sueldo = 12 * self.sueldoMensual
        print(f'El sueldo anual de {self.nombre}, Becario es de: ${sueldo}')


# Creando lista de objetos.
empleados = [
    Empleado('Juan', 1000),
    Contable('Angela', 1100),
    Publicista('Ryan', 1200),
    Becario('Pepito', 750)
]

for empleado in empleados:
    empleado.calcularSueldoAnual()

~~~

En el ejemplo anterior hacemos uso del polimorfismo, y gracias a el podemos llamar al metodo `calcularSueldoAnual()`, y este se comportara de manera diferente dependiendo de a que clase pertenezca cada uno de los objetos creados en la lista `empleados`.

> NOTA: De hecho, desde el momento en que redefinimos el constructor de una clase que hereda de otra estamos haciendo uso del polimorfismo


## **Abstraccion**
La abstraccion es un mecanismo que nos permite crear **clases abstractas**. Estas son, clases que nunca instanciaremos de manera directa. Estas clases nos sirven de estructura principal para otras subclases que van a heredar de esta clase abstracta.  
Las clases abstractas deben poseer por lo menos un **metodo abstracto**. Estos metodos se sobreescribiran obligatoriamente en las subclases que hereden de nuestra clase abstracta.

Para crear clases abstractas es necesario seguir los siguientes pasos.
1. Importar el metodo `abstractmethod` de la clase `ABC` o `ABCMeta`del modulo `abc`.
2. Hacer que las clases abstractas hereden de la clase `ABC`, o `metaclass=ABCMeta`.  
3. Definir los metodos como abstractos usamos el decorador `@abstractmethod` encima de la declaracion de la funcion. 
4. Opcionalmente podemos llamar los metodos de la clase abstracta al momento de definir el metodo de la subclase. En el ejemplo lo haremos con la linea `super().getStatus()` dentro de la funcion con el mismo nombre.

~~~py
from abc import ABC, abstractmethod

class Personaje(ABC):
    @abstractmethod
    def __init__(self, nombre):
        self.nombre = nombre
        self.nivel = 0
        self.vida = 100
        self.inventario = []


    @abstractmethod
    def atacar(self, objetivo):
        pass


    @abstractmethod
    def getStatus(self):
        print(f"Nombre: {self.nombre}. Nivel: {self.nivel}")


    def subirDeNivel(self):
        self.nivel +=1


    def verInventario(self):
        print(f"Inventario de {self.nombre}")
        for objeto in self.inventario:
            print(objeto)


class Mago(Personaje):
    def __init__(self, nombre):
        super().__init__(nombre)
        self.vida = 120
        self.inteligencia = 95
        self.inventario = ["Pocion de Mana", "Grimorio"]


    def getStatus(self):
        print("Clase Mago")
        # Extendemos el metodo getStatus.
        super().getStatus()


    def atacar(self, objetivo):
        objetivo.vida -= self.inteligencia * 0.6
        print(f"La vida actual del objetivo es: {objetivo.vida}")


    def saludar(self):
        print('Hola que tal! Soy un Mago')


class Guerero(Personaje):
    def __init__(self, nombre):
        super().__init__(nombre)
        self.vida = 200
        self.fuerza = 75
        self.inventario = ["Posion de vida", "Escudo", "Espada"]


    def getStatus(self):
        print("Clase Guerrero")
        super().getStatus()


    def atacar(self, objetivo):
        objetivo.vida -= self.fuerza * 0.8
        print(f"El objetivo se ha quedado con {objetivo.vida} puntos de vida.")


guerrero = Guerero("Kaladin")
mago = Mago("Yuno")

guerrero.getStatus()
mago.getStatus()

guerrero.verInventario()
mago.verInventario()

mago.atacar(guerrero)
guerrero.atacar(mago)
~~~

> Un decorador basicamente "envuelve" y modifica el comportamiento de la funcion que esta decorando. En el ejemplo anterior estamos convirtiendo los metodos `__init__()`, `getStatus()` y `atacar` de la clase personaje en metodod abstractod, ya que no instaciaremos la clase Personaje.

> NOTA: Podemos definir metodos que no hayamos definido como abstractos en las superclase o en las subclases sin problemas, como el metodo `saludar()` en el ejemplo anterior.


# CONCEPTOS AVANZADOS

## **Manejo de Excepciones**
Las excepciones son errores que ocurren durante la ejecucion del programa. Estos errores surgen a pesar de que la sintaxis sea correcta. Estos errores pueden ser, por ejemplo, intentar acceder a una posicion de una lista que no existe, intentar abrir un fichero que no se ha creado o intentar convertir una cadena de texto en un entero.

Manejar las excepciones en cualquier lenguaje os permite que el programa se siga ejecutando a pesar de que ocurran errores.

Las excepciones se manejan con los bloques `try:` y `except`. En el primero colocamos el codigo que es suceptible a que nos produzca un error, mientras que el segundo capturamos el tipo de excepcion que esperamos se pueda producir y establecemos lo que queremos que el programa realice cuando el error se haya producido. 

Algunos tipos de excepciones que se mas comunmente son:

- ` ZeroDivisionError`:  
Cuando intentamos dividir por cero.
- `IndexError`:  
Cuando se intenta acceder a un indice en una lista que no existe.
- `ValueError`:  
Cuando intentamos manejar un tipo de dato como si fuera otro. Por ejemplo un string como entero.
- `Exception`:  
Esta excepcion captura cualquier tipo de excepcion, sin tener la necesidad de conocer su clase especifica.

Ejemplo:

~~~py
def division(a, b):
    try:
        resultado = a/b
        print(resultado)

    except ZeroDivisionError:
        print("No se puede dividir por cero")


division(5,0)

print('Programa finalizado.')
~~~

Podemos colocar multiples bloques except para capturar diferentes tipos de excepciones y que el programa se comporte de manera distinda dependiendo de el error capturado.  
Tambien es posible *renombrar* excepciones para imprimir un mensaje descriptivo del tipo de error utilizando la palabra reservada `as` seguido del nombre que queramos asignarle.

~~~py
def elegirFrutas(listaFrutas):
    try:
        print(listaFrutas)
        index = int(input('Ingresa el numero de la fruta que deseas: '))
        print(f'Tu fruta favorita es: {listaFrutas[index]}')

    except IndexError:
        print(f'Indice incorrecto, debe estar entre 0 y {len(listaFrutas) - 1}')

    except ValueError:
        print('Tienes que ingresar un numero entero')

    except Exception as errorRandom:
        print('Se ha producido un error: ', errorRandom)


frutas = [
    '0-Platano',
    '1-Manzana',
    '2-Pomelo',
    '3-Melocoton'
]

elegirFrutas(frutas)

~~~

> NOTA: Para poder obtener mas informacion sobre los errores capturados con la excepcion `Exception`, podemos hacer uso de el metodo `logging.exception("Mensaje personalizado")` dentro del bloque `except`. Este metodo nos brinda informacion de la traza de errores en la pila de errores. Para eso debemos importar el modulo logging con la linea `import logging`

Podemos combinar las excepciones con las sentencias `raise`, `else` y `finally` para tener un mayor control en el manejo de errores. Las palabras anteriores hacen lo siguiente:
- `raise`:  
Dispara una excepcion especifica de manera voluntaria. Su sintaxis es `raise TipoDeError("Mensaje personalizado")`.
- `else`:  
El bloque **else** se ejecutara si el bloque **try** se ejecuta sin producir ningun error. En el siguiente ejemplo lo utilizamos para romper el ciclo while despues de haberse ejecutado nuestro codigo de manera satisfactoria.
- `finally`:  
El codigo escrito en esta seccion se ejecutara siempre, sin importar si se ha producido un error o no

~~~py
while True:
    try:
        total = 0
        sumandos = input("Pasa numeros separados por espacios: ")
        sumandos = sumandos.split()

        for num in sumandos:
            if num.isnumeric():
                total += float(num)
            else:
                raise ValueError("El valor no es un numero.")
            
    except ValueError:
        print('Los datos son incorrectos')
        print('Vuelve a introducir los numeros por favor: ')

    else:
        print(f'El valor de la suma es: {total}')
        break

    finally:
        print('Ha terminado la iteracion.')

~~~

## **Funciones Lambda**
Las expresiones lambda son funciones anonimas, que y se usan idealmente cuando necesitamos hacer algo simple y estamos mas interesados en hacer el trabajo rapidamente en lugar de nombrar formalmente la funcion. Algunas de las caracteristicas de las funciones lambda son que permiten multiples argumentos, y solo pueden tener una expresion (una linea de codigo).  

La estructura basica de una funcion lambda es: `lambda arg1, arg2 : expresion`.

En el siguiente ejemplo creamos tres funciones lambda llamadas **suma**, **saludar** y **maximo**, y en las dos ultimas vemos que podemos llamar funciones dentro ed la funcion lambda.

Ejemplo:

~~~py
# Creando una funcion lambda llamada suma.
suma = lambda a, b : a + b
print(suma(5,5))
print(suma(3,2))


# Llamando a otras funciones dentro de una funcion lambda.
saludar = lambda nombre: print(f"Hola {nombre}!!")
saludar("Sutano")

maximo = lambda a, b, c: f"El maximo entre {a}, {b}, y {c} es: {max(a, b, c)}"
print(maximo(3, 4, 5))
print(maximo(10, 99, -25))
~~~

Tambien podemos definir funciones lambda dentro de funciones convencionales. Su funcionamiento es un poco curioso, ya que diferentes argumentos seran pasados en diferentes momentos del llamado a estas funciones. En el siguiente ejemplo definimos dos funciones convencionales que reciben un parametro y nos retornan una funcion lambda cada uno. Esta funcion lambda recibe un parametro que no recibe al momento de definir la funcion convencional, sino que lo reciben al momento de llamar a las funcion  que definiremos a partir de la funcion lambda retornada por la funcion convencional.

Veamos:

~~~py
# Definiendo la funcion convencional que nos retornara una funcion lambda.
# Y definiendo uno de los argumentos de la funcion.
def ponerPrefijo(prefijo):
    return lambda nombre: f"{prefijo} {nombre}"


# Definiendo funciones a partir de la funcion convencional.
# El argumento 'prefijo' lo pasamos como argumento de la funcion 'ponerPrefijo()'
# Con esto, la expresion de la funcion lambda tiene uno de los valores 
# con los que trabajar, quedando pendiente el argumento 'nombre' de la funcion lambda
addMr = ponerPrefijo("Mr")
addSr = ponerPrefijo("Sr")
addMiss = ponerPrefijo("Miss")

# Llamamos a la funciones creadas a partir de 'ponerPrefijo()'.
# Y es ahora cuando pasamos el argumento 'nombre' de la funcion lambda.
# De esta manera hemos pasado los dos argumentos con los que 
# trabaja la expresion de la funcion lambda.
print(addMr("Juan"))
print(addSr("Julian"))
print(addMiss("Nerea"))

#====================================================================
# OTRO EJEMPLO DE FUNCION LAMBDA DENTRO DE UNA FUNCION CONVENCIONAL #
#====================================================================
def elevarA(exponente):
    return lambda base: base ** exponente


# Creando funciones a partir de la funcion lambda que retornara la funcion convencional 
# y fijando el argumento exponente
elevarCuadrado = elevarA(2)
elevarCubo = elevarA(3)

# Asignando el numero de base e imprimiendo el resultado de la elevacion en pantalla.
print(elevarCuadrado(3))
print(elevarCubo(2))
~~~

Es importante notar que las funciones `addMr()`, `addSr()`, y `addMiss()` se comportan como si fueran variables, y que el 'valor' que les es asignado al momento de crearlas es la funcion lambda que retorna la funcion convencional `ponerPrefijo()`, ya con el argumento `prefijo` establecido. por lo cual, cuando llamemos a las funciones mencionadas, el argumento que les estaremos pasando sera el correspondiente al argumento nombre de la funcion lambda.

> NOTA: En Python es comun utilizar funciones como si fueran objetos o variables, como podemos ver en el caso de las funciones `lambda` o la siguiente funcion que veremos, `filter`. por eso podemos pasarlos como parametros a otras funciones.

## **Funciones Map y Filter**
Las funciones `map()` y `filter()` son funciones que nos permiten trabajar con objetos iterables(listas, tuplas o strings). Estas funciones vienen incorporadas por defecto con Python.

### ***Funcion Filter***
La funcion `filter(function, iterable)` devuelve un **iterador** con los valores del **iterable** que cumplan con **function**. Filter ejecuta la funcion con cada uno de los elementos que contiene el iterable, por lo que seran comprobados los elementos uno a uno y los que cumplan con la funcion del primer parametro seran seleccionados y pasados al iterador. De esa manera, no sera necesario hacer un bucle que vaya recorriendo la lista para ir pasando los elementos al iterador.

En el siguiente ejemplo, se puede usar para comprobar emails validos de una lista. 

~~~py
emails = [
    'fulano@hotmail.es',
    'sutano@gmail.com',
    'frutas',
    'wikipedia.com'
]

#=========================#
# Haciendo uso de Listas: #
#=========================#
listaEmailsValidos = []

print('Imprimiendo emails validos usando listas:')
for email in emails:
    if '@' in email:
        print(f"el email {email} es valido.")
        listaEmailsValidos.append(email)
    else:
        print(f"el email {email} es invalido.")


# ==============================#
# Utulizando la funcion filter: #
# ==============================#
def evaluarEmail(email):
    return '@' in email
    

iteradorEmailsValidos = filter(evaluarEmail, emails)  

print('\nImprimiendo emails validos usando la funcion filter:')
print(next(iteradorEmailsValidos))
print(next(iteradorEmailsValidos))

~~~

> NOTA: La linea `return '@' in email` es una expresion condicional, por lo que devolvera `True` o `False` dependiendo si se encuentra el caracter `@` o no. Con esa linea evitamos usar el **if-else**, ya que seria redundante.

Tanto la funcion filter como map devuelven un **iterador**, y ***no se puede acceder a los elementos que contiene como los de una lista***. Si preferimos trabajar con listas es posible convertir el iterador en una con la funcion `list(iterador)`. Para acceder a ellos es necesario hacerlo a traves de funciones especificas, como por ejemplo:
- `next(iterador)`:  
Devuelve un elemento del iterador cada vez que se llama. Si se llama mas veces que el numero de elementos que contiene el iteradornos dara un error de **StopIteration**.

Podemos utilizar funciones lambda como parametro de la funcion filter. Volviendo al ejemplo anterior la forma de aplicarla seria lo siguiente:

~~~py
emails = [
    'fulano@hotmail.es',
    'sutano@gmail.com',
    'frutas',
    'wikipedia.com',
]

emailsValidos = list(filter(lambda email: '@' in email, emails))
print(emailsValidos)

~~~

### ***Funcion Map***
La definicion de map es muy similar a la definicion de filter (`map(function, iterable)`), pero a diferencia de la funcion filter, map **ejecuta la funcion usando como parametro cada elemento del iterable**. Por lo tanto **no se esta evaluando una condicion, simplemente se esta pasando los elementos del iterable por la funcion** y ya esta, no verifica si el retorno de la funcion es `True` o `False`.

Por ejemplo, en el siguiente programa contamos el numero de caracteres que conforman cada elemento de la tupla `palabras`:

~~~py
palabras = (
    'Hola',
    'que',
    'tal',
    'como',
    'estas',
    '?'
)

longitudes = list(map(lambda palabra: len(palabra), palabras))
print(longitudes)
~~~

Podemos pasar cuantos iterables deseemos siempre y cuando coincidan con el numero de argumentos que reciba la funcion que utilicemos de parametro para map. 

Por ejemplo, pasamos dos listas como iterables de map que son recibidos por la funcion lambda que necesita dos argumento. Cada elemento de la lista `eje_x` y `eje_xx` seran asignados a los argumentos `x` y `y` respectivamente.

~~~py
import math

eje_x = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
eje_xx = [3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]

eje_y = list(map(lambda x, y: round(math.cos(x) + math.exp(y), 2), eje_x, eje_xx))

print(eje_y)
~~~


## **Modulos y Paquetes**
### ***Modulos***
Los modulos son archivos de Python (Pueden ser de Cpython o de C). Estos archivos pueden contener funciones, clases y variables que despues pueden ser importadas a nuestros archivos para hacer uso de estas sin tener que volver a escribir su codigo.

Para crear un modulo creamos un archivo Python a parte donde esscribimos el codigo de nuestra eleccion. En nuestro siguiente ejemplo crearemos un modulo llamado **calcularArea.py**

~~~py
# Modulo calcularArea.py

PI = 3.1415

def areaCirculo(radio):
    return PI * radio ** 2


def areaTriangulo(base, altura):
    return base * altura / 2


def areaCuadrado(lado):
    return lado * lado
~~~

Y desde nuestro archivo principal importamos el modulo de la siguiente manera:

~~~py
# Archivo main.py

import calcularArea
from calcularArea import areaCuadrado, areaTriangulo

print(calcularArea.PI)
print(calcularArea.areaCirculo(5))
print(areaCuadrado(3))
~~~

> NOTA: Si importamos el modulo completo (`import calcularArea`) necesitamos escribir el nombre del modulo cada vez que deseemos usar una de sus funciones (por ejemplo: `print(calcularArea.areaCirculo(5))`). En cambio, si importamos unicamente la funcion que necesitamos (con la linea `from calccularArea import areaCuadrado` o importarlas todas con la linea `from calcularArea import *`), basta con escribir la funcion como si de una funcion interna se tratase.

### ***Paquetes***
Los paquetes son conjuntos de modulos, relacionados entre si, y que se encuentran en un mismo directorio.

Para crear un paquete necesitamos segior los siguientes pasos:  
- Crear una carpeta y asignarle el nombre de nuestro paquete.
- Dentro de el directorio creado colocaremos los archivos que seran los modulos de dicho paquete. 
- Crear un archivo de Python llamado `__init__.py` que se ejecutara cuando carguemos un paquete. Normalmente se deja vacio. 

> NOTA: Desde python 3.3 ya no es un requisito crear el archivo `__init__.py`, pero es una buena practica hacerlo.

Hay diferentes maneras de importar un paquete o modulo, ademas de la manera vista en el ejemplo anterior podemos hacerlo como en el siguiente ejemplo en el que establecemos que: 

Desde el modulo `calcularPermietro` del paquete `geometria` importamos la clase `CalcularPerimetros` renombrando la clase como (con la palabra reservada `as`) `CP`. Con esto podemos trabajar con un nombre de la clase mas facil de manejar.

Por ejemplo:

~~~py
# Modulo calcularPerimetro.py

import math

class CalculaPerimetros:
    def __init__(self):
        pass


    def perimetroCuadrado(self, lado):
        return lado * 4
    

    def perimetroCirculo(self, radio):
        return math.pi * radio * 2
    
    
~~~

~~~py
# Archivo main.py

from geometria.calcularPerimetro import CalculaPerimetros as CP
import geometria.calcularArea


cp = CP()
print('Imprimiendo Perimetro de circulo', cp.perimetroCirculo(2))

print('Imprimiendo Area de circulo', geometria.calcularArea.areaCirculo(3))

~~~

> NOTA: Podemos importar modulos o paquetes dentro de otros modulos sin ningun problema.

## **Interfaces Graficas con Tkinter**
Tkinter es un binding de la biblioteca gráfica Tcl/Tk para el lenguaje de programación Python. Se considera un estándar de interfaz gráfica de usuario para Python y está incluido por defecto con la instalación para Microsoft Windows. Para instalarlo en Ubuntu podemos usar el comando `sudo apt install python3-tkinter` y para Manjaro Linux con el comando `sudo pacman -S tk`.

Tkinter funciona mediante **widgets**, que son elementos predefinidos que podemos ir incrustando en nuestra aplicacion, como pueden ser un boton, un input de texto, o incluso, la ventana principal de la aplicacion.

Para crear una aplicacion con interfaz grafica como en el sigiente ejemplo debemos seguir los siguientes pasos:
- **importar el modulo `tkinter`**. Podemos renombrarlo con la palabra reservada `as` para colocarle un nombre mas manejable.
- **Instanciar un objeto de la clase `Tk()`** del modulo tkinter.
- **Creamos los objetos de tipo `tk.StringVar(app)`**  
Para poder trabajar con variables y usarlas en nuestra aplicacion ya sea asignandoles valor u obteniendo el contenido de algun widget por medio de los metodos `.set()` y `.get()` respectivamente.
- **Definimos las dimensiones por defecto de nuestra ventana** por medio del metodo app.geometry("600x300").
- **Establecemos un color de fondo** a traves del metodo `.configure(background="black")`.
- **Asignamos un titulo a nuestra ventana** con el metodo `tk.Wm.wm_title(app, "Mi interfaz grafica.")` de la clase Wm del modulo tkinter. Este recibe como parametro la ventana a la cual le asignaremos el titulo y el titulo en si.
- **Definimos las funciones** para interactuar con nuestra aplicacion.
- **Creamos los widgets** que contendra nuestra aplicacion.
- **Llamar al metodo `.mainloop()` de la clase Tk**, que se encarga de ir refrescando nuestra aplicacion para ir actualizando constantemente el estado de nuestra aplicacion, como por ejemplo, si hemos hecho click a algun boton o si debemos modificar algun widget.

Cada widget hace referencia a una clase de el modulo tk, y como primer parametro le agregamos el objeto de la ventana donde queremos anclarlo, y seguido, podremos agregar todos los demas parametros con sus respectivos valores para darle un estilo y fncionalidad a nuestra aplicacion. Dichos parametros deben ir separados por comas. Estos pueden ser:  
- `text`:  
Asigna el texto de nuestro widget.
- `font`:  
Establece el tipo y tamaño de fuente en nuestro widget.
- `bg`:  
Establece el color de fondo de nuestro widget.
- `fg`:  
Establece el color de la fuente de nuestro widget.
- `command`:  
Asigna una funcion **como un objeto**  (debe escribirse sin los parentesis), no como ejecucion de la funcion. se puede utilizar una funcion lambda. En caso de que se quiera asignar la ejecucion de una funcion (como podria ser la sentencia `print("Hola mundo!")`) esta se ejecutara sin que hayamos interactuado con el widget.
- `relief`:  
Define el tipo de borde que poseera nuestro widget.
- `justify`:  
Establece el alineado (centrado, derecha o izquierda) del texto de nuestro widget
- `textvariable`:  
Hace referencia a un objeto de tipo **StringVar** que permite interactuar con el contenido de nuestros widgets ya sea recuperando su contenido o asignandoles algun valor por medio de los metodos `.set()` y `.get()`.

Luego de haber definido los parametros de todo lo que contendra nuestro widget debemos llamar al metodo `pack()`. Este metodo lo que hace es enpaquetar nuestro widget y establecer en que direcciones (a lo alto y a lo ancho con el parametro `fill`) se rellenara el espacio disponible y si se expandira en el contenedor principal con el parametro `expand`.

Ejemplod de un programa con interfaz grafica usando tkinter:

~~~py
import tkinter as tk

app = tk.Tk()

palabra = tk.StringVar(app)
entrada = tk.StringVar(app)

app.geometry("600x300")
app.configure(background="black")
tk.Wm.wm_title(app, "Mi interfaz grafica.")

def saludar():
    print(f"Hola que tal {entrada.get()}!")


def cambiarPalabra():
    palabra.set(f"Cambiando palabra a: {entrada.get()}")


tk.Button(
    app,
    text="Click Me!",
    font=("Courier", 14),
    bg="#00a8e8",
    fg="white",
    command=cambiarPalabra,
    relief="flat"
).pack(
    fill=tk.BOTH,
    expand=True
)

tk.Label(
    app,
    text="Etiqueta",
    fg="white",
    bg="black",
    justify="center",
    textvariable=palabra
).pack(
    fill=tk.BOTH,
    expand=True
)

tk.Entry(
    app,
    text="Etiqueta",
    fg="white",
    bg="black",
    justify="center",
    textvariable=entrada
).pack(
    fill=tk.BOTH,
    expand=True
)

app.mainloop()

~~~

## **Decoradores**

# MANEJO DE BASES DE DATOS
## **SQLite**