___
# **MANUAL DE GIT Y GITHUB: DE CERO A AVANZADO**

1. [FUNDAMENTOS Y CONCEPTOS BASICOS](#1-fundamentos-y-conceptos-basicos)
    1. [¿Qué es Git?](#11-que-es-git)
    2. [Instalación y Configuración](#12-instalación-y-configuración)
    3. [Las Tres Áreas de Git](#13-las-tres-areas-de-git)
    4. [Primeros Pasos Prácticos](#14-primeros-pasos-practicos)
2. [RAMAS Y FUSION](#2-ramas-y-fusion)
    1. [¿Qué es una Rama (Branch)?](#21-qué-es-una-rama-branch)
    2. [Gestión de Ramas](#22-gestión-de-ramas)
    3. [Fusión de Ramas (Merging)](#23-fusión-de-ramas-merging)
    4. [Resolución de Conflictos](#24-resolución-de-conflictos)
3. [EL SALTO A LA NUBE (GITHUB Y COLABORACION)](#3-el-salto-a-la-nube-github-y-colaboracion)
    1. [Introducción a GitHub](#31-introducción-a-github)
    2. [Conectando Local con Remoto](#32-conectando-local-con-remoto)
    3. [Actualizaciones y Sincronización](#33-actualizaciones-y-sincronización)
    4. [Flujo de Trabajo Colaborativo (GitHub Flow)](#34-flujo-de-trabajo-colaborativo-github-flow)
4. HERRAMIENTAS DEL DIA A DIA Y BUENAS PRACTICAS
    Cosas que salvan vidas en el trabajo diario y que diferencian a un novato de alguien con experiencia.
    1. Ignorar Archivos con .gitignore
    2. Guardar Cambios Temporalmente (git stash)
    3. Deshacer Errores (Con Seguridad)
    4. Semántica de Commits
5. GIT Y GITHUB AVANZADO
    1. Reorganizar el Historial (git rebase)
    2. Técnicas de Rescate y Depuración
    3. Administración de Repositorios en GitHub
    4. Introducción a la Automatización (GitHub Actions)

## **1: FUNDAMENTOS Y CONCEPTOS BASICOS**

### **1.1: Que es Git?**
Git es un sistema de control de versiones (SCV por sus siglas en ingles) distribuido creado por Linus Torvalds. Lleva el control los cambios en el proyecto y tambien permite coordinar el trabajo de varias personas. Este guarda solo los cambios (Cuando se hicieron, o quien los realizo, etc.), lo cual lo hace el trabajo mucho mas eficiente.

Git esta optimizado para guardar cambios de forma incremental.Permite contar con un historial, regresar a una version anterior y agregar funcionalidades.Lleva un registro de los cambios que otras personas realicen en los archivos.

Cuales son las caracteristicas de git?
- Git almacena la informacion como un conjunto de archivos.
- No existen cambios, corrupcion o cualquier alteracion sin que git lo sepa.
- Casi todo en git es local. Es dificil que se necesiten recursos externos.
- Git cuenta con tres estados en los que es posible localizar un archivo:
    - **STAGED**: Has marcado el archivo modificado en su versión actual para que vaya en tu próxima captura (commit). Los archivos en este estado se añaden al área de preparación (Index o Staging Area)
    - **MODIFIED**: El archivo ha sido cambiado en tu directorio de trabajo, pero los cambios aún no están guardados en la base de datos de Git.
    - **COMMITED**: Los datos se han guardado de forma segura y permanente en tu base de datos local de Git.

### **1.2 Instalación y Configuración**

#### **Instalación en Windows, macOS y Linux**
En muchas distribuciones linux Git ya se encuentra instalado por defecto. Para verificarlo podemos simplemente usar el comando `git --version` y si este nos devuelve algo como `git version 2.55.0.ubuntu` entonces significa que el programa esta instalado. En caso de que no lo este podemos instalarlo facilmente con el comando siguiente.

> Nota: Dependiendo la distribucion de linux que estemos usando debe usarse el gestor de paquetes correspondiente. En el siguiente caso se usa apt como ejemplo tomando como referencia una distribucion basada en ubuntu. 

```bash
sudo apt update 
sudo apt install git
```

En windows, la instalacion es como en cualquier otro programa, debes bajar el archivo ejecutable desde el sitio web <https://python.org> en su ultima version.

#### **Configuración de Git**

Una vez instalado, el siguiente paso es configurar git. Para eso debemos agregar nuestro nombre de usuario y correo electronico para confirmar nuestra identidad, asi commo configurar el nombre de la rama principal (se recomienda que se utilice el nombre `main` para esta en luhgar de `master` debido a que puede resultar ofensiva para algunas personas.)

```sh
git config --global init.defaultbranch main
git config --global user.name "Tu_Nombre"
git config --global user.email "Tu_email@email.com"

# Puedes cestablecer el editor por defecto con cualquiera de los siguientes comandos:
git config --global core.editor "code --wait"
git config --global core.editor "subl -w"
git config --global core.editor "nano"Visualizar el historial de cambios en Git es fundamental para rastrear la evolución de tu código. Puedes hacerlo de forma rápida utilizando el comando git log en la terminal, mediante interfaces gráficas, o desde plataformas en línea como GitHub.
git config --global core.editor "vim"
git config --global core.editor "'C:/Program Files (x86)/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"
```

Puedes verificar estas configuraciones con el comando `git config --list`.

### **1.3 Las tres areas de Git**

Git organiza su flujo de trabajo en tres áreas principales: 

1. **Directorio de Trabajo (Working Directory):** Es la carpeta de tu computadora donde puedes ver, abrir y editar los archivos del proyecto. Su función es servir como tu espacio de desarrollo activo. Cuando modificas un código, creas un archivo nuevo o borras algo, lo estás haciendo en esta área. Git aún no registra estos cambios oficialmente; solo detecta qué archivos han sido alterados respecto a la última versión guardada.

2. **Área de Preparación (Staging Area o Index):** También conocida como índice, es un archivo intermedio (invisible en tu explorador de archivos) que almacena qué cambios específicos quieres incluir en tu siguiente guardado. Permite agrupar lógicamente las modificaciones. Por ejemplo, si modificaste tres archivos pero solo quieres guardar el progreso de dos de ellos, puedes enviar al staging únicamente esos dos. Se utiliza `git add <archivo>` para mover los cambios del área de trabajo al área de preparación.

3. **Directorio Git (Git Directory / Repositorio):** Es el núcleo de Git. Aquí es donde Git almacena de forma permanente el historial, las versiones y los metadatos de tu proyecto. Almacena el código en forma de capturas de pantalla o instantáneas (snapshots) cada vez que haces un commit. Es el equivalente a guardar una "partida" en un videojuego.Se utiliza `git commit -m "Mensaje"` para empaquetar los archivos que estaban en el área de preparación y guardarlos como una nueva versión en el repositorio.

### **1.4 Primeros pasos practicos**

#### **Crear un repositorio Git (git init)**

Para iniciar un proyecto con git, dentro del directorio raiz de nuestro proyecto debemos ejecutar el siguiente comando:

```sh
git init
```

Este comando inicializara el repositorio y creara una carpeta oculta llamada `.git`, la cual a partir de ahora comenzara a rastrear todos los cambios realizados en el proyecto.

#### **Ver el estado del proyecto (git status)**
filtrar el historial y mostrar únicamente los commits cuyo mensaje contenga el texto que buscas. A diferencia de git log -S (que busca dentro del código fuente), este comando se enfoca estrictamente en los títulos y descripciones de las confirmaciones
Puedes ver el estado de tu proyecto, en qué rama estás trabajando, qué archivos han sido modificados, cuáles están listos para confirmarse (stage) o si hay archivos nuevos sin seguimiento.

```sh
git status

# Visualización más rápida y compacta:
git status --short # O git status -s
```

> Nota: Esto te mostrará una lista de una línea por cada archivo modificado, donde los archivos sin seguimiento aparecen marcados con `**??**`, los modificados con `**M**` y los listos para guardar con `**A**`.

#### **Preparar archivos (git add)**

Una vez creados los primeros archivos debemmos añadirlos a la fase de **staged** para que puedan ser agregados en siguiente **commit**, para eso usamos el siguiente comando:

```sh
# Agregando un solo archivo:
git add Nombre_del_archivo

# Podemos agregar todos los archivos con la siguiente linea:
git add .
```

#### **Guardando los cambios (Committed)**

Una vez agregados los archivos modificados a la fase de staged podemos proceder a guardar los cambios con el siguiente comando:

```sh
git commit -m "Mensaje describiendo el cambio a guardar."
```
filtrar el historial y mostrar únicamente los commits cuyo mensaje contenga el texto que buscas. A diferencia de git log -S (que busca dentro del código fuente), este comando se enfoca estrictamente en los títulos y descripciones de las confirmaciones
> Podemos combinar los dos pasos anteriores (add y commit) con el comando `git commit -am "Mensaje descriptivo."`. Esto solo funciona si los archivos **ya han sido agregados previamente**, por lo cual los nuevos no seran agregados.

#### **Historial de cambios (git log, git shortlog y git diff)**

Visualizar el historial de cambios en Git es fundamental para rastrear la evolución de tu código. Puedes hacerlo de forma rápida utilizando el comando `git log` en la terminal. Por defecto, muestra una lista cronológica inversa (los más recientes primero) con el autor, la fecha y el mensaje del commit. 

**git log** acepta varios parametros que permiten modificar la salida del comando. Los ejemplos mas comunes son:

```sh
# Comando por defecto:
git log

# Muestra todo el historial de un solo archivo:
git log mi-archivo.txt

# Muestra las líneas exactas que se cambiaron:
git log -p 

# Buscar en que commits se modifico una cadena de texto especifica:
git log -S "cadena-de-texto"

# Muestra que cambios archivos cambiaron y cuántas líneas se modificaron:
git log --stat

# Mostrar un resumen en una sola linea (el id y el título del commit):
git log --oneline

# Muestra el historial de commits de todas las ramas y referencias del repositorio:
git log --all

# Limita el numero de commits a mostrar dependiendo del numero indicado:
git log -3

# Mostrar un grafico representando la estructura de ramas y fusiones:filtrar el historial y mostrar únicamente los commits cuyo mensaje contenga el texto que buscas. A diferencia de git log -S (que busca dentro del código fuente), este comando se enfoca estrictamente en los títulos y descripciones de las confirmaciones
# Suele usarse combinado con --oneline para compactar cada commit en una sola linea.
git log --graph --oneline

# Rastrear la evolución de un archivo:
# Evita conflictos si una rama se llama igual que el archivo
git log -- archivo.ext

# Mostrar a qué ramas, etiquetas (tags) o referencias apunta cada commit directamente en la lista del historial:
# Viene activada por defecto en las veriones modernas de Git.filtrar el historial y mostrar únicamente los commits cuyo mensaje contenga el texto que buscas. A diferencia de git log -S (que busca dentro del código fuente), este comando se enfoca estrictamente en los títulos y descripciones de las confirmaciones
git log --decorate

# Filtrar el historial y mostrar únicamente los commits cuyo mensaje contenga el texto que buscas. A diferencia de git log -S (que busca dentro del código fuente), este comando se enfoca estrictamente en los títulos y descripciones de las confirmaciones. 
git log --grep="TEXTO"
git log --grep="TEXTO" -i # No distingue entre mayusculas y minusculas.
git log grep="texto1" grep="texto2" --all-match #  Busca commits que mencionen dos palabras a la vez.
```

existen otros parametros utiles para el comando `git log`. 

```sh
# Muestra mensajes personalizados de los commits.
git log --pretty=format:"%cn hizo un commit %h el dia %cd"
git merge --abort

# Filtra commits por fechas.
git log --after=“2018-1-2”
git log --after=“today” y
git log --after=“2018-1-2” --before=“today”

# Commits hechos por autor que cumplan exactamente con el nombre.
git log --author=“Name Author”
```

> Nota: Podemos mandar el resultado de un git log a un archivo de texto con el comando `git log > log.txt`.

El comando git shortlog sirve para agrupar y resumir el historial de commits por autor. En lugar de mostrar una lista cronológica detallada, limpia la salida de la terminal para ofrecer una estructura de tipo "lista de tareas", ideal para crear registros de cambios (changelogs) o auditorías de código.

Este comando se vuelve mucho más útil cuando modificas su comportamiento con estos parámetros:
-**-s** (o --summary): Muestra únicamente el recuento total de commits por autor, ocultando por completo los títulos de los mensajes. Es perfecto para ver quién ha aportado más volumen de cambios.
- **-n** (o --numbered): Ordena la lista de autores de mayor a menor según su número de aportaciones, en lugar del orden alfabético.
- **-e** (o --email): Añade la dirección de correo electrónico al lado del nombre de cada autor.

```sh
# Organizar el historial en orden alfabético según el nombre de los desarrolladores:
git shortlog

# Obtener un ranking rápido de los desarrolladores más activos en tu proyecto actual:
git shortlog -sn
```

La herramienta principal para comparar diferentes estados de tu código es el comando `git diff`. Su función es mostrarte exactamente qué líneas de texto se agregaron, modificaron o eliminaron entre tu espacio de trabajo actual, tu área de preparación (staging) y tus commits.

```sh
# Por defecto muestra las modificaciones sin preparar(las que aun no se han agregado al staging area) 
git diff

# Muestra los cambio ya agregados al staging area y que estan listos para para incluirse en el proximo commit
git diff --staged

# Muestra las diferencias del trabajo actual contra el ultimo commit de tu rama actual (HEAD) o dos commit.
git diff rama_1 rama_2
git diff id_commit_1 id_commit_2
```

Si tu proyecto es grande y git diff te muestra demasiada información, puedes limitar la salida a un archivo o carpeta en particular añadiendo la ruta al final del comando, con 

```sh
git diff nombre_del_archivo.txt

git diff --staged ruta/al/directorio/
```

## **2: RAMAS Y FUSION**git merge --abort


### **2.1: ¿Qué es una Rama (Branch)?**

Una rama en Git es una versión paralela de tu código fuente que te permite desviar el desarrollo de la línea principal para trabajar de forma independiente sin afectar el proyecto original. Técnicamente, una rama no es una copia física de todos tus archivos, sino un puntero móvil que apunta a una confirmación específica (commit) dentro del historial.

Las ramas mas populares en el desarrollo de proyectos de software son:
- **Rama main:** Es la rama por defecto de nuestro proyecto.
- **Rama development:** Suelen ser ramas para hacer experimentos con nuestro codigo sin necesidad de afectar nuestro codigo principal.
- **Rama hotfix:** Tambien se les suele llamar **bug fixing** y se crean al detectar algun error critico en nuestro proyecto principal para hacer los arreglos necesarios. Cuando esta corregido se fusiona con la rama principal; a esta union de diferentes ramas de un proyercto se le llama **merge**.

#### **La teoría detrás del puntero HEAD y las bifurcaciones.**

El puntero HEAD y las bifurcaciones (ramas) son los mecanismos fundamentales que permiten a Git gestionar el historial de tu código de forma ultraeficiente. A diferencia de otros sistemas de control de versiones que copian carpetas enteras, Git gestiona todo mediante punteros a confirmaciones (commits).

El **HEAD** es una referencia interna (un puntero especial) que le indica a Git en qué lugar del historial te encuentras posicionado en este preciso momento. Es la "cámara" o el visor que determina qué archivos se muestran en tu directorio de trabajo.Su comportamiento habitualNormalmente, HEAD no apunta directamente a un commit, sino que apunta de forma indirecta a la rama activa en la que estás trabajando. La rama, a su vez, apunta al commit más reciente de esa línea de desarrollo.

```txt
[Commit A] <-- [Commit B] <-- [Commit C]
                                   ^
                                   |
                             [ branch: main ]
                                   ^
                                   |
                                [ HEAD ]
```

Cuando ejecutas un nuevo git commit, ocurren tres cosas en milisegundos:

1. Se crea el nuevo nodo de commit.
2. El puntero de la rama se mueve automáticamente hacia adelante para apuntar al nuevo commit.
3. El HEAD sigue a la rama, manteniéndose en la punta.

El estado de **HEAD desprendido (Detached HEAD)** ocurre cuando utilizas el comando `git checkout <hash-de-commit>` para viajar al pasado, apuntando directamente a un commit específico en lugar de a una rama.

```txt
[Commit A] <-- [Commit B] <-- [Commit C]
                   ^               ^

                   |               |
                [ HEAD ]     [ branch: main ]
```

> Nota: Si realizas nuevos commits estando en este estado, estos no pertenecerán a ninguna rama, y, como consecuencia, si te cambias a otra rama sin guardar esos commits en una nueva bifurcación, Git perderá el rastro de ellos y eventualmente serán borrados por el recolector de basura (Garbage Collector).

> Una bifurcación en Git no duplica archivos físicos, sino que separa la línea de tiempo del proyecto mediante una estructura de red donde cada commit conoce a su padre. Las ramas se crean instantáneamente como etiquetas de 41 bytes, y Git identifica automáticamente el ancestro común más cercano para gestionar la evolución independiente de la topología.

### **2.2: Gestión de Ramas**
La gestión de ramas es el proceso de crear, cambiar, fusionar y eliminar líneas de desarrollo en tu proyecto. Para dominarlo, solo necesitas entender los comandos esenciales de la terminal y aplicar una estrategia de flujo de trabajo adecuada. Las operaciones diarias de ramas se realizan con tres comandos principales:

#### **Crear, listar y borrar ramas (git branch).**
```sh
# Lista todas las ramas locales de tu proyecto
git branch

# Crear una rama nueva (pero no te cambia a ella)
git branch <nombre>: 

# Elimina una rama de forma segura (solo si ya fusionaste sus cambios)
git branch -d <nombre>
```

#### **Saltar entre ramas (git checkout vs. el moderno git switch/restore).**

Los comandos `git switch` y `git restore` fueron introducidos en la versión 2.23 de Git para solucionar un gran problema: el comando `git checkout` hacía demasiadas cosas diferentes y confundía a los usuarios.La diferencia principal es que `git checkout` es una herramienta multiusos, mientras que `git switch` se diseñó exclusivamente para cambiar y crear ramas.

El motivo del cambio radica en la separación de responsabilidades. En el Git clásico, `git checkout` se utilizaba tanto para el manejo de ramas como para la manipulación de archivos individuales, lo que provocaba errores accidentales. El problema de checkout radica en que si escribías `git checkout main`, cambiabas a la rama **main**. Pero si escribías `git checkout main.js`, Git no cambiaba de rama; en su lugar, borraba todos los cambios locales de ese archivo y lo revertía a su último estado guardado. Un simple error de dedo podía destruir tu trabajo. La solución moderna: Git dividió las funciones de checkout en dos comandos especializados mucho más seguros: 

- `git switch`: Se encarga únicamente de moverte entre ramas. Si intentas pasarle el nombre de un archivo, te dará un error en lugar de borrar tu código.
- `git restore`: Se encarga únicamente de descartar cambios locales o recuperar archivos.

```sh
# Cambiar a una rama existente
git checkout nombre-rama
git awitch nombre-rama

# Crear una rama y cambiar a ella
git checkout -b nueva-rama
git switch -c nueva-rama

# Regresar a la rama anterior
git checkout -
git switch -

# Deshacer los cambios locales en el directorio de trabajo
git checkout -- archivo.ext
git restore archivo.ext

# Sacar un archivo del staging area (Deshacer un git add)
git restore --staged archivi.ext
git reset HEAD archivo.ext
```

Por defecto, git restore regresa los archivos a su último commit (técnicamente, al estado guardado en el Staging Area o en el commit apuntado por HEAD).Sin embargo, el comando es muy flexible y te permite llevar los archivos a cualquier otro punto del historial utilizando el parámetro `--source`. Git busca la versión del archivo en el Staging Area (si ya habías hecho un git add previo de ese archivo) o en el último commit (HEAD) y sobrescribe tu archivo actual con esa información

Si necesitas recuperar cómo se veía un archivo en un commit específico de hace tres días, o cómo estaba en otra rama completamente diferente, puedes indicarle a Git el "origen" exacto con `--source`.

```sh
# Regresar desde un commit específico del pasado:
git restore --source hash-identificador archivo.ext

# Traer la versión tal y como está en tu rama de producción (main), pero sin cambiarte de rama:
git restore --source main index.html

# Ver cómo estaba el archivo justo antes del último commit que hiciste (HEAD~1 significa "el padre de HEAD"):
git restore --source HEAD~1 index.html
```

### **2.3: Fusión de Ramas (Merging)**

La fusión de ramas (git merge) es la operación que te permite unir dos líneas de tiempo diferentes en una sola. Es el paso final cuando terminas de desarrollar una nueva característica en tu rama secundaria y deseas integrarla al tronco principal (habitualmente la rama main).

Para fusionar, la regla de oro es posicionarte primero en la rama que va a recibir los cambios y luego llamar a la rama que deseas absorber:

```sh
git switch main
git merge nombre-rama-secundaria

```

Dependiendo de cómo haya evolucionado el historial, Git aplicará de forma automática una de estas dos estrategias:

#### **Fusión rápida (Fast-Forward).**

Ocurre cuando la rama principal (main) no ha recibido ningún commit nuevo desde que creaste la rama secundaria. El historial es una línea recta perfecta.
```txt
[Commit A] <-- [Commit B] (main)
                       \
                        [Commit C] <-- [Commit D] (feature)
```

¿Qué hace Git? No crea ningún commit especial. Simplemente desplaza el puntero de la rama main hacia adelante hasta alcanzar a feature. Es una fusión instantánea y limpia.

```txt
[Commit A] <-- [Commit B] <-- [Commit C] <-- [Commit D] (feature)(main)
```

#### **Fusión de tres vías (3-way merge o Merge commit).**

Ocurre cuando la rama principal (main) sí recibió commits de otras personas mientras tú trabajabas en tu rama secundaria. El historial se ha dividido en dos caminos independientes.                        
```txt
                        [Commit C] <-- [Commit D] (feature)
                       /
[Commit A] <-- [Commit B]
                       \
                        [Commit E] <-- [Commit F] (main)
```

¿Qué hace Git? Busca el ancestro común (Commit B), compara los cambios de ambas ramas y crea automáticamente un nuevo commit especial llamado **Commit de Fusión (Merge Commit)**. Este nuevo commit tiene la particularidad de tener dos padres y une ambas historias.

```txt
                        [Commit C] <-- [Commit D] 
                       /                         \
[Commit A] <-- [Commit B]                         [Commit G] (Merge Commit en main)
                       \                         /
                        [Commit E] <-- [Commit F] 
```

### **2.4: Resolución de Conflictos**

#### **¿Por qué ocurren los conflictos?**

Un conflictos ocurre cuando Git detiene una fusión (git merge) porque dos ramas modificaron la misma línea del mismo archivo, o porque una rama borró un archivo que la otra modificó. Git no sabe cuál versión conservar y te pide a ti, el programador, que tomes la decisión final.

Si tú modificaste una linea de un archivo en tu rama, y otra persona modificó la misma línea en la rama main, Git no sabrá cuál versión conservar y detendrá la fusión lanzando un **Conflicto de Fusión (Merge Conflict)**. En ese momento, Git detiene el proceso, altera temporalmente tus archivos y te pide a ti que decidas con qué código quedarte antes de completar el commit.

#### **Cómo leer las marcas de conflicto (<<<<<<<, =======, >>>>>>>).**

Si abres el archivo en conflicto dentro de tu editor de código (como VS Code), notarás que Git ha inyectado unas marcas visuales especiales para delimitar el problema:

```html
<<<<<<< HEAD
<h1>Título en la rama principal</h1>
=======
<h1>Título de la nueva función</h1>
>>>>>>> feature-rama
```
Anatomía de las marcas de conflicto:

- <<<<<<< HEAD: Indica el inicio de los cambios que están en la rama donde estás parado actualmente (la receptora).
- =======: Es la línea divisoria que separa ambas propuestas.
- >>>>>>> feature-rama: Indica el final de los cambios que provienen de la rama que estás intentando absorber.

#### **Buenas prácticas para resolverlos sin entrar en pánico.**

Resolver un conflicto consiste simplemente en limpiar el archivo para que quede exactamente como deseas y luego avisarle a Git. El proceso consta de tres pasos:
1. **Editar el archivo:** Elige con qué código te quedas. Puedes dejar la versión de HEAD, la versión de la rama secundaria, o borrar ambas y escribir una solución completamente nueva.
2. **Borrar las marcas:** Asegúrate de eliminar manualmente las líneas con `<<<<<<<`, `=======` y `>>>>>>>`. El archivo debe quedar impecable y funcional.
3. **Confirmar la solución:** Una vez que guardes el archivo limpio en tu editor, ejecuta en tu terminal:

```sh
git add archivo.ext
git commit -m "Fix: resolver conflicto de fusión en el título"
```

> Nota: Al hacer el git commit, Git completará la fusión y creará el commit de merge de forma exitosa.

Si el conflicto es demasiado grande, te confundes y prefieres congelar todo para analizarlo mejor o pedir ayuda, puedes **cancelar la fusión por completo** y regresar tu proyecto al estado exacto en el que estaba antes de iniciar el merge con este comando:

```sh
git merge --abort
```

## **3: EL SALTO A LA NUBE (GITHUB Y COLABORACION)**

### **3.1: Introducción a GitHub**

GitHub es una plataforma de desarrollo colaborativo basada en la nube que permite a los programadores alojar, gestionar, compartir y realizar un seguimiento de sus proyectos de software. Es propiedad de Microsoft y funciona esencialmente como una red social para desarrolladores e ingenieros de software.

Características principales de GitHub:
- **Control de versiones:** Permite revertir errores regresando a versiones anteriores del código sin perder el progreso actual.
- **Trabajo en equipo:** Los desarrolladores pueden trabajar simultáneamente en el mismo proyecto mediante "ramas" (branches). Esto evita que los cambios de una persona sobrescriban o rompan el trabajo de otra.
- **Herramientas de colaboración:** Ofrece funciones como las Pull Requests (solicitudes para revisar e integrar código nuevo) e Issues (reportes para reportar fallos o sugerir mejoras).
- **Comunidad de código abierto:** Alberga millones de proyectos públicos donde desarrolladores de todo el mundo comparten sus códigos de forma gratuita para que otros aprendan o ayuden a mejorarlos.
- **Automatización e IA:** Incorpora herramientas modernas como GitHub Actions para automatizar pruebas y despliegues de software, así como asistentes de inteligencia artificial como GitHub Copilot para ayudar a escribir código más rápido.

#### **Creación de cuenta y configuración de seguridad (claves SSH y tokens de acceso)**

Para configurar tu entorno de GitHub de forma segura, el proceso se divide en tres pasos esenciales: la creación de la cuenta, la vinculación de tu computadora mediante una clave SSH (para subir código de forma segura) y la generación de un token de acceso (para autenticar aplicaciones o herramientas externas).

Para crear una cuenta en github debemos seguir los siguientes pasos:

1. Ingresa al sitio oficial en github.com.
2. Haz clic en el botón Sign up ubicado en la esquina superior derecha.
3. Introduce tu correo electrónico, define una contraseña segura y elige un nombre de usuario (este nombre formará parte de la URL de tus proyectos).
4. Resuelve el acertijo visual de verificación para demostrar que no eres un robot.
5. GitHub te enviará un código de verificación de 8 dígitos a tu correo. Ingrésalo en la web para activar la cuenta.

Una vez creada la cuenta, procedemos a configurar una clave ssh don el siguiente codigo:

```sh
ssh-keygen -t ed25519 -C "tu_correo@ejemplo.com" -f "$HOME/.ssh/id_ed25519" -N ""

eval "$(ssh-agent -s)"

ssh-add "$HOME/.ssh/id_ed25519"

```
> Presiona Enter en todas las solicitudes que aparezcan para guardarla en la ruta por defecto y dejar la contraseña en blanco (o añade una frase de seguridad si deseas máxima protección).

Copiar la clave publica generada"

- **Windows (Git Bash):** cat ~/.ssh/id_ed25519.pub | clip
- **Mac:** pbcopy < ~/.ssh/id_ed25519.pub
- **Linux:** cat ~/.ssh/id_ed25519.pub 

> (En Linux, selecciona el texto que se muestra en pantalla y cópialo manualmente)

Para vincular la clave a nuestra cuenta de github seguimos los siguientes pasos:

1. Ve a GitHub, haz clic en tu foto de perfil (esquina superior derecha) y selecciona Settings.
2. En el menú lateral izquierdo, haz clic en SSH and GPG keys.
3. Haz clic en el botón verde New SSH key.
4. En Title, escribe un nombre que identifique a tu computadora (ej. Mi Laptop Personal).
5. En Key, pega el código que copiaste en el Paso B.
6. Haz clic en Add SSH key.

Por ultimo configuramos lops **Tokens de Acceso Persona (PAT)**. Los tokens funcionan como contraseñas temporales con permisos limitados. Son obligatorios si usas herramientas externas (como Visual Studio Code, herramientas de línea de comandos o aplicaciones de terceros) para interactuar con tus repositorios.

GitHub ofrece dos tipos de tokens. Se recomienda usar los **Fine-grained tokens** porque permiten restringir el acceso a repositorios específicos en lugar de dar acceso a toda tu cuenta.
1. En la página de Settings de GitHub, baja en el menú izquierdo hasta el final y haz clic en **Developer settings**.
2. Selecciona **Personal access tokens** y luego haz clic en **Fine-grained tokens**.
3. Haz clic en **Generate new token**.
4. Configura los datos principales:
    1. T*oken name:* Un nombre descriptivo (ej. Acceso desde VS Code).
    2. **Expiration:** El tiempo de vida del token (se recomiendan **30 o 60 días** por seguridad).
    3. **Repository access:** Selecciona si tendrá acceso a todos tus proyectos (All repositories) o solo a algunos seleccionados (Only select repositories).
5. En **Permissions**, define qué puede hacer el token. Para un uso estándar de desarrollo, despliega **Repository permissions** y marca como **Read and Write** las opciones de **Contents** (para leer y subir código) y **Metadata** (obligatoria por defecto).
6. Haz clic en **Generate token** al final de la página.

> **Importante:** Copia el token que aparece en pantalla inmediatamente y guárdalo en un lugar seguro (como un gestor de contraseñas). No podrás volver a verlo una vez que cierres la página.

### **3.2: Conectando Local con Remoto**
#### **Crear un repositorio en GitHub.**
#### **Vincular repositorios (git remote add origin).**
#### **Subir cambios (git push -u origin main).**
### **3.3: Actualizaciones y Sincronización**
#### **Traer cambios del servidor (git fetch vs. git pull).**
### **3.4: Flujo de Trabajo Colaborativo (GitHub Flow)**
#### **Hacer un Fork de un repositorio.**
#### **Crear un Pull Request (PR).**
#### **Revisión de código, comentarios y aprobación de PRs.**


## **4: HERRAMIENTAS DEL DIA A DIA Y BUENAS PRACTICAS**
### **4.1: Ignorar Archivos con .gitignore**
#### **Sintaxis y qué archivos nunca deben subirse (credenciales, carpetas como node_modules, configuraciones del - sistema operativo).**
### **4.2: Guardar Cambios Temporalmente (git stash)**
#### **¿Qué hacer si tienes que cambiar de rama pero tus cambios actuales no están listos para un commit?**
### **4.3: Deshacer Errores (Con Seguridad)**
#### **Descartar cambios en el directorio de trabajo (git restore).**
#### **Sacar archivos del Staging Area (git restore --staged).**
#### **Modificar el último commit (git commit --amend).**
#### **Viajar al pasado en el historial (git reset vs. git revert).**
### **4.4: Semántica de Commits**
#### **Cómo escribir mensajes claros y profesionales (introducción a Conventional Commits).**


## **5: GIT Y GITHUB AVANZADO**
### **5.1: Reorganizar el Historial (git rebase)**
#### **Diferencias filosóficas entre merge y rebase.**
#### **Interactive Rebase (git rebase -i): aplastar (squash), renombrar y reordenar commits.**
### **5.2: Técnicas de Rescate y Depuración**
#### **Traer commits específicos de otras ramas (git cherry-pick).**
#### **Encontrar en qué commit se rompió algo (git bisect).**
#### **¿Quién escribió esta línea de código? (git blame).**
#### **Recuperar commits aparentemente perdidos (git reflog).**
### **5.3: Administración de Repositorios en GitHub**
#### **Reglas de protección de ramas (Branch Protection Rules).**
#### **Uso de Issues, Projects y etiquetas para gestionar el desarrollo.**
### **5.4: Introducción a la Automatización (GitHub Actions)**
#### **Qué es CI/CD (Integración y Despliegue Continuos).**
#### **Crear un flujo de trabajo básico (por ejemplo, correr tests automáticamente al hacer un push).**