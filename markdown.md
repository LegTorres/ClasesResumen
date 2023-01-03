___
# **INTRODUCCION A MARKDOWN**

Markdown es un lenguaje de marcado ligero creado por John Gruber y Aaron Swartz que trata de conseguir la máxima legibilidad y facilidad de publicación tanto en su forma de entrada como de salida, inspirándose en muchas convenciones existentes para marcar mensajes de correo electrónico usando texto plano.Se distribuye bajo licencia BSD y se distribuye como plugin (o al menos está disponible) en diferentes sistemas de gestión de contenidos (CMS).

**Tabla de contenidos**

- [Encabezados](#encabezados)
- [Parrafos](#parrafos)
- [Negritas y Cursivas](#negritas-y-cursivas)
- [Citas](#citas)
- [Listas Ordenadas y Desordenadas](#listas-ordenadas-y-desordenadas)
- [Reglas Horizontales](#reglas-horizontales)
- [Bloques de Codigos](#bloques-de-codigo)
- [Tablas](#tablas)
- [Enlaces](#enlaces)
- [Imagenes](#imagenes)
- [Anular Simbolos Markdown](#anular-simbolos-markdown)

___

## **ENCABEZADOS**

Para crear un encabezado en Markdown se antepone un simbolo numeral delante de texto del encabezado, separado por un espacio. El nivel del encabezado se define segun el numero de signos numerales. Un solo numeral equivale a un h1 en HTML, mientras que 6 numerales equivalen a un h6. 

Ejemplo:

~~~md
# Este es un encabezado equivalente a un <h1> </h1>
###### Este es un encabezado equivalente a un <h6> </h6>
~~~

> Resultado:
>
> # Este es un encabezado equivalente a un `<h1> </h1>`
> ###### Este es un encabezado equivalente a un `<h6> </h6>`

Existe una sintaxis alternativa para para los encabezados nivel 1 y nivel 2. Para el primero se colocan en la linea inmediatamente inferior tantos signos igual como la longitud de el texto del encabezado, mientras que para el encabezado nivel 2 se colocan giones simples.  

Ejemplo:

~~~md
Encabezado nivel 1
==================

Encabezado nivel 2
------------------
~~~

> Resultado:
>
> Encabezado nivel 1
> ==================
>
> Encabezado nivel 2
> ------------------

## **PARRAFOS**

Para generar un nuevo parrafo se deja una linea en blanco entre ambos parrafos.  
Para iniciar una nueva linea dentro del mismo parrafo se tiene que pulsar dos veces la **barra espaciadora** antes de presionar **intro**

> Nota: Markdown al igual que HTML no permite doble linea entre parrafo, por lo que sin importar cuantas lineas en blanco se dejen, al momento de visualizarse se mostraran como una sola.

## **NEGRITAS Y CURSIVAS**

Para dar formato al texto, ya sea en negrita como con cursiva, se puede lograr encerrando la palabra o frase (tambien funciona en silabas de una palabra) que queramos resaltar entre **asteriscos** o entre **guiones bajos**.

La combinacion para dar formato a los parrafos es la siguiente:
- **Cursiva**: Se coloca **UN** asterisco (\*) o gion bajo (\_) al principio y al final.
- **Negrita**: Se coloca **DOS** asteriscos o guiones bajos al principio y el final.

- **Negrita y Cursiva**: Se coloca **TRES** asteriscos o guiones bajos al principio y el final.

Ejemplo:

~~~md
Texto en *cursivas* utilizando asteriscos.

Texto en _cursivas_ utilizando guiones bajos.

Texto en **negritas** utilizando asteriscos.

Texto en __negritas__ utilizando guiones bajos.

Texto en ***negrita y en cursivas*** utilizando asteriscos.

Texto en ___negrita y en cursivas___ utilizando guiones bajos.

Resaltando una si**la**ba con asteriscos.

Resaltando una si__la__ba con guiones bajos.
~~~

> Resultado:
>Texto en *cursivas* utilizando asteriscos.
>
> Texto en _cursivas_ utilizando guiones bajos.
> 
> Texto en **negritas** utilizando asteriscos.
>
> Texto en __negritas__ utilizando guiones bajos.
> 
> Texto en ***negrita y en cursivas*** utilizando asteriscos.
>
> Texto en ___negrita y en cursivas___ utilizando guiones bajos.
> 
> Resaltando una si**la**ba con asteriscos.
>
> Resaltando una si__la__ba con guiones bajos.

## **CITAS**

Para crear citas se agrega el simbolo **mayor que** delante de la linea de texto.  

Ejemplo:

~~~md 
> Primera linea de la cita
>
> Continuando en un segundo parrafo
>> Cita anidada
>> Segundo subparrafo
~~~

> Resultado:
>
> Primera linea de la cita
>
> Continuando en un segundo parrafo

Para crear una cita con diferentes subniveles (anidadas) se agrega dos o mas signo de mayor que dependiendo del nivel que necesitemos definir.  
Es importante separar los saltos de linea si nos encontramos en una cita anidada.

Ejemplo:

~~~md
> Primer nivel de la cita
>> Cita anidada, nivel dos.   
>> Segundo subparrafo en nivel dos.
>>> Tercer nivel.  
>
> Linea en primer nivel. 
~~~

> Resultado:
>
> Primer nivel de la cita
>> Cita anidada, nivel dos.   
>> Segundo subparrafo en nivel dos.
>>> Tercer nivel.  
>
> Linea en primer nivel. 

## **LISTAS ORDENADAS Y DESORDENADAS**

### Desordenadas:

Para crear listas desordenadas se pueden utilizar los simbolos de **Asteriscos** \*, **Guiones** \-, o **Mas** \+.  Estos se pueden combinar sin problemas.
Para crear listas anidadas, se coloca el equivalente a cuatro espacios (o bien presinando la tecla *TAB*).

Ejemplo:

~~~md
- Elemento 1
    - Subelemento con tecla TAB 
- Elemento 2
- Elemento 3
* Elemento 4
    + Subelemento con cuatro espacios
+ Elemento 5
~~~

> Resultado:
>
> - Elemento 1
>    - Subelemento con tecla TAB 
> - Elemento 2
> - Elemento 3
> * Elemento 4
>    + Subelemento con cuatro espacios
> + Elemento 5

### Ordenadas:

Para una lista ordenada se coloca el numero del item seguido por un punto delante de cada elemento de la lista. Se pueden combinar ambos tipos de listas.

Ejemplo:

~~~md
1. Elemento 1
2. Elemento 2
    1. Sub elemento 2.1
    2. Sub elemento 2.2
3. Elemento 3
    - Subelemento desordenado
    - Subelemento desordenado dentro de una lista ordenada 2
~~~

> Resultado:
>
> 1. Elemento 1
> 2. Elemento 2
>     1. Sub elemento 2.1
>     2. Sub elemento 2.2
> 3. Elemento 3
>     - Subelemento desordenado
>     - Subelemento desordenado dentro de una lista ordenada 2


## **REGLAS HORIZONTALES**

Para separar secciones de una manera visual dentro del documento se utilizan las reglas horizontales. Para ello podemos utilizar tres simbolos de **Asteriscos** \*\*\*, **Guiones simples** \-\-\- o **Guiones Bajos** \_\_\_. Pueden ir juntos o separados por un espacio para fines esteticos.

Ejemplo:

~~~md
***
---
___

<!-- Separados por espacios -->

* * *
- - -
_ _ _
~~~

> Resultado:
> 
> ***
> ---
> ___
> 
> <!-- Separados por espacios -->
> 
> * * *
> - - -
> _ _ _

## **BLOQUES DE CODIGO**

Si queremos agregar bloques que contengan codigo de algun lenguaje de programacion encerramos dicho bloque entre dos lineas con tres **virgulillas** \~\~\~ o con tres **tildes invertidas** \`\`\`, cada una al principio y al final del bloque.  
Para especificar el lenguaje enmarcado en el bloque de codigo podemos hacerlo escribiendo el **nombre del lenguaje** o bien la **extension** detras de las tres virgulillas de la primer linea. 

Ejemplo con **Virgulillas**:

```md
~~~py
def main():
    print("Hola mundo")


if __name__ == '__main__':
    main()
~~~
```

Ejemplo con **Tildes invertidas**:

~~~md
```python
def main():
    print("Hola mundo")


if __name__ == '__main__':
    main()
```
~~~

> Resultado:
> 
> ```python
> def main():
>     print("Hola mundo")
> 
>
> if __name__ == '__main__':
>     main()
> ```

Otra manera de crear un bloque de codigo es agregando cuatro espacios en blanco delante de cada linea respetando el sangrado del codigo fuente.  Esta linea debe comenzar con los cuatro espacios en blanco, de lo contrario (Como especificando una cita, por ejemplo) no funcionara.  
Es muy util cuando se quire mostrar una sola linea de codigo, pero cuando se quieren colocar varias lineas es mejor usar el metodo anterios (con las **virgulillas** o **tildes invertidas**), ya que sera necesario agregar los cuatro espacios al inicio de cada una de las lineas de codigo.

Ejemplo:

~~~md
<!-- Ejemplo de codigo dentro de markdown -->
    def main():
        print("Hola mundo")


    if __name__ == '__main__':
        main()


<!-- Fin del bloque de codigo -->
~~~

> Resultado: 

    def main():
        print("Hola mundo")
    
    
    if __name__ == '__main__':
        main()
    
    

Lod metodos anteriores nos generan un bloque de codigo. Si queremos espeificar codigo dentro de una linea de texto lo hacemos encerrando la linea de codigo dentro de **tildes invertidas** \` \`.

Ejemplo:

~~~md
Ejemplo de especificar codigo de un lenguaje, como por ejemplo, el de una etiqueta `<strong>html</strong>` en una linea en markdown.
~~~

> Resultado:
> 
> Ejemplo de especificar codigo de un lenguaje, como por ejemplo, el de una etiqueta `<strong>html</strong>` en una linea en markdown.

## **TABLAS**

Para crear tablas en markdown se utiliza el simbolo de **barra vertical** (\|) antes y despues de cada elemento para separar las columnas. El encabezado  se crea en la primer linea; la segunda sirve para separar el encabezado del contenido de la tabla agregando tres o mas **guiones simples**; y de la tercer linea en adelante se agrega el contenido.

Ejemplo:

~~~md
|Header 1   |Header 2   |Header 3   |
|-----------|-----------|-----------|
|Item 1     |Item 1.2   |Item 1.3   |
|Item 2     |Item 2.2   |Item 2.3   |
|Item 3     |Item 3.2   |Item 3.3   |
|Item 4     |Item 4.2   |Item 4.3   |
~~~

> Ejemplo:
>
>|Header 1   |Header 2   |Header 3   |
> |-----------|-----------|-----------|
> |Item 1     |Item 1.2   |Item 1.3   |
> |Item 2     |Item 2.2   |Item 2.3   |
> |Item 3     |Item 3.2   |Item 3.3   |
> |Item 4     |Item 4.2   |Item 4.3   |

## **ENLACES**

Existen varios tipos de link dentro de un documento Markdown, estos pueden ser:
- **En linea**: (los de toda la vida). 
- **Enlaces como referencia**: estos tienen la ventaja de que nos permiten crear un contenido de una manera mas ordenada y legible, ya que cuando un enlace contiene links demasiado complejos estos se pueden volver dificiles de leer. Para solucionar esto, los enlaces como referencia enlazan palabras o codigos concretos definidos en otro apartado del documento, simplificando asi su lectura.  
Para definir este tipo de enlaces se usa un par de corchetes en lugar de parentesis para escribir la referencia.
- **Enlaces automaticos**; estos ultimos consisten en escribir entre signos **menor y mayor que** (\< \>) el **URL** del enlace tal cual. Esta opcion es util si lo que queremos es escribir la URL completa

Un enlace consta de dos partes (excepto los enlaces automaticos): El texto que mostrara el enlace que se escribira entre **corchetes** \[ \] y la ruta o URL que se escribira entre parentesis ( ). Adicional al URL se puede escribir una descripcion del sitio a donde lleva el enlace escribiendolo dentro de **comillas dobles** " "

Ejemplos:

~~~md
<!-- Ejemplo de un enlace en linea -->
[Google](https://google.com "Enlace al buscador de Google")

<!-- Ejemplo de un enlace de referencia -->
[GitHub](sitioGH)

<!-- Ejemplo de un enlace automatico -->
<https://youtube.com>

<!-- Definiendo la referencia para el enlace-->
[sitioGH]: https://github.com "Enlace al sitio de GitHub"
~~~

> Resultado
>
<!-- Ejemplo de un enlace en linea -->
> [Google](https://google.com "Enlace al buscador de Google")
>
><!-- Ejemplo de un enlace de referencia -->
>[GitHub][sitioGH]
>
<!-- Ejemplo de un enlace automatico -->
><https://youtube.com>

Para crear enlaces a secciones dentro del mismo documento simplemente hay que cambiar el **URL** por el nombre del encabezado de la seccion a donde queremos enlazar. Es importante que el URL vaya precedido por por el signo numeral, y los espacios deben cambiarse por guiones, ademas de que todo debe escribirse en minuscula.

Ejemplo:

~~~md
[Titulo](#encabezado-principal)

## Encabezado principal
~~~

<!-- Definiendo la referencia para el enlace-->
[sitioGH]: https://github.com "Enlace al sitio de GitHub"

## **IMAGENES**

Las imagenes se crean de manera similar a los enlaces, solo agregando un signo de exclamacion de cierre (!) al principio.

Ejemplo:

~~~md
<!--Imagenes -->
![Tux](./assets/tux.png "Tux, mascota de Linux")
~~~

> Resultado:
>
>![Tux](./assets/tux.png "Tux, mascota de Linux")

Al igual que con los enlaces, se pueden utilizar referencias para acceder a la imagen



## **ANULAR SIMBOLOS MARKDOWN**

Si queremos que algunos simbolos dejen de ser interpretados como codigo Markdown y que en su lugar se muestren como texto plano podemos hacerlo colocando una **barra invertida** (\\) delante del simbolo cuya funcion queremos anular. 

Por ejemplo:

~~~md
<!-- Mostrando un simbolo mayor que: -->
\>
~~~

> Resultado
>
> Mostrando un simbolo mayor que: \>
