# Git 🎁

Git sólo trabajará 100% bien con archivos de texto plano, es decir te puede decir en que linea fue que cambio, cosa que no ocurre con archivos binarios.

## Configurar quienes somos 😎🤳

Con el un guión usamos las letras y con el doble guión usamos una palabra en este caso --global. Lo que significa que vamos a cambiar todos los usuarios globales.

- Primero pondremos el nombre de usuario:

        git config --global user.name "Digovil"
        
- Luego en el siguiente comando pondremos nuestro email:

        git config --global user.email "dilangvidal@gmail.com"

Para poder ver la configuración por defecto de git:

    git config --list

Para poder ver donde estan guardadas las configuraciones de git

    git config --list --show-origin 

## Inicializar Git 🐱‍🏍

Para este paso se utiliza el comando git init, lo que hace es crearte una carpeta .git, es un repositorio local donde estaremos guardando todos los cambios del proyecto:

    git init

Esto se tiene que hacer en la carpeta central donde se encuentra el proyecto.


## Agregar un nuevo archivo a la base de datos local de Git

Para esto necesitamos primero avisarle de que el archivo existe:

    git add nombreArchivo.extensionArchivo

Por consiguiente necesitamos avisar de que todos los cambios están listos para ser guardados en la base de datos del sistema de control de versiones, para tener un versionamiento del proyecto:

    git commit -m "mensaje de que le quieres dar"

Para avisarle a git que todos los archivos existen:

    git add .

Eso hará que se carguen todos los archivos que contiene el proyecto. Una vez teniendo identificado todos esos archivos, le avisamos que a git nuevamente que ya esta listo todo para que nos guarde el proyecto en la versión en que se encuentra:

    git commit -m "Listo finalizado"

## Comandos de consulta a la base de datos local de Git

- Estado de la base de datos:

        git status

- Cambios historicos hechos, mostrandote las lineas de código anterior, posterior y quién lo cambió, esto te lo muestra con un diff que lo que hace es comparar:

        git show

- Si quiero ver el historial completo de un archivo, con el nombre de la modificación:

        git log nombreArchivo.extensionArchivo

## Manejo en repositorio remoto

Para enviar a un repositorio remoto el repositorio local:

    git push

## Sacar archivo de Git Add ⛏


Cached significa que esta todavía en memoria RAM, que no están guardados sus cambios en la base de datos local de git:

    git rm --cached nombreArchivo.extensionArchivo


## Comparando commits 😮

Primero tenemos que ver los commits existente del archivo a comparar

    git log .

De esta forma podemos ver que cosa cambio:

    git diff commit1 commit2

## Staging 🧐

Cuando se inicializa git en un proyecto, se crea un área en memoria ram llamada staging y se crea el repositorio /.git/, cuando tu escribes add este archivo pasa a vivir a staging la cual es un lugar totalmente aislado, que esta esperando a que lo mandes al repositorio local /.git/ o a que lo quites con un rm --cached, cuando tu le das un commit, este archivo se manda para el repositorio local, el cual tiene un nombre por default el cual es master.

El staging es la memoria ram, es el estado temporal donde tu agregas archivos que vas cambiando.

Antes del git add, el archivo esta untrackted (sin rastreo) despues del git add, el archivo está en un estado tracked (rastreado), ahí hace parte de staging, es decir que el archivo está trackeado 

## Traer los cambios de un archivo del repositorio local 🐛

Para ello utilizaremos el comando:

    git checkout