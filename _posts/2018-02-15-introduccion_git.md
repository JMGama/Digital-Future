---
layout: post
cover: assets/post/2018-02-15-how-to-git/git-logo.jpg
title: Iniciando con Git
date: 2018-02-11T04:00:00.000Z
tags: Curso Introduccion Git
author: Jose Manuel Gama
---

Este curso trata sobre como iniciarnos en el uso de Git. Explicaremos conceptos sobre **control de versiones**, veremos como **instalar Git** en nuestro sistema, como **configurarlo** para iniciar a trabajar en el y los **comandos** para utilizar Git.

# ¿Qué es Git?

Git, es un software **controlador de versiones distribuido** _(open source)_ que fue diseñado por Linus Torvalds, así es... el desarrollador de Linux. Pero aquí la pregunta mas importantes es, ¿Que es un controlador de versiones? :thinking:

<amp-img src="https://images.g2crowd.com/uploads/product/image/social_landscape/social_landscape_1489700483/git.png" width="656" height="400" layout="responsive" alt="" class="mb3">
</amp-img>

Un controlador de versiones es un sistema que se encarga de **registrar los cambios realizados** sobre algún proyecto a lo largo del tiempo, de forma que puedes **recuperar** versiones especificas mas adelante. ~~(¡podemos volver al pasado!)~~ :scream:

Este tipo de controladores de versiones los percibimos en muchos lugares, un ejemplo es cuando estamos trabajando en Word y borramos algo sin querer o queremos deshacer algún cambio, podemos utilizar **Ctrl + z** para volver a un estado anterior y recuperar lo que habíamos perdido.

Existen tres tipos de controlador de versiones:

- Controlador de versiones locales.
- Controlador de versiones centralizado.
- Controlador de versiones distribuido.

## Controlador de versiones local

Es un método de control de versiones en donde únicamente se **copian los archivos del proyecto** a otro directorio _(quizás indicando la fecha y hora en que lo hicieron, si son ingeniosos)._ Este es uno de los métodos mas comunes ya que es el mas sencillo, pero a su vez es muy propenso a errores. Es muy fácil que se nos olvide en que directorio estamos, y que guardemos accidentalmente en el archivo equivocado o sobrescribir archivos que no queríamos.

<amp-img src="{{ site.baseurl }}assets/post/2018-02-15-how-to-git/vcs.png" width="656" height="400" layout="responsive" alt="" class="mb3">
</amp-img>

## Controlador de versiones centralizado

Los CVCS _(por sus siglas en ingles)_ surgen con la necesidad de **trabajar con otros colaboradores**. Los CVCS fueron desarrollados para solucionar este problema. Estos sistemas tienen un **único servidor** en donde se almacenan todos los archivos versionados en donde los usuarios o colaboradores pueden acceder a ellos.

Este sistema tiene muchas ventajas frente a un VCS _(sistema controlador de versiones)_ local. Ya que hasta cierto punto todos saben en que están trabajando los demás colaboradores, los administradores tienen un control mas detallado de lo que puede hacer cada usuario y es mas fácil administrar una CVCS que tener que lidiar con VCS locales de cada uno de los colaboradores.

<amp-img src="{{ site.baseurl }}assets/post/2018-02-15-how-to-git/cvcs.png" width="656" height="400" layout="responsive" alt="" class="mb3">
</amp-img>

## Controlador de versiones distribuido

Los sistemas de control de versiones distribuidos _(DVCS por sus siglas en ingles)_ nos dan una solución a los problemas mencionados en los anteriores VCS. En un DVCS _(como Git, Mercurial, Bazaar o Darcs)_ los usuarios no solo descargan la ultima copia instantánea de los archivos, si no que se genera una **replica completa** del repositorio. De esta forma, si un servidor u ordenador **deja de funcionar** y estos sistemas estaban colaborando a través de el, **cualquiera** de los repositorios disponible de los usuarios puede ser copiado al servidor para restaurarlo.

Cada clon es realmente una copia completa de todos los datos. Además, muchos de estos sistemas se encargan de manejar numerosos repositorios remotos con los cuales se puede trabajar, de tal forma que se puede colaborar simultáneamente con diferentes grupos de personas en distintas maneras dentro del mismo proyecto.

<amp-img src="{{ site.baseurl }}assets/post/2018-02-15-how-to-git/dvcs.png" width="656" height="400" layout="responsive" alt="" class="mb3">
</amp-img>

Ahora que ya tenemos una idea mas clara de lo que es un sistema controlador de versiones, podemos ver mas a fondo lo que es realmente Git y como funciona :muscle: _(Git, como ya mencionamos es un sistema controlador de versiones distribuido)_.

--------------------------------------------------------------------------------

# Beneficios de Git

- Velocidad :zap:.
- Tiene un diseño **sencillo** para darte las herramientas necesarias con las cuales puedes moverte en el tiempo del VCS :hourglass_flowing_sand:.
- Apoyo al desarrollo no lineal, con el que puedes **bifurcar** tu proyecto para trabajar en varias cosas al mismo tiempo :twisted_rightwards_arrows:.
- Sistema completamente distribuido :computer: :computer:.
- Capacidad para manejar proyectos de **gran** tamaño :chart_with_upwards_trend:.

--------------------------------------------------------------------------------

# ¿Como maneja Git los datos?

Comúnmente los VCS almacenan la información en forma de una **lista de cambios en los archivos**. Estos sistemas manejan esta información como archivos y las modificaciones que se le hicieron a través del tiempo.

Git, a diferencia de los demás, maneja sus datos como **conjuntos de fotos** de un sistema de archivos miniatura, cada vez que confirmamos un cambio o guardamos el estado de nuestro proyecto en Git, este lo que hace es tomar una foto del aspecto de todos nuestros archivos en ese momento y guarda una referencia a la foto, para mayor eficiencia si los archivos no se modificaron Git **no almacena** el archivo nuevamente, si no que guarda un enlace al archivo anterior que es idéntico y fue previamente almacenado.

<amp-img src="{{ site.baseurl }}assets/post/2018-02-15-how-to-git/snapshots.png" width="656" height="400" layout="responsive" alt="" class="mb3">
</amp-img>

La mayoría de las operaciones en Git se hacen **localmente**, por lo cual si quieres subir a un avión o aun tren y quieres trabajar un poco en tu proyecto, puedes confirmar tus cambios sin ningún problema hasta que consigas una conexión a red para subirlos.

En Git, todo se verifica mediante una **suma de comprobación** _(checksum)_ antes de que se almacene y a partir de ese momento se identifica con dicha suma.

El método parar generar esta suma se le conoce como **hash SHA-1**. Es una cadena de 40 caracteres hexadecimales el cual se calcula en base al archivo o a la estructura del directorio en Git. Un **hash SHA-1** se ve de esta forma:

`24b9da6552252987aa493b52f8696cd6d3b00373`

Git usa estos hash parar **guardar** toda la información en lugar de el nombre de los archivos, por lo cual estaremos viendo estos hash por todos lados :eyes:.

--------------------------------------------------------------------------------

# Estados de Git

_Es importante poner mucha atención en este tema, ya que es fundamental para poder seguir trabajando con Git sin ningún problema (puedes tomar tus propias notas si lo crees necesario) :memo:._

Git maneja tres estados en los cuales se pueden encontrar tus archivos:

- Confirmado _(commited)_, significa que los datos se encuentran **almacenados** de manera segura en tu **base de datos local**.
- Modificado _(modified)_, significa que el archivo tuvo **cambios** pero aun **no se han confirmado** a tu base de datos local.
- Preparado _(staged)_, significa que has **marcado** un archivo **modificado** para que vaya en tu próxima **confirmación**.

Esto nos lleva a las tres secciones principales que tiene un proyecto en Git:

- El directorio de trabajo _(working directory)_ es la **copia** de una versión del proyecto **almacenada en disco** para que la puedas usar o modificar.
- Área de preparación _(staging area)_ es un archivo que almacena la información acerca de lo que va a ir en tu próxima confirmación.
- El directorio de Git _(Git directory o Repository)_ es donde se almacenan los meta-datos y la base de datos de los objetos para tu proyecto, **es la parte mas importante de Git** y es lo que se copia cuando clonas un repositorio desde otra computadora.

<amp-img src="{{ site.baseurl }}assets/post/2018-02-15-how-to-git/sections.png" width="656" height="400" layout="responsive" alt="" class="mb3">
</amp-img>

La forma **correcta** de tener un flujo de trabajo en Git es:

1. Se **modifican** los archivos en tu **directorio de trabajo**.
2. Preparas tus archivos listos, añadiéndolos a tu **área de preparación**.
3. Confirmas los cambios realizados, tomándolos tal cual del área de preparación y almacena esa copia instantánea de forma **permanente** en tu **directorio de Git**.

--------------------------------------------------------------------------------

Ya sabemos que es Git y como es que funciona realmente, ahora si podemos ensuciarnos las manos y comenzar a utilizarlo. :raised_hands:.

Se puede trabajar de muchas formas en Git. La mejor forma y la que estaremos viendo es con las herramientas originales de la **linea de comandos**. Existen muchas otras opciones con **interfaces de usuario**, pero la linea de comando es es el único lugar donde se puede ejecutar **todos** los comandos de Git. Sin embargo, si aprendemos a usar la linea de comandos desde un inicio, podremos después utilizar cualquier software con interfaz de usuario y buscar la forma de hacer las cosas, en cambio si iniciamos con una interfaz de usuario, nos sera mas difícil, debido a que estos sistemas solamente implementan **una parte** de las características de Git.

--------------------------------------------------------------------------------

# Instalación de Git

Antes de poder empezar a trabajar, debemos contar con Git instalado en nuestra computadora.

Linux y Mac vienen por defecto con Git instalado, pero no estaría mal asegurarnos de que este instalado o de actualizarlo a la versión mas reciente.

## Instalación en Windows

La mejor forma de instalar Git en Windows es por medio de el instalador de [Github para Windows](https://desktop.github.com/), que incluye la versión de linea de comandos y la interfaz de usuario de Git.

Tambien se puede intalar de una forma mas oficial, desde [Git en Windows](https://git-scm.com/download/win) pero el proceso de instalación es un poco mas complicado ya que es mas personalizable.

## Instalación en Mac

Como mencionamos antes, en Mac ya viene instalado Git por defecto, pero nunca esta de mas verificar o actualizar. Puedes hacer la instalación mediante un [instalador binario](http://git-scm.com/download/mac.). Lo puedes descargar en la pagina de [Git](http://git-scm.com/download/mac.).

## Instalación en Linux

En linux puedes instalar Git mediante la herramienta básica de administración de paquetes que tiene tu distribución :package: .

### Debian/Ubuntu

`$ apt-get install git`

### Fedora

`$ yum install git`

### Gentoo

`$ emerge --ask --verbose dev-vcs/git`

_**si no aparece tu distribución puedes consultar la [lista completa](https://git-scm.com/download/linux).**_

--------------------------------------------------------------------------------

# Configurando Git

Lo primero que debemos hacer cuando instalamos Git es establecer un **nombre de usuario** y una **dirección de correo electrónico**. Esta información se introduce de manera **inmutable** siempre que realizamos un _commit_.

Para establecer estos valores lo hacemos desde la **linea de comandos** mediando los siguientes comandos:

`$ git config --global user.name "Panchito López"`

`$ git config --global user.email panchito@example.com`

Para entender mejor `git config` es una herramienta que nos permite obtener y establecer las **variables de configuración** para Git. Al usar la bandera `--global` estamos especificando que la configuración que vamos a establecer sera para **todo** lo que se haga en el sistema con Git. Si se quiere sobrescribir esta información con otro nombre y/o correo para trabajar en algún proyecto en especifico, unicamente ejecutamos el comando **sin** el `--global`.

## Establecer editor

Puedes establecer el **editor de texto** por defecto que Git utilizara cuando necesite que introduzcas un mensaje, en caso de **no indicar** nada, Git utilizara el editor por defecto de tu sistema.

Para establecer tu editor usa el siguiente comando:

`$ git config --global core.editor atom`

En este caso yo estoy utilizando [Atom](https://atom.io/) como mi editor por defecto, pero tu puedes poner el que tu quieras.

## Comprobar configuración

Si quieres comprobar la configuración que tienes en Git, puedes hacerlo con en el comando `git config --list` y se te mostrara una lista de todas tus propiedades de Git:

```terminal
$ git config --list
user.name=Panchito López
user.email=panchito@example.com
core.editor=atom
...
```

--------------------------------------------------------------------------------

Ahora si ya tenemos todo completamente listo para poder comenzar a versionar nuestros proyectos y sacarle todo el provecho a Git :ok_hand: .

Ya es momento de sumergirnos en lo divertido y comenzar a teclear en nuestra linea de comandos. A continuación aprenderemos a movernos en el tiempo con las herramientas que nos ofrece Git mediante la linea de comandos :tada: .

--------------------------------------------------------------------------------

#

--------------------------------------------------------------------------------

# Referencias

La información que se utilizo en este curso, fue extraída de la [pagina oficial de Git](https://git-scm.com/) y de el libro de [Pro Git por Scott Chacon y Ben Straub - Segunda Edición, Publicado por Apress](https://git-scm.com/book/en/v2)

## Aquí puedes descargar el libro en PDF y un Cheat Sheet increible de Git/GitHub:

- [Pro Git por Scott Chacon y Ben Straub - Segunda Edición, Publicado por Apress][1] :closed_book:
- [GitHub - Git - Cheat Sheet][2] :octocat:

[1]:{{ site.baseurl }}/downloads/books/progit.pdf

[2]:{{ site.baseurl }}/downloads/cheat-sheets/github-git-cheat-sheet.pdf
