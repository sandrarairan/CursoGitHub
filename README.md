# CursoGitHub

# TABLA DE CONTENIDO
- [Instalando Git y GitBash en Windows](#Instalando-Git-y-GitBash-en-Windows)
- [Comandos](#Comandos)
- [Configura tus llaves SSH en local](#Configura-tus-llaves-SSH-en-local)
- 

<!-- toc -->

## Instalando Git y GitBash en Windows

[https://git-scm.com/downloads](https://git-scm.com/downloads)

 - Git from the command line and also from 3d sw
 - Use the OPENSSL Library
 - Check WINdows-style, commit unix-style line endings
 - Use MinTTY (default terminal MSYS2)

**Una vez Git ha sido instalado, los primeros parámetros que se deben configuarar son el correo y el nombre de usuario, usando respectivamente:

git config --global user.email ejemplo@dominio.com
git config --global user.name "Nombre de Usuario"
Por último para habilitar los colores en el Bash de Git se escribe:

git config --global color.ui true
**

## Comandos
```Git Init
<!-- Git Init -->
Git Init
git config --global user.email ejemplo@dominio.com
git config --global user.name "Nombre de Usuario"git init
git config --global color.ui true
rm -rf .git
```
**Git-init (Creando repositorios)**
Para crear nuestro primer repositorio vamos a crear el comando git init y el nombre de nuestro repositorio.
Si utilizamos el comando ls vemos que aún no tenemos nada. Por eso vamos a crear un nuevo archivo que se llame file.txt. Adicionalmente, vamos a crear una carpeta que se llame segundo_repo, y para esto vamos a usar el comando mkdir de la terminal.
Si creamos un repositorio, pareciera que no tuviera información, sin embargo el sistema operativo crea unos archivos ocultos, para borrarlo podríamos buscar dentro de los archivos de nuestra máquina.
Para borrar un repositorio, vamos a usar el comando rm -rf .git y así se haría de forma manual.


## Configura tus llaves SSH en local

Primer paso: Generar tus llaves SSH. Recuerda que es muy buena idea proteger tu llave privada con una contraseña.

ssh-keygen -t rsa -b 4096 -C "tu@email.com"
Segundo paso: Terminar de configurar nuestro sistema.

En Windows y Linux:

# Encender el "servidor" de llaves SSH de tu computadora:
eval $(ssh-agent -s)

# Añadir tu llave SSH a este "servidor":
ssh-add ruta-donde-guardaste-tu-llave-privada
- Comprobar proceso y agregarlo (Windows)
```
eval $(ssh-agent - s)
ssh-add ~/.ssh/id_rsa
**En Mac:**
```
# Encender el "servidor" de llaves SSH de tu computadora:
eval "$(ssh-agent -s)"

# Si usas una versión de OSX superior a Mac Sierra (v10.12)
# debes crear o modificar un archivo "config" en la carpeta
# de tu usuario con el siguiente contenido (ten cuidado con
# las mayúsculas):
Host *
        AddKeysToAgent yes
        UseKeychain yes
        IdentityFile ruta-donde-guardaste-tu-llave-privada

# Añadir tu llave SSH al "servidor" de llaves SSH de tu
# computadora (en caso de error puedes ejecutar este
# mismo comando pero sin el argumento -K):
ssh-add -K ruta-donde-guardaste-tu-llave-privada
