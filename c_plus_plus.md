# **Curso de C++**
C++ es un lenguaje de programación diseñado en 1979 por Bjarne Stroustrup. La intención de su creación fue extender al lenguaje de programación C y añadir mecanismos que permiten la manipulación de objetos. En ese sentido, desde el punto de vista de los lenguajes orientados a objetos, C++ es un lenguaje híbrido.

## **El proceso de compilacion**
1. Escribir el codigo fuente en un archivo .cpp o .h: en un IDE
2. Preprocesamiento: Archivos incluidos, sombolos reemplazados.
3. compilacion: Codigos de objetos .obj o .o.
4. Link Edit: El programa linker se encarga de juntar el codigo fuente despues de haber sido procesado y compilado en ocodigo objeto con las librerias o dependencias necesarias.
5. Load: El loader es el programa que arranca la ejecucion de nuestro programa e importa las librerias que se pueden incluir de manera dinamica, es decir que no necesitan incluirse en el ejecutable de nuestro programa sino que ya puedan estar instaladas en el sistema operativo de destino y que se comuniquen con ellas.
6. Ejecucion: El programa sera monstado en memoria y sus instrucciones seran ejecutadas una tras otra por el CPU y genera los datos de salida.

## **Algunos tipos de datos de C++**
--------------
|Tipo de dato|Tipo de valor|Tamaño|Descripcion|
|--|--|--|
|bool|Valor logico|4 Bytes| |
|int|Numero entero|4 Bytes|Se utiliza un bit para el signo positivo o negativo.|
|float|Numero de punto flotante (Decimal)|4 Bytes|Se almacenan las bases y los exponentes para almacenarlos en lenguajes como C++.|
|double|Numero de punto flotante de doble posicion|8 Bytes|Puedes almacenar numeros mucho mas grandes que con tipos de datos float.|
|char|Caracter ASCII|1 Byte|Puede almacenar el caracter o su valor numerico.|

> Es recomendable verificar cuales son los tamanos reales de los tipos de datos en la plataforma para la que vamos a compilar y tambien los del compilador, pues en muchos casos esos valores son diferentes.

## **Declaracion de variables**
Para declarar variables debemos indicar el tipo de datos, el nombre de la variable y opcionalmente un valor inicial.

~~~c++
/* Ejemplo: */
int numero = 10;
~~~

Para agregar un salto de linea se agrega << endl; al final de la funcion cout.