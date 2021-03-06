# Guía de instalación de Git y Visual Studio Code en Raspberry Pi

## Git en Raspberry Pi

### 1.Instalar Git.

Lo que aprenderá en esta guía, es a instalar y utilizar el software de control de versiones de Git para trabajar en tus propios proyectos dentro de Raspberry.

Lo que vas a aprender:


*   Instalar Git en Raspberry
*   Crear un Repositorio y subirlo a Github



Vamos a utilizar los conocimientos de [SSH Raspberry](https://github.com/fullmakeralchemist/raspberrysetupes) en esta guía utilizando el Shell de Raspberry desde Putty y vamos a ingresar el siguiente comando.



```
sudo apt install git
```

![installgitMEDIUM](https://user-images.githubusercontent.com/79243784/117558740-73628300-b045-11eb-82ae-bf7c4526751e.png)

![GITINTALED](https://user-images.githubusercontent.com/79243784/117558750-8aa17080-b045-11eb-8085-846e2401320f.png)


### 2.Configurando Git

Lo primero que debemos hacer es ingresar a Git nuestra información. Esto es importante, ya que muchas personas pueden usar Git de forma colaborativa, por lo que es necesario saber quién realizó cambios en qué archivos. Puede usar su propio nombre de usuario y dirección de correo electrónico.
Así que ingresaremos los siguientes comandos:


```
git config --global user.name "usuariogit"
git config --global user.email "emailusuariogit@mail.com"
```
![USERGITMEDIUM](https://user-images.githubusercontent.com/79243784/117558774-b58bc480-b045-11eb-9800-b9f4235b6d05.png)

![emailgitMEDIUM](https://user-images.githubusercontent.com/79243784/117558776-bb81a580-b045-11eb-95cc-79aa8c1464dd.png)

A continuación, debes decirle a Git qué editor de texto desea usar. Si no tienes un editor favorito, simplemente puedes escribir:

```
git config --global core.editor nano
```
![EDITORmedium](https://user-images.githubusercontent.com/79243784/117558783-c76d6780-b045-11eb-943c-9475f75f3aa7.png)

### 3.Creando nuestro primer proyecto
¿Quieres empezar un nuevo proyecto? Tal vez sea un bot como Jarvis que te cuide en todo momento. Necesitará de un directorio en su computadora para todos sus archivos, así que lo primero que debe hacer es crear ese directorio.

En la terminal, puede usar el comando ls (en lista el contenido del directorio actual) para revisar las carpetas y archivos.
En la terminal, puede usar el comando cd (cambio de directorio) para cambiar un nuevo directorio.
En la terminal, puede usar el comando mkdir (crear directorio) para crear un nuevo directorio.


```
ls 
cd Desktop
mkdir snitch-sniffer
cd snitch-sniffer
```
![mrkpruebaMEIDUM](https://user-images.githubusercontent.com/79243784/117558794-e966ea00-b045-11eb-990e-1e088519eb0d.png)

A continuación, puedes crear un archivo que le dirá a las personas de qué se trata el proyecto. Puede utilizar cualquier editor de texto para hacer esto, como el Bloc de notas o mas adelante cuando tengamos el Visual Studio Code puedes hacer un segundo archivo para practicar. Crea un archivo llamado README.md, La extensión .md significa Markdown, que es un lenguaje de marcado. Puede obtener más información sobre Markdown [aquí](https://daringfireball.net/projects/markdown/). Para crear un archivo desde el Shell de Raspberry utilizaremos el comando:

```
nano README.md
```
Ahora podremos ingresar texto en nuestro archivo, para guardar el archivo "Ctrl+O" y finalmente para salir del editor "Ctrl+X".

Una segunda opción es utilizar los conocimientos anteriores de [Wireless Setup](https://github.com/fullmakeralchemist/raspberrysetupes), para ingresar por VNC y crear el archivo. Como en cualquier ordenador usaremos clic derecho, opción nuevo y le damos un nombre y extensión al archivo.

Yo ingrese el siguiente texto en el archivo README.md


```
# The Golden Snitch Sniffer
This is a project that uses multiple long-range ultrasonic sensors to find and track
an object flying in three-dimensional space. It displays the object's coordinates,
speed, and trajectory through a VR headset.
```
![README](https://user-images.githubusercontent.com/79243784/117558806-fdaae700-b045-11eb-8f70-ecf780be6175.png)

![textREADMEMEDIUM](https://user-images.githubusercontent.com/79243784/117558811-00a5d780-b046-11eb-9b84-fc13d1d212ee.png)

Su archivo debería haber sido creado y ahora estará ubicado en su directorio. Puede escribir en la terminal para ver una lista de archivos el siguiente comando.

```
ls
```

Por el momento, el directorio es como cualquier otro de su sistema. Ahora necesitas hacer la parte de el control de versiones. Esto se conoce como repositorio de Git y toma la forma de un directorio oculto que realiza un seguimiento de todos los cambios en el directorio de trabajo. Escriba lo siguiente para crear el repositorio, que de ahora en adelante solo se llamará repositorio:

```
git init
```
![gitinitraspberry](https://user-images.githubusercontent.com/79243784/117558825-10bdb700-b046-11eb-995f-2db9bf133eb9.png)

Si vuelve a escribir ls, no parecerá que haya cambiado nada. Sin embargo, puede usar `ls -a` para ver todos los archivos y directorios ocultos.

Ahora debería ver algo como esto en la ventana de su terminal:

`. .. .git README.md`

Ese directorio .git es el esqueleto del repositorio. Puede echar un vistazo al interior escribiendo lo siguiente.

```
ls -a .git
```

Así que ahora tienes la parte de la mochila mágica, pero aún no le has agregado nada. Ese archivo README.md aún no se ha colocado en la bolsa. Debe decirle a Git que desea agregar el archivo README.md al repositorio. Para hacer esto, simplemente escriba:

```
git add README.md
```
Sin embargo, a veces es más fácil agregar todo al repositorio, en lugar de agregar archivos individuales. Para hacer esto, puede escribir:

```
git add --all
```

Ahora Git sabe que necesita realizar un seguimiento de todos los cambios que suceden en el archivo README.md. Puede ver el estado de su repositorio en cualquier momento escribiendo lo siguiente:

```
git status
```
La respuesta anterior le indica que el archivo README.md aún no se ha confirmado. Esto significa que, aunque Git conoce el archivo, todavía no tiene almacenado ninguno de sus contenidos. La forma más sencilla de realizar una confirmación es escribiendo:

```
git commit -am "add README.md"
```

Esto confirma todos los cambios que ha realizado en el directorio en el repositorio de Git y agrega un mensaje que dice lo que hizo. El mensaje puede ser cualquier cosa en realidad, pero es mejor que sea bastante breve pero descriptivo de lo que ha cambiado.

![GITCOMITT1MEDIUM](https://user-images.githubusercontent.com/79243784/119278205-5b643500-bbe9-11eb-8997-2ab05f2bbe05.png)

### 4.Trabajando con un Github

Ahora que sabe cómo hacer lo básico en Git, es hora de aprender a usarlo en todo su potencial: úselo para compartir su trabajo y colaborar con otros.

Hay muchos servicios que alojarán su repositorio de Git de forma gratuita. GitLab es uno de esos servicios y BitBucket es otro. En este recurso, utilizará GitHub, que es uno de los servicios más populares.

Lo primero que debe hacer es registrarse para obtener una cuenta en [GitHub](https://github.com/join?source=header-home) y simplemente elegir el plan gratuito.

Ahora que tiene una cuenta, puede crear un repositorio de snitch-sniffer en GitHub. Busque el botón Nuevo repositorio y haga clic en él.

![new-repo](https://user-images.githubusercontent.com/79243784/117558864-46fb3680-b046-11eb-9208-31c6c735a6e8.png)

Asigne un nombre y una descripción al repositorio y haga clic en el botón Crear repositorio

![new-repo2](https://user-images.githubusercontent.com/79243784/119278291-ec3b1080-bbe9-11eb-87a6-f0c481f3e5b3.png)

A continuación, debería aparecer una página de instrucciones.

![instructions](https://user-images.githubusercontent.com/79243784/117558872-55495280-b046-11eb-94e3-d318528645e9.png)

Como ya tiene un repositorio listo para enviar a GitHub, entonces todo lo que necesita hacer es asegurarse de estar en el directorio de su proyecto y escribir:

```
git remote add origin git@github.com:HarryPotter/snitch-sniffer.git
```
y luego:

```
git push -u origin master
```
Si busca en GitHub, ahora debería poder ver su repositorio, junto con el archivo README.md que se muestra y que escribió.

![gh-repo](https://user-images.githubusercontent.com/79243784/117558894-80cc3d00-b046-11eb-9ef5-9d7d8952c012.png)

Cada vez que realiza cambios en su proyecto y desea enviarlos a GitHub, puede escribir:

`git push origin master`

Si está trabajando en una rama diferente, escribiría:

`git push origin <branch-name>`

Para saber mas acerca de Git en Raspberry te recomiendo ir a [Getting started with Git](https://projects.raspberrypi.org/en/projects/getting-started-with-git).


## Instalar Visual Studio Code en Raspberry.

### 1.Instalación
Thonny IDE (entorno de desarrollo integrado) incluido con la última versión del sistema operativo Raspberry Pi OS. Thonny viene con Python 3.7 integrado, por lo que no es necesario instalar nada.

Como preferencia personal mi IDE favorito es VS CODE, para algunos proyectos como Apps en Flask, Bots y Tensorflow, me siento mas cómodo trabajando en la interfaz de VS.

La gran noticia es que VS Code ahora está disponible como parte de los paquetes apt de Raspberry Pi OS. Inicie la terminal Raspberry Pi y ejecute los siguientes comandos:
```
sudo apt update
sudo apt full-upgrade
sudo apt install code -y
```
Tardara un poco la instalación, después de terminar, puedes acceder por VNC y revisar que la instalación fue exitosa.

![visualRASPBERRYmedium](https://user-images.githubusercontent.com/79243784/117558901-90e41c80-b046-11eb-9172-92fa7f89775a.png)

Listo con esto, podemos empezar a trabajar con VS CODE y Git, trata de utilizar lo aprendió en esta guía, para crear un segundo repositorio con VS.

También puedes revisar el repositorio de este post en mi Github.
