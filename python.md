# **CURSO DE PYTHON**

Python es un lenguaje de programación de alto nivel, interpretado cuya filosofía hace hincapié en la legibilidad de su código, se utiliza para desarrollar aplicaciones de todo tipo.​ Fue creado a finales de los años ochenta​ por Guido van Rossum en Stichting Mathematisch Centrum (CWI), en los Países Bajos, como un sucesor del lenguaje de programación ABC.

Se trata de un lenguaje de programación multiparadigma, ya que soporta parcialmente la orientación a objetos, programación imperativa y, en menor medida, programación funcional. Es un lenguaje interpretado, dinámico y multiplataforma.

Administrado por Python Software Foundation, posee una licencia de código abierto, denominada Python Software Foundation License.

**Tabla de Contenido**

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

|Funcion          | Hace                                                                        |
|-----------------|-----------------------------------------------------------------------------|
|`.upper()`       | Cambia todo el texto a mayusculas.                                          |
|`.capitalize()`  | Cambia la primera letra a mayuscula.                                        |
|`.lower()`       | Cambia toda el texto a minuscula.                                           |
|`.strip()`       | Elimina los espacios entre caracteres.                                      |
|`.replace(x, y)` | Reemplaza **x** por **y**.                                                  |
|`len(x)`         | Devuelve la longitud de x.                                                  |
|`.split(sep='')` | Divide una cadena en una lista de palabras separandolas por el valor de sep.|

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
# Programa que identifique si una palabra es palindroma

palabra = input('Ingrese una palabra para verificar si es palindromo: ')
if palabra == palabra[::-1]:
    print('Es un palindromo')
else:
    print('No es un palindromo.')
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
Ademas de los operadores para asignar o comparar valores numericos existen muchas funciones que nos facilitan el trabajar con enteros o decimales. Algunas de las funciones son:

|Funcion            | Hace                                                     |
|-------------------|----------------------------------------------------------|
|`round(a, b)`      | Reduce a **b** la cantidad de numeros decimales de **a** |
## **Manejo de ficheros**






Informacion complementaria 
https://www.programarya.com/Cursos/Python
