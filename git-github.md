___
# **INTRODUCCION A GIT Y GITHUB**

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

**Tabla de contenidos**

- [instalacion y configuracion](#instalacion-y-configuracion)
- [Iniciar un proyecto con Git](#iniciar-un-proyecto-con-git)

## **INSTALACION Y CONFIGURACION**

### **Instalacion**
En muchas distribuciones linux Git ya se encuentra instalado por defecto. Para verificarlo podemos simplemente usar el comando `git --version` y si este nos devuelve algo como `git version 2.55.0.ubuntu` entonces significa que el programa esta instalado. En caso de que no lo este podemos instalarlo facilmente con el comando siguiente.

> Nota: Dependiendo la distribucion de linux que estemos usando debe usarse el gestor de paquetes correspondiente. En el siguiente caso se usa apt como ejemplo tomando como referencia una distribucion basada en ubuntu. 

```bash
sudo apt update 
sudo apt install git
```

En windows, la instalacion es como en cualquier otro programa, debes bajar el archivo ejecutable desde el sitio web <https://python.org> en su ultima version.

### **Configuracion**

Una vez instalado, el siguiente paso es configurar git. Para eso debemos agregar nuestro nombre de usuario y correo electronico para confirmar nuestra identidad, asi commo configurar el nombre de la rama principal (se recomienda que se utilice el nombre `main` para esta en luhgar de `master` debido a que puede resultar ofensiva para algunas personas.)

```sh
git config --global init.defaultbranch main
git config --global user.name "Tu_Nombre"
git config --global user.email "Tu_email@email.com"
# Si prefieres usar VS Code en lugar de vim:
git config --global core.editor "code --wait"
```

Puedes verificar estas configuraciones con el comando `git config --list`.

## **INICIAR UN PROYECTO CON GIT**

### **Inicializando el repositorio**

Para iniciar un proyecto con git, dentro del directorio raiz de nuestro proyecto debemos ejecutar el siguiente comando:

```sh
git init
```

Este comando inicializara el repositorio y creara una carpeta oculta llamada `.git`, la cual a partir de ahora comenzara a rastrear todos los cambios realizados en el proyecto.

### **Preparar el archivo (Staged)**

Una vez creados los primeros archivos debemmos añadirlos a la fase de **staged** para que puedan ser agregados en siguiente **commit**, para eso usamos el siguiente comando:

```sh
# Agregando un solo archivo:
git add Nombre_del_archivo

# Podemos agregar todos los archivos con la siguiente linea:
git add .
```

### **Guardando los cambios (Committed)**

Una vez agregados los archivos modificados a la fase de staged podemos proceder a guardar los cambios con el siguiente comando:

```sh
git commit -m "Mensaje describiendo el cambio a guardar."
```

> Podemos combinar los dos pasos anteriores (add y commit) con el comando `git commit -am "Mensaje descriptivo."`. Esto solo funciona si los archivos **ya han sido agregados previamente**, por lo cual los nuevos no seran agregados.

