---
presentation:
  fragments: true
  shuffle: false
  transition: fade

puppeteer:
  landscape: true
  format: "letter"

export_on_save:
  puppeteer: true
---

<!-- slide -->
# start( )

<!-- slide -->
Antes de iniciar propiamente el curso, necesitamos asegurarnos de que disponemos de un entorno funcional de Python para lo cual se requiere:

1. Una instalación funcional de **Python 3** <!-- .element: class="fragment" -->
1. Un editor adecuado.<!-- .element: class="fragment"  -->
1. Posibilidad de ejecutar python desde el editor y desde la línea de comandos. <!-- .element: class="fragment" -->
<!-- slide -->
## setup( )

<!-- class="fragment" -->
<p class="fragment">El proceso de instalación dependerá del sistema operativo que usemos
</p>

<!-- slide -->
### setup(os="Linux")
Lo más probable es que ya tengas python3 instalado, simplemente ejecuta [[python -V]] y debe aparecer a continuación el número de versión que tengas.

``` 
drini@gauss:~$ python -V
Python 3.9.6
```

<!-- slide -->

Si aparece Python 2.x , entonces intenta con [[python3 -V]]

``` 
drini@coltrane:~$ python -V
Python 2.7.12 
drini@coltrane:~$ python3 -V
Python 3.8.6 
```

<!-- p: class="fragment"  -->
Si no tienes Python 3 instalado, usa el administrador de paquetes de tu distribución para añadirlo.<!-- p: class="fragment"  -->

<!-- slide -->
###  setup(os="Windows")

Hay dos^(tres?)^ formas comunes de instalarlo. 

La primera es instalarlo directamente desde la página oficial de python, **python.org**
<!-- slide -->
![python.org](./gfx/010-pythonorg.png)
<!-- slide -->
Para facilitarnos la vida más adelante, es necesario que activemos algunas opciones adicionales

![installer](./gfx/020-installer.png)
<!-- slide -->
![installer](./gfx/020-installer.png)
<!-- slide -->
![installer](./gfx/021-installer.png)
<!-- slide -->
![installer](./gfx/022-installer.png)
<!-- slide -->

La segunda alternativa, es usar la tienda de aplicaciones de Microsoft...

![msstore](./gfx/030-msstore.png)

Cualquiera de las opciones (3.9, 3.8, 3.7...) nos sirve.

<!-- slide -->

Una tercera alternativa, si eres valiente, es instalar WSL (Windows Subsystem for Linux) y correr linux dentro de Windows:

<!-- class="fragment" -->
![wsl](gfx/040-wsl.png) 

<!-- slide -->
## edit( )

<!-- slide -->
En realidad, no necesitamos ningún programa especial para crear y ejecutar programas en Python. 

Si bien, es posible escribir directamente el programa en el intérprete, salvo la gente más salvaje, lo usual es redactar el programa en un editor, y luego ejecutarlo aparte.

<!-- slide -->

Y aunque, en principio puedes editar en el bloc de notas, estamos de acuerdo que esto...

![notepad](./gfx/050-notepad.png)

<!-- slide -->
...es mucho más difícil de escribir, corregir y revisar que esto:

![](./gfx/051-highlighted.png)

<!-- slide -->
Por eso, vamos a instalar un editor moderno que 
nos proporcione un entorno de programación más cómodo, no sólo mediante el uso de sintaxis coloreada, sino que permita ejecutar y trabajar con los programas de forma más sencilla<

<!-- slide -->

Existen varias opciones populares, tanto para linux como para windows. En windows, tenemos por ejemplo:

* Sublime Text (la que instalaremos)
* VSCode (la que usa el profe)
* Notepad++
* Atom

<p class="fragment">y muchas, muchas opciones más.</p>

<!-- slide -->

Para instalar SublimeText, vamos a [[sublimetext.com]] y descargamos la versión gratis.

![st](gfx/060-sublimeweb.png)

<!-- slide -->

![installer](gfx/061-sublimeinstaller.png)

<!-- slide -->

Trans instalarlo, lo abrimos, y creamos el siguiente archivo, guardándolo con el nombre [[gauss00.py]]

``` python
S=0
for k in range(101):
	S=S+k

print(S)
```

<!-- slide -->
Es importante que los archivos de python tengan extensión [[.py]], para que aparezcan correctamente coloreados. 

![st](gfx/062-sublimepy.png)

<!-- slide -->

Si usas linux, hay dos editores muy populares: [[vim]] y [[emacs]]. El primero es prácticamente el estándar que está en todas partes, pero es algo complicado de dominar por sus peculiaridades.

Alternativas comunes para el modo gráfico pueden ser: [[gedit]], [[kate]], [[geany]], o vesiones para linux de Sublime Text o VSCode.

<!-- slide -->

## run( )

<!-- slide -->

Ya tenemos instalado Python, ya tenemos instalado un editor, ya tenemos un pequeño programa listo, nos falta el tercer paso: poder usar nuestro programa.

Tenemos primero que cerciorarnos que podemos correr un programa deste el editor, pero también desde una línea de comandos.

<!-- slide -->

![st](gfx/062-sublimepy.png)

En Sublime Text, si ya tenemos un programa escrito y guardado, y si Python está configurado correctamente, basta con presionar [[Control+B]] para correrlo.

Tomemos el programa [[gauss00.py]] del ejemplo. 
(¿Qué está calculando?)

<!-- slide -->
Al presionar [[Control+B]], el programa se ejecuta y muestra su resultado en la parte inferior: [[5050]]

![run](gfx/070-sublimerun.png)

<p class="fragment">Diferentes editores tendrán distintas formas de correr los programas.</p>

<!-- slide -->

Si el programa no se ejecuta y aparece un error de que Python no está instalado, asegúrate de que durante la instalación seleccionaste añadir Python a la variable [[PATH]].

Asegúrate también de haber copiado correctamente el código (¡los espacios son importantes!).

<!-- slide -->

El programa de ejemplo realiza un cálculo y muestra el resultado. Pero en ocasiones será necesario pedir al usuario información (por ejemplo, hasta qué número llegar, o con qué dato o número trabajar, etc.) 

En este caso, necesitaremos correr el programa desde la **línea de comandos**.

<!-- slide -->

En Windows, hay dos líneas de comando. La antigua "ms-dos" y la nueva "powershell".

Presiona la tecla [[⊞ Win.]] y escribe [[cmd]].

![cmd](gfx/080-cmd.png)

<!-- slide -->

La vieja confiable

![cmd](gfx/081-cmd.png)

<!-- slide -->

Otra manera de abrir la terminal Powershell, en vez de usar el menú de inicio y escribir Powershell, es presionar [[Win+X]] y seleccionar Powershell del menú.

![cmd](gfx/082-powermenu.png)

<!-- slide -->

Una vez abierta la terminal, vamos al directorio donde tenemos guardado nuestro programa.

![run](gfx/090-run01.png)

<p class="fragment">
Y veremos el resultado del cálculo, [[5050]].</p>

<!-- slide -->

Aparentemente pudimos haber hecho lo mismo desde el editor, por ello damos otro ejemplo de programa donde sí es necesario usar la líena de comando para interactuar con el usuario:

Crea un archivo denominado [[saludo00.py]] con el siguiente código:

``` python
nombre = input("¿Cómo te llamas? ")

print("Saludos,", nombre)
```

Aquí, la línea con [[input( )]] pide información al usuario.

<!-- slide -->

Si lo ejecutamos dentro del editor, tendremos problemas porque no podemos "darle" la información que pide y se bloqueará.

En cambio, desde la línea de comandos:

![run](gfx/090-run02.png)

<p class="fragment">
y cuando pongamos el nombre y presionemos [[Enter]]:</p>

<!-- slide -->

![run](gfx/090-run03.png)

<p class="fragment">
El programa está "usando" la información que le dimos.
</p>

<!-- slide -->
¡Eso es to.. eso es to.. eso es todo amigos!


