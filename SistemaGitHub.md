#Sistema de control de versiones GitHub
##Indice

* [Crear Repositorio y clonacion con **git clone**]()
* [Creacion de Archivo .md y configuracion de la cuenta con **git config**]()
* [Preparar archivo para subir y colocar mensaje con **git commit**]()
* [Subir el archivo al repositorio con **git push**]()

* * *

# CREAR REPOSITORIO
Para crear un repositorio dentro de la pagina de GitHub seguimos los siguientes pasos:
* click en el icono o simbolo mas (+)
* Click en **New repository**

![crear proyecto](https://picoolio.net/images/2015/06/01/Pantalla13436e.png)

* Colocar un nombre para el reposistorio
* Seleccionar el check de tipo Public
* Click en el boton **Create Repository**

![Nombre repositorio](https://picoolio.net/images/2015/06/01/Pantalla22988e.png)

* Ubicarnos en la carpeta o directorio donde deseamos clonar el Repositorio
* Copiar la url Generada despues de haber creado el Proyecto

![urlProyect](https://picoolio.net/images/2015/06/01/Pantalla3cc590.png)

* Ubicados ya en la carpeta colocamos el siguiente codigo en la terminal.

```
git clone [Url:http//github.com/nombreusuario/Nombre_Proyecto.git]
```
* Revisamos si realmente clono de manera correcta el proyecto con la siguiente linea de comandos en la terminal.

```
:~$ ls
```
* Ingresa a la carpeta clonada y colocar el siguiente codigo para ver archivos ocultos.

```
:~$ ls -la
```
* * *
# Creacion de Archivo .md y configuracion de la cuenta git config
* Crear un archivo de tipo .md para este ejemplo con el siguiente comando.

```
:~$ nano README.md
```

Editamos el archivo creado con la estructura **Mark Down**.
```
* :(Lista)
# :(Titulo)
##:(subtitulo)
...
```

Una vez editadon nuestro documento de tipo .md guardamos y configuramos nuestra cuenta para subir y hacer un commit de la siguiente forma.
```
:~$ git config --global user.name "nombre_de_usuario".
:~$ git config --global user.email tu_correo@tipo.com
```
La configuracion de la cuenta solo se la debe hacer una sola vez.
* * *
# Preparar archivo para subir y colocar mensaje con 'git commit'
Luego de haber configurado nuestra cuenta preparamos el archivo para subir al repositorio con el comando **"commit"**.
```
:~$ git commit -m "Mensaje_del_archivo"
```
Luego de haber echo el commit vera que en la pagina de nuestra cuenta no existe aun el archivo, esto se debe que con el comando commit solo se prepara el archivo para subir a nuestro repositorio, para subir realmente el archivo deberemos hacer con el comando push.
* * *
# Subir el archivo al repositorio con 'git push'
Luego de haber preparado el archivo con el commit, solo nos queda hacer un push para subir al repositorio.
Para poder hacer push al archivo se hace con la siguiente linea de codigo.
```
:~$ git push origin master
```
Luego de haber echo el push nos pedira datos de nuestra cuenta, el nombre usuario y password de la cuenta.
Una vez colocado nuestros datos de cuenta nos vamos a la pagina de git y actualizamos y veremos que ya ha sido subido nustros archivos.
Para saber el estado actual de nuestro archivo podemos ver con la siguiente linea de codigo.
```
:~$ git status
```
La linea de codigo nos muestra el estado actual que tiene nuestro reporsitorio.
Para subir un nuevo archivo al repositorio deberemos usar el comando:
```
:~$ git add nombre_del_archivo.add (o)
:~$ git add . (sube todos los archivos que hayamos creado).
```


