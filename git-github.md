___
# **INTRODUCCION A GIT Y GITHUB**

Git es un sistema de control de versiones (SCV por sus siglas en ingles) distribuido creado por Linus Torvalds. Lleva el control los cambios en el proyecto y tambien permite coordinar el trabajo de varias personas. Este guarda solo los cambios (Cuando se hicieron, o quien los realizo, etc.), lo cual lo hace el trabajo mucho mas eficiente.

Git esta optimizado para guardar cambios de forma incremental.Permite contar con un historial, regresar a una version anterior y agregar funcionalidades.Lleva un registro de los cambios que otras personas realicen en los archivos.

Cuales son las caracteristicas de git?
- Git almacena la informacion como un conjunto de archivos.
- No existen cambios, corrupcion o cualquier alteracion sin que git lo sepa.
- Casi todo en git es local. Es dificil que se necesiten recursos externos.
- Git cuenta con tres estados en los que es posible localizar un archivo:
    - STAGED
    - MODIFIED
    - COMMITED


**Tabla de contenidos**

- [Ramas \(Branches\)](#ramas-o-branch)
- [Repositorios remotos en Github](#repositorios-remotos-en-github)
- [Conexiones cifradas por SSH](#conexiones-cifradas-con-ssh)









## **RAMAS O BRANCHES**
Una rama es una version del codigo de nuestro proyecto. Ayudan a mantener el orden y a manipular el codigo de forma segura. Las ramas mas populares en el desarrollo de proyectos de software son:
- **Rama main:** Es la rama por defecto de nuestro proyecto.
- **Rama development:** Suelen ser ramas para hacer experimentos con nuestro codigo sin necesidad de afectar nuestro codigo principal.
- **Rama hotfix:** Tambien se les suele llamar bug fixing y se crean al detectar algun error critico en nuestro proyecto principal para hacer los arreglos necesarios. Cuando esta corregido se fusiona con la rama principal a traves del comando merge.

El comando que nos muestra las ramas que tiene un proyecto es el siguiente:

~~~GIT
$ git show-branch --all
~~~

A la union de diferentes ramas de un proyecto se le llama **merge**. 


> Nota: Hay que tener en cuenta que al hacer merge puede haber archivos que provoquen conflicto con otros archivos del proyecto.


Cuales tipos de reset que hay?
-Reset duro(Hard): Vuelve a la version tal cual estaba en su momento.
- Reset suave(soft): Vuelve a la version anterior, pero lo que tengamos en staging continuara disponible para el proximo commit.
- Reset mixed: Elimina los cambios hasta el working area.

Que representa la cabecera(HEAD)?
Representa la rama y el commit de dicha rama donde estamos trabajando. Por defecto, sera la rama main.

Que es un conflicto en git?
Es cuando dos ramas diferentes hacen cambios distintos en una misma linea.

Que es el estado unmerged?
Es el estado en el que entran los archivos luego de hacer un merge en el que se detectan conflictos.

Los merges tambien son commits?
Verdadero.

Como se arregla un conflicto durante un merge?
Se arregla borrando la linea que no queremos conservar. Eso puede ser automaticamente con editores como visual studio code o manual, borrando la linea que no nos interesa.


## **REPOSITORIOS REMOTOS EN GITHUB**

Es una plataforma de desarollo colaborativo para alojar proyectos utilizando git. Se emplea principalmente para la creacion de codigo fuente de programadores. Se puede considerar como un curriculum vitae, pues aqui se guarda el portafolio de proyectos de programacion.

Cuales son las caracteristicas de GitHub?
- Permite alojar proyectos en repositorios de manera gratuita y publica, aunque tiene una forma de pago para privados.
- Puedes compartir facilmente tus proyectos.
- Permite colaborar para mejorar los proyectos de otros y viceversa.
- Ayuda a reducir significativamente los errores humanos, a tener un mejor mantenimiento de sistintos entornos y detectar fallos de una manera mas rapida y eficiente.
- Es la opcion perfecta para poder trabajar en equipos dentro de un mismo proyecto.
- Ofrece todas las ventajas de git, pero tambien ofrece otras herramientas para un mejor control de proyectos.

Que es GitHub?
Es una plataforma que nos permite guardar repositorios de Git utilizandolos de manera remota y ejecutar algunos comandos de manera visual e interactiva.

Luego de crear nuestra cuenta en GitHub que podemos hacer?
- Crear o importar repositorios.
- Crear organizaciones y proyectos de trabajo.
- Descubrir repositorios de otras personas.
- Contribuir a proyectos de otros.
- Dar estrellas y muchas otras cosas.


Que es el README.md?
Es un archivo que veremos por defecto al entrar en un repositorio. Es muy buena practica configurarlos para describir el proyecto, los requerimientos y las instrucciones a seguir para contribuir correctamente.


Comos se clona un repositorio desde GitHub?
Se debe copiar el URL y ejecutar el comando $ git clone URL. Eso descargara la version del proyecto alojado en GitHub.


Cuales son los pasos a seguir para conectar un repositorio de GitHub con nuestro repositorio local?
- $ git remote add origin URL: Guardar la URL del repositorio de githhub con el nombre origin.
- $ git remote -v: Verificar que la URL se haya guardado correctamente.
- $ git pull origin main --allow-unrelated-histories: Traer la version del repositorio remoto y hacer merge para crear un commit con los archivos de ambas partes. Pull es la combinacion fetch y merge.
- $ git push origin main: Guardamos los cambios de nuestro repositorio local en GitHub.


Como te autenticas en GitHub 2022?
- Renombrar la rama master a main. Para eso debemos estar posicionados en la rama a la que queremos renombrar y ejecutar: 
    $ git branch -M main.
- Crear un token de acceso personal, y usarlo como contrasena cuando nos pida clave:
    - Settings > Developer settings > Personal access tokens > Generate new token\(Se puede colocar un nombre, una fecha de expiracion, etc?\) > Tildar en repo > Generate token. 

Como se envia una rama a GitHub\(Despues de haber hecho pull\)
```
$ git push origin rama-a-enviar
```

## **CONEXIONES CIFRADAS CON SSH**



Para que sirven las claves publicas y privadas(Cifrado asimetrico de un solo camino)
Para mandar mensajes privados entre varios nodos con la logica de que firmas tu mensaje con una llave publica vinculada a una llave privada que puede leer el mensaje para asi evitar el riesgo de que sea interceptado por algun atacante.


Como funciona un mensaje cifrado con llaves publicas y privadas?
- Ambas personas deben crerar su llave publica y privada.
- Ambas personas pueden compartir su llave publica a las otras personas.
- La persona que quiere compartir el mensaje puede usar la llave publica de la otra persona para cifrar los archivos y asegurarse que solo puedan ser descifrados con la llave privada de la otra persona.
- El mensaje esta cifrado, asi que puede enviarse a la otra persona sin peligro.
- El receptor puede emplear su llave privada para descifrar el mensaje.
NOTA: La llave privada nunca debe ser compartida.


Como se crean las llaves SSH en Windows/Linux? 
Genera las llaves SSH: 
    $ ssh-keygen -t rsa -b 4096 -C "mi@email.com"
        -t: Algoritmo para la creacion de las llaves.
        -b: Complejidad de bytes del cifrado.
        -C: A que correo se ligara la llave.
Evaluar que el servidor de llaves SSH este corriendo en el equipo:
    $ eval $(ssh-agent -s)
Agregar las llaves SSH a dicho servidor:
    $ ssh-add ruta-donde-guardar-mi-llave-privada


Como se crean las llaves SSH en MacOS? 
$ ssh-keygen -t rsa -b 4096 -C "tu@email.com"
$ eval "$(ssh-agent -s)"
$ ssh-add ruta-donde-guardaste-tu-llave-privada
NOTA: En versiones superiores a MacOS Sierra(v10.12), debes crear o modificar un archivo config en tu carpeta de usuario con el siguiente contenido (Creamos el archivo si no existe):
    Host *
        AddKeysToAgent yes
        UseKeychain yes
        IdentityFile ruta-donde-guardaste-tu-llave-privada
$ ssh-add -K ruta-donde-guardaste-tu-llave-privada
    NOTA: Si da error le quitamos el argumento -K


Cuantas veces se necesita crear las llaves SSH?
Una vez por computadora.


Como agregamos nuestras llaves publicas a GitHub oara comunicarnos de forma segura?
- En GutHub entramos a: 
    Settings > SSH and GPG keys > New SSH key > Rellenar la informacion requerida > Add SSH Key > 
    Configuracion de Llaves SSH > Crear una nueva llave con el nombre que quieras > pega el contenido de la llave publica de tu pc.
- En git: Actualizar la URL del repositorio remoto y reemplazarla por la URL SSH.
    $ git remote set-url origin url-ssh-del-repositorio-GitHub


Que comandos son utiles para copiar la llave publica ssh?
- Linux: cat ~/.ssh/id_rsa.pub
- Windows: $ clip < ~/.ssh/id_rsa.pub
- MacOs: $ pbccopy < ~/.ssh/id-rsa.pub


-------------------------------
| TAGS  Y ALIAS EN GIT/GITHUB |
-------------------------------


Que comandos nos sirven para trabajar con tags(etiquetas)?
- Crear un nuevo tag y asignarlo:
    $ git tag -a nombre-del-tag -m "Mensaje-describiendo-el-tag" id-del-commit
- Listar los tags de nuestro repositorio local: 
    $ git tag     o   $ git show-ref --tags
- Borrar un tag en el repositorio local: 
    $ git tag -d nombre-del-tag
- Publicar un tag en el repositorio remoto:
    $ git push origin --tags
- Borrar un tag del repositorio remoto:
    $ git push origin :refs/tags/nombre-del-tag


Donde son mas utiles los tag?
En gitHub, para que puedan ser vistos por los demas colaboradores.


Que es un alias?
Es un conjunto de sentencias utilizadas para generar un comando complejo con varios comandos de manera optimizada.


Como se agrega un alias solo para git?
- Para un proyecto:
    $ git config alias.nombre-del-alias "log --all --graph --decorate --oneline"
- Global:
    $ git config --global alias.nombre-del-alias "log --all --graph --decorate --oneline"
- Para correrlo:
    $ git nombre-del-alias


-------------------------------------------------------
| MULTIPLES COLABORADORES EN UN REPOSITORIO DE GITHUB |
-------------------------------------------------------


Como se agrega colaboradores en GitHub?
En la pagina de GitHub ingresar a:
    Repositorios > Settings(Del repositorio, no del usuario) > Collaborators > (Agregar el username o correo, si esta configurado como publico) > Add collaborator > (Esperar que el colaborador acepte la invitacion)


Que se necesita para el colaborador pueda ser encontrado por medio de su email en GitHub?
Necesita que su email este configurado como publico en su perfil.


Si como colaborador agregamos el mensaje erroneo del commit como lo podemos cambiar?
- Hacemos un commit con el nuevo mensaje:
    $ git commit -amend
- Corregimos en mensaje.
- Traemos el repositorio remoto:
    $ git pull origin main
Ejecutamos el cambio:
    $ git push --set-upstream origin main


Para ser un colaborador de un proyecto en GitHub debemos ejecutar un comando git init?
- NO, tenemos que irnos al repositirio en el que vamos a colaborar, copiar la url(o SSH) del repositorio y ejecutar el siguiente comando: 
    $ git clone url-del-repositorio
    $ git pull origin main
    $ git push origin main


Como seria un flujo de trabajo profesional, optimo y de buenas practicas  al momento de trabajar en un proyecto conjunto?
- Crear ramas.
- Asignar una rama a cada programador.
- El programador baja el rtepositorio con: $ git pull origin main
- El programador cambia de rama.
- El programador trabaja en esa rama y hace commits.
- El programador sube su trabajo con: $ git push origin nombre-de-la-rama
- El encargado de organizar el proyecto baja, revisa y unifica todos los cambios.


-------------------------------
| TRABAJANDO CON PULL REQUEST |
-------------------------------


Que es un pull request(PR)?
Es un estado intermedio antes de enviar el codigo(por medio de un merge). Por lo general es forkear el proyecto, implementar el cambio en una nueva rama, hacer el pull request y esperar que los administradores del proyecto, luego de revisar el codigo hagan el merge o pidan algun cambio en el codigo o commitsque hiciste.


En un entorno profesional normalmente se bloquea la rama main. Para enviar el codigo a dicha rama po donde debe de pasar normalmente?
Por un CODE REVIEW para su aprobacion se unen los codigos con un MERGE REQUEST.


Para realizar pruevas a donde se envia el codigo de nuestro proyecto?
    A servidores que noprmalmente llamamos STAGING DEVELOP(Servidores de pruebas), despues de esto pasan al servidor de produccion con el MERGE REQUEST.


Que nos permite hacer el pull request?
- Que otros miembros del equipo revisen el codigo y asi aprueben el merge a la rama.
- Permite a las personas que no forman parte del equipo trabajar y colaborar con una rama.


Como se llama la persona que tiene la responsabilidad de aceptar los pull resquest y hacer los merge?
DEvOps


El pull request es una caracteristica de git?
NO, es una caracteristica exclusiva de GitHub. En GitLab se conoce con el nombre de MERGE REQUEST.


Como se realiza un pull request?
- Se trabaja en una rama paralela los cambios que se desean con el comando:
    $ git Checkout -b nombre-de-la-rama
- Se hace un commit a la rama:
    $ git commit -am "Comentario"
- Se suben al remoto los cambios:
    $ git push origin nombre-de-la-rama
- En GitHub se hace el pull request comparando la rama main con la del fix.
- Uno o varios colaboradores revisan que el codigo sea correcto y dan el feedback(En el chat del pull request)
- El colaborador hace los cambios deseados en la rama y lo vuelve a subir al remoto(Automaticamente jala la historia de los cambios que se hagan en la rama, en remoto)
- Se aceptan los cambios en GitHub.
- Se hace merge a main desde GitHub.
NOTA: Cuando se modifica una rama, tambien se modifica el pull request.


------------------------
| TRABAJANDO CON FORKS |
------------------------


Que es un fork?
eEs una bifurcacion de un repositorio completo. Comparte una historia en comun con el proyecto original pero son dos proyectos completamente diferentes, por lo cual el repositorio podra servir como otro origen y ser clonado... etc. Quien crea el fork pasa a ser dueno del repositorio fork.


Por que son importantes los forks?
Porque es la manera en la que funciona el open source, ya que aunque  alguien no sea colaborador de un proyecto puede contribuirt al mismo, haciendo mejor software que pueda ser utilizado por cualquiera.


Como se hace un fork remoto desde consola en GitHub?
- Generamos un remoto adicional desde la consola.
    $ git remote add nombre-del-remoto url-del-remoto
    $ git remote upstream https://github.com/freddier/hyperblog
- Al crear el remoto adicional podemos hacer pull desde el nuevo origen.(En caso de tener permisos podemos hacer fetch y push)
    $ git pull nombre-del-remoto rama
    $ git pull upstream main
- Este pull nos traera los cambios del remoto, por lo que se estara al dia. El flujo de trabajo cambia, en adelante se estara trabajando haciendo pull desde el upstream y push al origin para pasar a hacer pull request.
    $ git pull upstream main
    $ git push origin main


Como se clona un repositorio de GitHub?
$ git clone url-del-repositorio-en-GitHub


----------------------------
| DEPLOYMENT A UN SERVIDOR |
----------------------------


Que es un deploy?
Es el proseso que permite enviar al servidor uno o varios archivos. Este puede ser de prueba, desarrollo o produccion.


Cuales son los pasos para hacer un deployment en un servidor web?
- Entra a la carpeta de los archivos del servidor.
- Copiar link en clone, elegir HTTPS o SSH del repositorio a contribuir.
- En la carpeta deseada se clona el repositorio:
    $ git clone url
    Deploy:
- Realiza cambios y commit en GitHub.
- Traer al repositorio local las actualizaciones para el servidor en la carpeta de los archivos del servidor:
    $ git pull rama-remota main
    NOTA: Siemnpre se debe proteger el archivo .git. Dependiendo del software para servidor web existen diferentes maneras.


La conexion entre GitHub y el servidor se puede realizar mediante:?
- Travis(pago)
- Jenkis(Open Source)


-----------------------------------
| IGNORAR ARCHIVOS CON .GITIGNORE |
-----------------------------------


Que es el archivo .gitignore?
Es un archivo creado en la raiz del repositorio con las reglas de para lops archivos que no se deberian subir al repositorio.


Como se ignoran archivos en un .gitignore?
Creando un archivo llamado .gitignore y en el escribiendo el nombre de los archivos o directorios que no queremos que git envie al repositorio.
NOTA: Podemos usar comodines como *.txt o excepciones a archivos ya ignorados utilizando el simbolo (!)

En que situaciones es deberias evitar que un archivos se vaya a un repositorio, por lo tanto debera ser ignorado?
- Archivos donde estan las contrasenas(.env)o cuando te estas conectando a una base de datos.
- Blob(binary large object) Archivos binarios que son dificiles de gestionar en git.
- Archivos que se generan corriendo comandos, por ejemplo la carpeta node_modules, que genera npm al correr el comando npm install.


----------------------------------------
| SITIOS WEB PUBLICOS CON GITHUB PAGES |
----------------------------------------


Que es GitHub Pages?
    Es un servicio de hosting gratuito perteneciente a GitHub. Con el puedes tener un repositorio alojado en GitHub y hacer que el contenido se muestre en la web en tiempo real.


Cuales son lo pasos para subir un repositorio a GitHub Pages?
    - Debemos tomar la llave SSH y hacer un git clone Ejemplo-ssh en mi computador local.
    - Acceder a la carpeta nueva que aparece en nuestra maquina local.
    - Crear un nuevo archivo que se llame index.html.
    - Guardar los cambios, hacer un git pull y seguido hacer un git push a main.
    - En el apartado del repositorio ir a las opciones de:
        Settings > Source(En la parte de abajo, en la columna pages, ahi seleccionamos la rama que queremos usar de fuente) > Guardar los cambios.


--------------------------------------------------
| GIT REBASE: REORGANIZANDO EL TRABAJO REALIZADO |
--------------------------------------------------


Que es rebase?
Es el proceso de mover o combinar una secuencia de confirmaciones en una nueva confirmacion base. En otras palabras, es sobreescribir una secuencia de commit con otra, para que pareciera como si las secuencias de commits reemplazadas nunca hubieran pasado.


Para hacer un rebase en la rama feature de la rama main que comando ejecutariamos?
$ git checkout feature
$ git rebase main
    Este comando transplanta la rama feature desde su locacion actual hacia la punta de la rama master.
$ git checkout main
git rebase feature  
    - Este comando fusiona la rama feature con la rama main.
    - NOTA: Nunca debes reorganizar las confirmaciones una vez que se hayan enviado a un repositorio publico. La reorganizacion sustituiria las confirmaciones antiguas por las nuevas y pareceria que esa parte del historial de tu rpoyecto se hubiera desvanecido.
    - NOTA: El comando rebase es una mala practica, sobretodo en respositorios remotos. Con rebase puedes recoger todos los cambios confirmados en una rama y ponerlos sobre otra.


---------------------------------------------------------------------
| GIT STASH: GUARDANDO CAMBIOS EN MEMORIA PARA RECUPERARLOS DESPUES |
---------------------------------------------------------------------


Que es un stage?
Es una lista de estados que que nos guarda algunos cambios que hicimos en Staging para poder cambiar de rama sin perder el trabajo que todavia no guardamos en un commit.


En que casos podria ser util hacer un stage?
Cuando necesitamos cambiar de rama y no tenemos cambios que ameriten hacer un commit podermos guardarlos y no perderlos.


Para agregar los cambios al stage se utiliza el comando?
$ git stash
o bien: $ git stage save "Mensaje sobre el elemento del staged"


Por que decimos que el stash se comporta de manera tipo LIFO?
Porque el ultimo dato en entrar es el primero en salir.


Para que sirve el metodo pop?
Para sacar de la lista el ultimo estado del stash y lo insertara en el stagin area.
NOTA: Es importante saber en que rama te encuentras para poder recuperarlo ya que el stash siempre recuperara los cambios que hiciste en el lugar que lo llamas.


Cual es el comando para recuperar los ultimos cambios desde el stage al staging area?
$ git stash pop


Cual es el comando para aplicar los cambios de un stash especifico y eliminarlo del stage?
$ git stash pop stash@{numero-del-stash}


Cual es el comando para retomar los cambios de una posicion especifica del stash?
$ git stash apply stash@{numero-del-stash}


Cual es el comando para ver la lista de cambios guardados en stash?
$ git stash list


Con que comando podemos crear una rama y aplicar el stash mas reciente?
$ git stash branch nombre-de-la-nueva-rama


Que comando podemos usar para crear una rama y aplicar un stash especifico(obtenido desde $ git stash list)?
$ git stash branch nombre-de-la-nueva-rama stahs@{numero-del-stash}


Que comando se utiliza para eliminar los cambios mas recientes dentro del stash?
$ git stash drop


Que comando se utiliza para eliminar un stash a traves de su indice(obtenido con $ git stash list)?
$ git stash drop stash@{numero-del-stash}


Que comando sirve para eliminar todos los elementos del stash?
$ git stash clear.


Que consideraciones se debe tener en cuanta al hacer uso de los stash?
- El cambio mas reciente al crear un stash SIEMPRE recibe el valor 0 y los que estaban antes aumentan su valor.
- Al crear un stash tomara los archivos que han sido midificados y eliminados. Para que tomen un archivo creado es necesario agregarlo al staging area con git add nombre-del-archivo con la intencion de que git tenga un seguimiento de ese archivo, o tambien utilizando el comando $ git stash -u(que guardara los archivos que no esten en el staging)
- Al aplicar un stash este no se elimina, es buena practica eliminarlo.


------------------------------------------------------------
| GIT CLEAN: LIMPIANDO EL PROYECTO DE ARCHIVOS NO DESEADOS |
------------------------------------------------------------


Para que sirve el comando $ git clean?
Para borrar los archivos que no estan en seguimiento ya que no forman parte de nuestro directorio de trabajo.


En la ejecucion del comando $ git clean se puede producio un error. Como podemos hacer para que el comando sea efectivo (forzarlo)?
$ git clean -f
    Es una medida de seguridad, ya que el comando clean no se puede deshacer.
    NOTA: Cuando hay archivos sin seguimiento, con el mismo nombre que otro archivo que si esta en seguimiento dentro de otras carpetas, el comando git clean no las borra, ya que a git no le importan las carpetas, sino los archivos.
    NOTA: El comando $ git clean solo puede borrar archivos que puede indexar, esto significa que si un archivo esta incluido dentro de .gitignore no sera eliminado con el comando.


Cual es el comando para revisar los archivos que no tienen seguimiento?
    $ git clean --dry-run
        Lo que hace el comando es simular cuales archivos serian los que va a borrar. Significa algo asi como "Ejecucion en seco"


-------------------------------------------
| TRAYENDO COMMITS VIEJOS CON CHERRY-PICK |
-------------------------------------------


Que es el comando $ git cherry-pick?
Es un comando que permite tomar uno o varios commits de otra rama sin necesidad de tener que hacer un merge.
NOTA: El uso del comando cherry-pick es considerada una mala practica porque significa que estamos reconstruyendo el historial del proyecto.


Como se usa el comando $ git cherry-pick?
$ git cherry-pick numero-del-commit


-----------------------------
| USO DE GIT RESET Y REFLOG |
-----------------------------


Que es un reflog o registro de referencia?
Es un mecanismo de git a traves del cual se realiza el seguimiento de las actualizaciones en el extremo de las ramas.


---------------------------------
| RECONSTRUIR COMMITS CON AMEND |
---------------------------------


Para que sirve el comando amend?
Puede modificar el commit mas reciente en la misma rama. Es usado para agregar archivos nuevos o actualizar el commit anterior y no generar commits innecesarios. Tambien es una forma sencilla de editar o agregar comentarios al commit anterior ya que abrira la consola para editar este commit anterior.


Cuales son los comando para ejecutar un amend?
$ git add -A
    NOTA: Para hacer uso del amend los archivos deben estar en staging area usando el comando $ git add mi-archivo.
$ git commit --amend
    Remendar el ultimo commit.


Por que se dice que usar el comando amend es mala practica?
Porque si se ha hecho un push o pull al repositorio remoto, en dicho caso va a generar un conflicto que se va a arreglar haciendo un commit adicional, por lo que se perdera el beneficio del amend.

-----------------------------------------------
| BUSCAR EN ARCHIVOS Y COMMITS CON GREP Y LOG |
-----------------------------------------------

Cual es el coamando usado para buscar palabras palabras en los archivos de nuestro proyecto?
$ git grep termino-por-buscar
NOTA: Para buscar etiquetas html(como <p> por ejemplo) se debe escribir la etiqueta dentro de comillas.


Si queremos saber en que lineas esta la palabra color, que comando podemos usar?
$ git grep -n color


Si queremos aber cuantas veces utilizamos una palabra-o-etiqueta en nuestros archivos usamos el comando:?
$ git grep -c palabra-o-etiqueta


Que comando utilizas si lo que quieres es hacer una busqueda en los commits y no en los archivos?
$ git log -S "palabra-que-quieres-buscar"


-----------------------------------------------------
| COMANDOS Y RECURSOS COLABORATIVOS EN GIT Y GITHUB |
-----------------------------------------------------

Que comando muestra cuantos commit han hecho cada miembro del equipo?
$ git shortlog -sn
$ git shortlog -sn --all 
    # Muestra hasta los que se hayan eliminado.
$ git shortlog -sn --all --no-merges 
    # Muestra cuantos commits ha hecho cada miembro, quitando los eliminados sin los merges.


Que comando muestra quien hizo cada cosa linea por linea?
$ git blame nombre-del-archivo
$ git blame nombre-del-archivo -linea-inicial,linea-final
    # Indica desde que linea empezar a ver. Ejemplo: -L35,50
    

Que opcion nos muestra como funciona un comando en particular?
$ git nombre-del-comando --help


Que comando muestra todas las ramas remotas?
$ git branch -r

Que comando muestra todas las ramas, tanto locales como remotas?
$ git branch -a


------------------------------
//////////////////////////////
==============================
| COMANDOS GENERALES DE GIT. |
==============================
//////////////////////////////
------------------------------



$ git init                  
- Empieza un repositorio en tu carpeta de proyecto, dicho repositorio se crea con el nombre de .git, y es una carpeta oculta.

$ git add mi-archivo.txt    
- Agrega mi los archivos que especifiquemos para empezar a darles seguimiento. Los agrega al staging area(Los mantiene en la memoria ram). Siempre que se hace un cambio en el archivo es necesario usar este comando antes de hacer un git commit.

$ git add .
- Con el punto (.) agregas todos los archivos de la carpeta en la que estas.

$ git commit -m "Mensaje acerca de los cambios que hemos realizado."   
- Envia los ultimos cambios del archivo a la base de datos del sistema de control de veriones, o sea, lo toma del staging area y lo guarda en el repositorio (el directorio .git). Puedes agregar un mensaje. (De hecho, no enviar el mensaje se considera una mala practica). Si no seagrega el mensaje e el paramtreo -m entrara a un editor donde tendremos que ingresar el mensaje. Para salir del editos los hacemos con la combinacion ESC + SHIFT + ZZ

$ git commit -am "Mensaje de mi commit"
- Combina el comando add en mi commit. NOTA: Solo funciona para archivos a los cuales ya se les ha hecho add previamente.

$ git status
- Muestra el estado de  la base de datos. (Que archivos han sido modificados y si han sido o no agregados esos cambios a la base de datos)

$ git show mi-archivo.txt 
- Muestra el historial de todos los cambios hechos.

$ git log mi-archivo.txt
Muestra toda la historia de un archivo.

$ git log --stat
Muestra los cambios especificos que se hicieron, en cuales archivo a partir del commit.

$  git push
- Envia nuestro archivo a un servidor remoto

$ git rm --cached mi-archivo.txt
- Remueve el archivo por de la lista, por lo cual deja de darle seguimiento. sera necesario usar el comando git add nuevamente para darle seguimiento. Con el argumento -f(se puede usar tambien --force) se fuerza su eliminacion del disco duro, mientras que con --cached solo se elimina el indice de cambios en memoria.
- No elimina su historial, por lo que sera posible recuperarlo por medio del comando checkout.

$ git diff commit-id-1 commit-id-2
-Nos muestra la direfencia entre uno y otro commit de nuestro archivo.

$ git branch nombre-de-nueva-rama
- Crea una nueva branch de nuestro proyecto. Todas las versiones de nuestro proyecto salen de la rama principal. Producir una nueva rama se conoce con el nombre de checkout. Para borrar una branch podemos usar $ git branch -d.

$ git checkout -b nombre-de-la-rama
- Genera una rama y nos muehe hacia ella.

$ git checkout nombre-de-nueva-rama
- Cambia a la rama especificada de nuestro proyecto y tambien movernos entre diferentes versiones de nuestro proyecto.
- Para volver a la rama principal despues de haber usado el comando $ git checkout main.

$ git checkout commit-id mi-archivo.extension
- Nos movemos a la version del archivo especificada a traves del commit-id. NOTA: Antes de hacer un checkout se debe guardar los cambios que hemos realizado, ya que al movernos perderemos lo que no se haya guardado.

$ git merge nombre-de-la-rama-a-convinar-con-la-actual
Crea un nuevo commit con la combinacion de dos ramas(una es la rama donde nos encontramos y la otra es la que especifiquemos en el comando merge). Un merge siempre trae los cambios hacia la rama en la que estamos en ese momento, por lo cual pasa a ser la principal, asi que es recomendable hacer el merge estando posicionado en la rama principal. Si aparece un conflicto al momento de hacer merge deberemos resolverlo manualmente y luego hacer un commit ya que git solo hace el commit automaticamente luego de un merge si no se producen conflictos.

$ git merge --abort
Aborta la fusion de ramas. 

$ git reset --hard commit-id 
- Vuelve a la version escogida en commit-id. Con este comando no hay posibilidad de regresar a los cambios hechos despues de el punto hacia el cual hicimos reset. Siempre debe aplicarse con un argumento (--soft, --hard, etc.)

$ git reset id-commit
- Nos lleva al commit especificado sin importar la rama eliminando el historial de los commit posteriores al tag seleccionado.

$ git reset HEAD
- Saca los archivos del staging area. No los borra, sino que hace que los archivos no se envien al ultimo commit.

--------------------------------------------
| COMANDOS PARA TRABAJAR EN REMOTO CON GIT |
--------------------------------------------

$ git clone url-del-servidor-remoto
- Nos permite descargar los archivos de la ultima version de la rama principal y todo el historial de cambios en la carpeta git.

$ git push
- Manda los cambios al servidor remoto (Previamente debemos haber hecho add y commit despues para aplicar los cambios en el repositorio local)

$ git fetch
- Trae actualizaciones del servidor remoto y las guarda en nuestro repositorio local.

$ git merge
- Se utiliza para combinar los ultimos cambios del servidor remoto y nuestro directorio de trabajo.

$ git pull
- Es como convinar los comandos fetch y merge.

------------------------
| CONFIGURACION DE GIT |
------------------------

$ git config --list
Muestra un listado de las configuraciones por defecto de git y las cosas que faltan por configurar. Si no se le pasa un argumento y solo usamos el comando $ git config, por defecto intenta usar las variables de entorno del sustema operativo

$ git config --list --show-origin
Muestra donde estan las configuraciones guardadas.

$ git config --global user.name "mi-nombre-de-usuario"

$ git config --global user.email "mi-correo-electronico"

$ git config pull.rebase false  # merge
$ git config pull.rebase true   # rebase
$ git config pull.ff only       # fast-forward only
$ git config --global pull.ff true 



----------------------------------------------------------
| COMANDOS UTILES PARA TRABAJAR EN PROYECTOS MUY GRANDES |
----------------------------------------------------------

$ git log --all
- Muestra todos los
$ git log --oneline
- e muestra el id commit y el título del commit.

$ git log --decorate
- Te muestra donde se encuentra el head point en el log.

$ git log --stat
- Explica el número de líneas que se cambiaron brevemente.

$ git log -p
- Explica el número de líneas que se cambiaron y te muestra que se cambió en el contenido.

$ git shortlog
- Indica que commits ha realizado un usuario, mostrando el usuario y el título de sus commits.

$ git log --graph --oneline --decorate y

$ git log --pretty=format:"%cn hizo un commit %h el dia %cd"
- Muestra mensajes personalizados de los commits.

$ git log -3
- Limitamos el número de commits.

$ git log --after=“2018-1-2”
$ git log --after=“today” y
$ git log --after=“2018-1-2” --before=“today”
- Commits para localizar por fechas.

$ git log --author=“Name Author”
- Commits hechos por autor que cumplan exactamente con el nombre.

$ git log --grep=“INVIE”
- Busca los commits que cumplan tal cual está escrito entre las comillas.

$ git log --grep=“INVIE” –i
- Busca los commits que cumplan sin importar mayúsculas o minúsculas.

$ git log – index.html
- Busca los commits en un archivo en específico.

$ git log -S “Por contenido”
- Buscar los commits con el contenido dentro del archivo.

$ git log > log.txt
- guardar los logs en un archivo txt