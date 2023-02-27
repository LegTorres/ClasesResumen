# **CURSO DE PYTHON**

Python es un lenguaje de programación de alto nivel, interpretado cuya filosofía hace hincapié en la legibilidad de su código, se utiliza para desarrollar aplicaciones de todo tipo.​ Fue creado a finales de los años ochenta​ por Guido van Rossum en Stichting Mathematisch Centrum (CWI), en los Países Bajos, como un sucesor del lenguaje de programación ABC.

Se trata de un lenguaje de programación multiparadigma, ya que soporta parcialmente la orientación a objetos, programación imperativa y, en menor medida, programación funcional. Es un lenguaje interpretado, dinámico y multiplataforma.

Administrado por Python Software Foundation, posee una licencia de código abierto, denominada Python Software Foundation License.



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

## **Operadores**
Los operadores son símbolos que le indican al intérprete que realice una operación específica, como aritmética, comparación, lógica, etc.

Algunos tipos de operadores son:

OPERADORES ARITMETICOS:

|OPERADOR| DESCRIPCION                               |
|--------|-------------------------------------------|
|+       | Suma dos numeros                          |
|-       |Resta dos numeros                          |
|*       |Multiplica dos numero                      |
|/       |Divide dos numeros                         |
|%       |Obtiene el modulo de una operacion         |
|**      |Eleva un numero a una determinada potencia |
|//      |Divide dos enteros(dejando un residuo)     |

OPERADORES LOGICOS:
|OPERADOR|DESCRIPCION                                      |
|--------|-------------------------------------------------|
|and     |Devuelve True si ambos operandos son True        |
|or      |Devuelve True si alguno de los operandos es True |
|not     | Devuelve True si alguno de los operandos False  |

OPERADORES DE COMPARACIONO RELACIONALES:
       
|OPERADOR |DESCRIPCION       |
|---------|------------------|
|==       |Igual que         |
|!=       |Distindo que      |
|>        |Mayor que         |
|<        |Menor que         |
|>=       |Mayor o igual que |
|<=       |Menor o igual que |


|OPERADOR |DESCRIPCION       |
|---------|------------------|


## **Tipos de Datos**
## **Condicional IF**
## **Ciclo FOR**
## **Ciclo WHILE**
## **Funciones**
## **Manejo de Cadenas de Texto**
## **Listas**
## **Diccionarios**
## **Tuplas**






Informacion complementaria 
https://www.programarya.com/Cursos/Python
