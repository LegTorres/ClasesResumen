
---

# **PERSONALIZACION DE ESPACIO DE TRABAJO**

## **Indice**
1. [Lista de aplicaciones](#lista-de-aplicaciones)
2. [Extensiones de VS Code](#extensiones-de-vs-code)
3. [Personalizacion de Vim](#personalizacion-de-vim)
4. [Personalizando la terminal](#personalizando-la-terminal)
5. [Instalacion de NodeJS](#instalacion-de-nodejs)

## **Lista de aplicaciones**
- Tilix
- Vim
- Brave Web Browser
- Google Chrome
- Firefox
- Microsoft Edge
- VS Code
- Sublime Text
- Notepad Plus Plus
- Handbrake
- Audacity
- MusicBraniz Picard
- EasyTag
- Gimp
- Inkscape
- Kdenlive
- Krita
- LibreOffice
- Calibre
- Sigil
- Yt-dlp

## **Extensiones de VS Code**
- Auto Rename Tag
- Color Highlight
- Live Server
- Material Icon Theme
- Prettier - Code Formatter
- C/C++
- C/C++ Compile Run
- Python

## **Personalizacion de Vim**
Agregar las siguientes lineas al archivo **.vimrc**

~~~sh
set number
syntax on
set ts=4
set background=dark
set autoindent        
~~~

## **Personalizando la Terminal**

### **Zsh**

Personalizaremos la terminal con Oh My Zsh y PowerLevel10k para la shell **Zsh**.

1. Instalar y establecer **Zsh** como shell por defecto.
 
~~~sh 
chsh -s $(which zsh)
~~~

2. Instalamos **oh-my-zsh**. Esto nos permitira incrementar las funcionalidades de ZSH. Para ello entramos al sitio [https://ohmyz.sh/](https://ohmyz.sh/ "Sitio de oh-my-zsh") y seguimos las instrucciones para instalar el script.

~~~sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
~~~

3. Luego instalaremos el tema **powerlevel10k** desde el repositorio de GitHub [https://github.com/romkatv/powerlevel10k](https://github.com/romkatv/powerlevel10k "powerlevel10k") y nos dirigimos hacia el apartado de **instalacion**  y ahi escogemos con que utilidad aplicarlo, en nuestro caso sera con **Oh My Zsh**. Ingresamos el comando para clonar el repositorio con Git e instalar el tema.

~~~sh
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
~~~

4. Abrimos el documento de configuracion de .zshrc y comentamos o reemplazamos la linea que hace referencia al tema actual para indicarle que aplique el nuevo tema. El resultado quedaria de la siguiente forma:

~~~sh
#ZSH_THEME="robbyrussell"
ZSH_THEME="powerlevel10k/powerlevel10k"
~~~

> Nota: Para que el resultado sea el mejor es recomendable utilizar las fuentes **MesloLGS NF** previamente a instalar el tema powerlevel10k.

5. Reiniciamos la shell. Para ello solo debemos insgresar el comando `zsh`. Ahora solo es cuestion de escoger las opciones que prefiramos y **listo!!!**.

### **Bash**

1. Instalando PowerLine:

sudo apt install powerline
2. Agregar las siguientes lineas de codigo al archivo .bashrc:

~~~sh
powerline-daemon -q
POWERLINE_BASH_CONTINUATION=1
POWERLINE_BASH_SELECT=1
. /usr/share/powerline/bindings/bash/powerline.sh
~~~

> Nota: Es recomendable agregar las siguientes lineas al archivo .zshrc:
>
> ~~~sh
> powerline-daemon -q
> . /usr/share/powerline/bindings/zsh/powerline.zsh
> ~~~
> 

## **Instalacion de NodeJS**
Instalando **NodeJS** por medio de el manejador de paquetes **NVM**

~~~sh
# Instalando NVM:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

# Instalando NODEJS a traves de NVM
nvm install node

# Para instalar la version LTS de Node
nvm install --lts
~~~

Para crear una aplicacion web con **ReactJS** escribimos los siguientes comandos:

~~~sh
npx create-react-app nombre-de-mi-aplicacion
# Nos desplazamos al directorio de la aplicacion
cd nombre-de-mi-aplicacion
# Iniciamos el servidor
npm start
~~~