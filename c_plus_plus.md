# **CURSO DE C++**
C++ es un lenguaje de programación diseñado en 1979 por Bjarne Stroustrup. La intención de su creación fue extender al lenguaje de programación C y añadir mecanismos que permiten la manipulación de objetos. En ese sentido, desde el punto de vista de los lenguajes orientados a objetos, C++ es un lenguaje híbrido.

**Tabla de Contenido**

- [El Proceso de Compilacion](#el-proceso-de-compilacion)
- [Algunos Tipos de Datos](#algunos-tipos-de-datos-de-c)
- [Estructura Basica de un Programa en C++](#estructura-basica-de-un-programa-en-c)
- [Declaracion de Variables, Constantes y Listas](#declaracion-de-variables-constantes-y-listas)
- [Operadores](#operadores)
- [Entrada y Salida de Datos](#entrada-y-salida-de-datos)
- [El Condicional IF](#el-condicional-if)
- [El Condicional SWITCH](#el-condicional-switch)
- [El Ciclo FOR](#el-ciclo-for)
- [El Ciclo WHILE y DO-WHILE](#el-ciclo-while-y-do-while)
- [Funciones, Metodos y Procedimientos en C++](#funciones-metodos-y-procedimientos-en-c)
- [Bibliotecas](#bibliotecas)
- [Acerca de using namespace std;](#acerca-de-using-namespace-std)
- [Comentarios en C++](#comentarios-en-c)

## **El Proceso de Compilacion**
1. Escribir el codigo fuente en un archivo **.cpp** o **.h**: en un IDE
2. Preprocesamiento: Archivos incluidos, simbolos reemplazados.
3. compilacion: Codigos de objetos .obj o .o.
4. Link Edit: El programa linker se encarga de juntar el codigo fuente despues de haber sido procesado y compilado en ocodigo objeto con las librerias o dependencias necesarias.
5. Load: El loader es el programa que arranca la ejecucion de nuestro programa e importa las librerias que se pueden incluir de manera dinamica, es decir que no necesitan incluirse en el ejecutable de nuestro programa sino que ya puedan estar instaladas en el sistema operativo de destino y que se comuniquen con ellas.
6. Ejecucion: El programa sera monstado en memoria y sus instrucciones seran ejecutadas una tras otra por el CPU y genera los datos de salida.

## **Algunos Tipos de Datos de C++**
|Tipo de dato|Tipo de valor|Tamaño|Descripcion|
|--|--|--|--|
|bool|Valor logico|4 Bytes| |
|int|Numero entero|4 Bytes|Se utiliza un bit para el signo positivo o negativo.|
|float|Numero de punto flotante (Decimal)|4 Bytes|Se almacenan las bases y los exponentes para almacenarlos en lenguajes como C++.|
|double|Numero de punto flotante de doble posicion|8 Bytes|Puedes almacenar numeros mucho mas grandes que con tipos de datos float.|
|char|Caracter ASCII|1 Byte|Puede almacenar el caracter o su valor numerico.|

> Es recomendable verificar cuales son los tamanos reales de los tipos de datos en la plataforma para la que vamos a compilar y tambien los del compilador, pues en muchos casos esos valores son diferentes.

## **Estructura Basica de un Programa en C++**
Podemos ver la estructura basica de un programa en el siguiente ejemplo, donde imprimimos en pantalla el mensaje de **Hola Mundo**:

~~~cpp
#include <iostream>

using namespace std;

int main()
{
    cout << "Hola Mundo" << endl;
}
~~~

La librería **iostream**, te permite recibir datos de entrada o mostrar datos de salida.  
**using namespace std**, te permite utilizar, en el código, nombres estandar de C++, para poder importarlas sin necesidad de escribir desde donde la estamos importando.  
La función `main()`, es la funcion principal de nuestro código. Es lo primero que ejecuta el programa.  
Para mostrar en pantalla, utilzar `cout << "Un texto"`, que seria una salida en C++. `<< endl` agrega un salto de linea al final de nuestro texto. Tambien podemos agregar un salto de linea escribiendo `\n` dentro de nuestra cadena de caracteres.

## **Declaracion de Variables, Constantes y Listas**
Para declarar variables debemos indicar el tipo de datos, el nombre de la variable y opcionalmente un valor inicial. No se pueden utilizar guiones simples(-) para el nombre de las variables, pero si se puede usar el gion bajo (_).

~~~c++
/* Ejemplo: */
int numero = 10;
~~~

Para crear una constante se agrega la palabra `const` delante de la declaracion de la variable.

~~~cpp
const char letra = 'A';
~~~

Para declarar una lista de elementos debemos especificar el tipo de datos que contendra nuestra lista, ademas de colocar **corchetes** detras del nombre de la lista, luego debemos colocar los valores de la lista dentro de corchetes, y cada uno de estos valores debe ir separados por comas.

~~~cpp
int lista_edades[] = {18, 25, 32, 40};
~~~

Para accedere a los elementos lo hacemos a traves de los indices de la lista, de esa manera podemos leer el valor almacenado o modificarlos por uno diferente.  
Ejemplo:

~~~cpp
lista_edades[1] = 26;
cout << lista_edades[1];
~~~

## **Operadores**
Existen varios tipos de operadores dentro de C++. ALgunos de ellos son:

|TIPO        |OPERADORES                      |
|------------|--------------------------|
| Aritmeticos|+  -  *  /  %             |
| Comparacion|==  !=  >  <  >=  <=      |
| Aignacion  |=  +=  -=  *=  /=  ++  -- |
| Logicos    |&&  \|\|  !               |
| Otros      |sizeof  <<  >>            |

> NOTA: `sizeof(variable)` nos permite saber el tamaño en bytes de una variable u objeto. Esto son podria ser de mucha utilidad para saber el numero de elementos que posee una lista, dividiendo el tamaño en bytes de la lista entre el numero de bytes que tiene el tipo de datos.

> El operador logico `!` nos permite invertir el valor logico de una operacion, por lo tanto si el valor es **verdadero** se convertira en falso y viceversa.

## **Entrada y Salida de Datos**
Las entradas y salidas de datos en C++ se manejan por medio de la libreria **iostream**. Para direccionar una cadena de caracteres hacia la pantalla a traves de **cout** se utiliza el operadores de direccionamiento **<<**, para direccionar un texto desde la pantralla hacia una variable o funcion se utiliza **cin** junto con el operador de direccionamiento **>>**.  
Por ejemplo:

~~~cpp
int edad = 0;
cout << "Ingresa tu edad: ";
cin >> edad;
cout << "Tu edad es: " << edad;
~~~

## **El Condicional IF**
La estructura **if** nos permite realizar una accion en funcion de si se cumple una condicion o no.  
Ejemplo:

~~~cpp
// Programa que permitiria votar a personas que esten dentro de 18 y 40 años de edad.
if (edad < 18) {
    cout << "No puedes votar";

}
else if (edad > 40) {
    cout << "No puedes Votar";
}
else {
    cout << "Puedes Votar";
}
~~~

## **El Condicional SWITCH**
La estructura **switch** permite elegir entre multiples opciones especificas. Segun el valor de la opcion a evaluar se ejecutara el codigo dentro del bloque **case** que coincida con el valor asignado.  

~~~cpp
 int opcion = 0;
cout << "Ingresa una opcion del menu: \n";
cin >> opcion;

switch (opcion) {
    case 1:
        cout << 'Opcion 1';
        break;
    case 2:
        cout << "Opcion 2";
        break;
    default:
        cout << "Opcion incorrecta" << endl;
}
~~~

> Nota:Es importante colocar la sentencia **break** al final del bloque **case**, ya que de no hacerlo se ejecutara el codigo dentro de la sentencia **default**.

## **El Ciclo FOR**
Los ciclos for son lo que se conoce como **estructuras de control de flujo cíclicas** o simplemente **estructuras cíclicas**, y permiten ejecutar una o varias líneas de código de forma iterativa. PAra ello especificamos:

1. Un valor especifico inicial.
2. El valor final
3. Determinar el tamaño del paso entre cada "giro" o iteración del ciclo.

Ejemplo:

~~~cpp
// Imprimiendo los numeros de el 0 al 9    
for(int i = 0; i < 10; i++){
    cout << i << endl;
}
~~~

Podemos recorrer los elementos de una lista.  
Por ejemplo:

~~~cpp
int lista[] = {100, 200, 300, 400, 500, 600, 700, 800, 900,1000};

for (int i = 0; i < sizeof(lista) / sizeof(lista[0]); i += 1){
    cout << lista[i] << endl;
   
}
~~~

Podemos romper un ciclo utilizando la palabra `break`, de ese modo las siguientes iteraciones del ciclo no se ejecutaran.

~~~cpp
for(int i = 0; i < 10; i++){
    cout << i << endl;

    if (i == 5){
        break;
    }
}
~~~

## **EL Ciclo WHILE y DO-WHILE**
Al igual que el ciclo **for** los ciclos **while** y **do while** son estructuras cíclicas, que permiten ejecutar una o varias líneas de código de manera repetitiva sin necesidad de tener un valor inicial e incluso a veces sin siquiera conocer cuando se va a dar el valor final que se espera. Dependen de valores booleanos, de este modo, son mucho más efectivos para condiciones indeterminadas, que no conocemos cuando se van a dar.


~~~cpp
/*
*   Ejemplo de un programa que pida al usuario que adivine un numero entre uno y diez, 
*   y mientras no acierte que le pida ingresar un nuevo numero
*   hasta que ingrese el numero, que en este caso es 3.
*/

int numero;
cout << "Ingresa un numero entre 1 y 10: ";
cin >> numero;

while (numero != 3) {
    cout << "No has adivinado, ingresa otro numero: \n";
    cin >> numero;
}
~~~

Al diferencia del bucle **while**, que comprueba la condición antes de entrar en el bucle, la estructura **do - while** la evalúa al final. Esto implica que el ciclo se ejecutará al menos una vez.

Al igual que el ciclo **for**, los ciclos **while** y **do while** se pueden romper con la sentencia `break`.

Ejemplo:

~~~cpp
/*
*   pedir al usuario que confirme si desea salir del programa, 
*   y que este no se cierre mientras el no especifique que desea salir.
*/

char respuesta;

do {
    cout << "Deseas finalizar el segundo programa?";
    cin >> respuesta;
    if(respuesta == 'y' || respuesta == 'Y'){
        cout << "Saliendo del segundo programa!!!!" << endl;
        break;
    }
} while (true);
~~~

## **Funciones, Metodos y Procedimientos en C++**
Aunque se acostumbre a usar los tres terminos de manera indistinta es necesario aclarar que estas poseen diferencias fundamentales:
- **Funciones**:  
Son un conjunto de procedimiento encapsulados en un bloque, usualmente reciben parámetros y siempre **retornan** un valor. Siempre debe especificarse el tipo de dato de la funcion, y esta debe coincidir con el tipo de dato que retornará.
- **Metodos**:  
Son idénticos a las funciones, pero su diferencia radica en el contexto en el que existen. Un método también puede recibir valores, efectuar operaciones con estos y retornar valores, sin embargo está asociado a un objeto. Básicamente un método es una función que pertenece a un objeto o clase, mientras que una función existe por sí sola, sin necesidad de un objeto para ser usada.
- **Procedimientos**:  
Son básicamente un conjunto de instrucciones que se ejecutan **sin retornar ningún valor**, aun que no suelen recibir valores o argumentos en la definición no hay nada que se lo impida. En el contexto de C++ un procedimiento es básicamente una función void que no nos obliga a utilizar una sentencia return.

Ejemplo de declaracion de una funcion:

~~~cpp
#include <iostream>

using namespace std;

int suma(int a, int b = 0) {
    cout << "Sumando " << a << " mas " << b << endl;
    return a + b;
}

int main() {
    cout << suma(5, 12) << endl;

}
~~~

> Es necesario tener presente que cualquier instruccion que se encuentre después de el return NO será ejecutada. Es común encontrar funciones con múltiples sentencias return al interior de condicionales, pero una vez que el código ejecuta una sentencia return lo que haya de allí hacia abajo no se ejecutará.

Como los procedimientos no retornan valores no tienen un tipo especifico, y se declaran escribiendo la palabra `void` delante del nombre de la función. 

Ejemplo de declaracion de un procedimiento:

~~~cpp
#include <iostream>
#include <string>

using namespace std;

void imprimirNombre (int num, string nombre) {
    if (nombre == "") {
        cout << "El nombre esta vacio";
        return;
    }

    for (int i = 1; i <= num; i++) {
        cout << i << " " << nombre << "\n";
    }
}

int main()
{
    imprimirNombre(10, "Fulanito de Tal");
}
~~~

> Los procedimientos también pueden usar la sentencia return, pero no con un valor. En los procedimientos el return sólo se utiliza para finalizar allí la ejecución de la función.

## **Bibliotecas**
Las **bibliotecas**, del ingles **library**, tambien conocidas como **librerias** son cierto tipo de archivos que podemos importar o incluir en nuestro programa. Estos archivos, generalmente terminados con la extension **.lib, .bpl, .a, .dll, .h**, entre otras, contienen las especificaciones de diferentes funcionalidades ya construidas y utilizables que podremos agregar a nuestro programa. Permiten hacer nuestros programas más modulares y reutilizables, facilitando además crear programas con funcionalidades bastante complejas en unas pocas líneas de código.

La sintaxis para declarar una biblioteca en C++ es la siguiente: `#include <nombredelalibrería>` o alternativamente `#include "nombredelalibrería"`. 

ALgunas bobliotecas estandar de C++ son:

|BIBLIOTECA  |FUNCION                         |
|------------|--------------------------------|
|iostream    |Entrada y salida de datos.      |
|string      |Manejo de cadenas de texto.     |
|cmath       |Funciones matematicas comunes.  |
|exception   |Utilidad para manejo de errores.|
|array       |Manejo de arreglos de datos.    |
|vector      |Manejo de vectores de datos.    |

Algunas de las funciones de la biblioteca **string** son:

|FUNCION         |DESCRIPCION                                       |
|----------------|--------------------------------------------------|
|variable.size() |Retorna la longitud de la cadena de texto         |
|stoi(variable)  |Retorna el valor de un texto convertido en entero |
|stof(variable)  |Retorna el valor de un texto convertido en float  |

~~~cpp
#include <iostream>
#include <string>

using namespace std;

int main() {
    string nombre = "Fulanito de Tal";
    cout << nombre << endl;

    cout << "Longitud de la cadena de texto: " << nombre.size() << endl;

    string numero = "10";
    cout << "Convirtiendo texto a entero: " << stoi(numero);

    string flotante = "10";
    cout << "Convirtiendo texto a float: " << stoi(flotante);
}
~~~

> NOTA: El valor de las variables de tipo string deben escribirse entre comillas dobles, de lo contrario producirá un error.

## **Acerca de `using namespace std;`**
Esta linea permite declarar un espacio de nombre y evita tener que usarlo cada que accedemos a alguna función especifica de una librería. Teniendo este namespace declarado podemos llamar, por ejemplo, el comando `cout << "Texto";`, que pertenece a la librería **iostream**. De no especificarse en dicha lineatendriamos que escribir el namespace cada vez que llamemos alguna de sus funciones, porejemplo: `std::cout << "Texto";`.

## **Comentarios en C++**
Para crear comentarios en C++ tenemos dos opciones.
- **Comentarios de una sola linea**:  
Se crean colocando dos simbolos de barra inclinada(//) delante de el texto que queremos comentar:
- **Comentarios multi linea**:  
Se crean escribiendo barra y asterisco(/\*) al inicio y con asterisco y barra(\*/) al final.  

Ejemplo:

~~~cpp
// Ejemplo de un comentario de una sola linea.

/*
Ejemplo de un comentario
con multiples lineas
en C++
*/
~~~