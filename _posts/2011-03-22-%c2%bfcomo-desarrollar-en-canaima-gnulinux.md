---
title: ¿Como desarrollar en Canaima GNU/Linux?
author: guerrerocarlos
layout: post
permalink: /%c2%bfcomo-desarrollar-en-canaima-gnulinux/
categories:
  - Canaima
---
Si quieres modificar algun paquete de Canaima para adaptarlo a tus necesidades, hacerle alguna mejora y/o contribuir a la distribución Canaima GNU/Linux, este es el mejor momento para aprender a hacerlo.

Luego de una muy interesante evolución dentro de los equipos de desarrollo de Canaima, se ha llegado ya a un punto de automatización que permite hacer el proceso de empaquetado y versionamiento del software, un proceso casi transparente para el desarrollador.

Esta guía es un adelanto de lo que probablemente será uno de los modelos oficiales de desarrollo para la distribución. En una intención de compartir y socializar el conocimiento que he adquirido en el desarrollo y uso de estas nuevas herramientas.

**Paso 1: Selecciona un paquete que quieras modificar:**

Ingresa a <http://gitorious.org/canaima-gnu-linux/> y selecciona cualquiera de los paquetes que allí se encuentran. Todos los paquetes que verás son los que conforman la distribución, como por ejemplo: [canaima-plymouth][1] es el tema grafico que muestra el logo de canaima con las estrellas dando vueltas en circulo cuando se inicia el sistema; [canaima-estilo-visual][2] contiene todos los iconos y el estilo gráfico; mientras que [canaima-escritorio-gnome][3] tiene todo lo referente al entorno grafico por defecto de canaima (gnome).

**Paso 2: Instala *canaima-desarrollador*:**

&#8220;*canaima-desarrollador*&#8221; es un paquete que instala una colección de herramientas y documentación que tienen como objetivo facilitar todo el proceso de desarrollo y empaquetamiento de aplicaciones para Canaima. Para instalarlo puedes hacerlo mediante el gestor de paquetes synaptic buscando la palabra &#8220;*canaima-desarrollador*&#8221; o simplemente ejecutando &#8220;aptitude install canaima-desarrollador&#8221; desde cualquier terminal (actualmente debes tener el repositorio de ***pruebas*** en  /etc/apt/sources.list).

**Paso 3: Traete el codigo fuente a tu computadora:**

O en terminos de versionamiento &#8220;Clonalo&#8221; a tu maquina para hacerle las modificaciones. En Canaima se utiliza un [sistema de control de versiones][4] llamado [&#8220;git&#8221;][5] este sistema es el que nos permite trabajar de manera distribuida y modificar el codigo fuente del sistema al mismo tiempo por muchos desarrolladores y poder integrar todas las mejoras en un solo codigo; en otras palabras es como si muchos arquitectos pudieran modificar el plano de una casa al mismo tiempo, cada uno desde un rincon diferente de Venezuela, y luego se pudieran integrar en un solo plano todas las modificaciones de cada uno para resultar en un solo plano final. Solo que en vez de el plano de una casa, es el plano del sistema operativo. Obviamente este sistema &#8220;git&#8221; permite ver cada modificacion, retroceder, deshacer cambios y todo lo necesario para que entre todos podamos decidir que modificaciones se quedan y cuales no. [Aqui puedes ver][6] una hoja de resumen en español de como se utiliza git.

Es por eso que la forma mas sencilla de obtener el codigo fuente de cualquier paquete de Canaima, es tambien utilizando &#8220;git&#8221;, supongamos que quieres modificar el codigo de [canaima-plymouth][1] para cambiar el color de fondo que sale al iniciar canaima.

Deberás ingresar a http://gitorious.org/canaima-gnu-linux/ y ver donde dice **Clone & push urls** justo debajo de &#8220;canaima-plymouth&#8221;, alli copias la linea que dice: &#8220;http://git.gitorious.org/canaima-gnu-linux/canaima-plymouth.git&#8221;para utilizarla en el comando:

> ***$ git clone http://git.gitorious.org/canaima-gnu-linux/canaima-plymouth.git***

al terminar este comando tendrás una nueva carpeta llamada *canaima-plymouth* donde se encuentra el codigo fuente que puedes modificar a tu gusto.

**Paso 4: Realiza las modificaciones/mejoras/aportes:**

En este ejemplo, vamos a modificar el color de fondo que sale al arrancar canaima, que por defecto es un degradado de marron oscuro.

Como es de esperarse, cada codigo fuente requiere ser revisado, y entendido para poder ser modificado, por lo que en este paso habria que revisar todo el contenido de las carpetas y entender el funcionamiento del tema, esperando que el desarrollador se haya tomado la molestia de documentarlo lo maximo posible para facilitar precisamente este proceso.

Luego de entendido el codigo, nos damos cuenta que el codigo fuente se encuentra dividido en varias carpetas, cuales son:

AUTHORS (contiene la información de quienes hicieron y han aportado a este paquete, y a quienes corresponden entonces los creditos de autoria)  COPYING (define la licencia del software y los permisos que tiene o no de ser copiado y distribuido, obviamente canaima-plymouth tiene licencia GPL) CREDITS (contiene los creditos y agradecimientos que el autor haya querido dar a quienes colaboraron y siguen colaborando en el paquete) debian (es una carpeta que contiene toda la informacion y ajustes requeridos para empaquetar este software para debian) img (contiene las imagenes que utiliza este codigo fuente) Makefile (es el archivo que define como se &#8220;compila&#8221; o instala este paquete, independientemente del modo de empaquetamiento que se quiera usar) README (contiene la descripcion e instrucinoes) scripts (es una carpeta con los scripts que hacen que el tema pueda funcionar en plymouth) src (es una carpeta que contiene los archivos fuentes con los que se han creado las imagenes que ahora se encuentran en la carpeta img, por ejemplo alli esta el archivo de Blender con el que se crearon las estrellas en 3D, que giran al rededor del logo, asi como el archivo original de gimp con el que se realizo el logo) TODO (es un archivo de texto donde se tiene anotado cualquier otra cosa que falte por hacer)

Para modificar los colores de fondo se deben modificar las lineas 4 y 5 del archivo ***/scripts/canaima-plymouth.script***

Window.SetBackgroundTopColor (0.313, 0.241, 0.036); #esta linea define el color de fondo del borde superior de la pantalla  
Window.SetBackgroundBottomColor (0.392, 0.249, 0.061); #esta linea define el color de fondo del borde inferior de la pantalla

Como se puede observar, el fondo resultante es un degradado desde el color superior al color inferior. Los valores se refieren a la cantidad de rojo, verde y azul que lleva cada color, de manera que (0.313, 0.241, 0.036) da un marron mas claro que (0.392, 0.249, 0.061)

Les dejo a su ingenio como generar el color que necesiten, les doy la pista de que el valor de cada color primario solo va de 0 a 1. <img src='http://blog.carlosguerrero.com/wp-includes/images/smilies/icon_wink.gif' alt=';)' class='wp-smiley' /> 

**Paso 5: Generar el paquete .deb:**

Luego de realizadas las modificaciones, para generar el paquete .deb con el que se intalará canaima-plymouth en esta version modificada, basta con ejecutar el comando:

> ***c-d empaquetar &#8211;mensaje=&#8221;Version de canaima-plymouth con el color de fondo en degradado de equis color&#8221; &#8211;procesadores=&#8221;2&#8243; &#8211;no-enviar***

El &#8220;mensaje&#8221;es una linea de texto que sirve para identificar las modificaciones que se realizaron para este empaquetamiento, si tienes una maquina con cuatro procesadores, puedes poner &#8220;4&#8243; en vez de &#8220;2&#8243;, &#8211;no-enviar se utiliza para generar el paquete, sin subir las modificaciones al repositorio git de donde extragiste el codigo fuente. Para poder subir codigo directamente al repositorio de Canaima en gitorious.org, debes formar parte del grupo [+canaima-developers][7] pero tambien puedes configurar canaima-desarrollador para que suba tu codigo al repositorio git que tu prefieras (puedes crear tu propio repositorio en gitorious.org sin ninguna restricción, de modo que lleves tus propios proyectos y desarrollos por separado, luego tus aportes pueden ser integrados a los repositorios de canaima sin ningun problema), esta información la configuras en el archivo:*** ~/.config/canaima-desarrollador/usuario.conf  
***

Una vez que tengas bien configurado este archivo usuario.conf, podrás tambien obtener el codigo fuente del paquete que necesites, con el comando:

***$ c-d descargar &#8211;proyecto=&#8221;canaima-plymouth&#8221;***

en vez de ***&#8220;git clone &#8230;&#8221;***

Este comando ***c-d empaquetar &#8230;*** generará el .deb en la carpeta que le hayas especificado en el archivo usuario.conf, esto para facilitar que tengas todos los codigos fuentes en un lugar, y todos los .deb se generen en otro.

Luego puedes usar ese .deb para instalarlo en tu maquina directamente o subirlo a algun repositorio que luego utilizas con canaima-semilla y con un comando tan sencillo como:

> ***$ canaima-semilla construir &#8211;medio=&#8221;iso&#8221; &#8211;arquitectura=&#8221;i386&#8243; &#8211;sabor=&#8221;popular&#8221;***

Obtienes una imagen .iso de Canaima GNU/Linux pero con las modificaciones realizadas por ti en los paquetes, pero canaima-semilla es ya otra herramienta que merece su propio articulo <img src='http://blog.carlosguerrero.com/wp-includes/images/smilies/icon_wink.gif' alt=';)' class='wp-smiley' />

 [1]: http://gitorious.org/canaima-gnu-linux/canaima-plymouth
 [2]: http://gitorious.org/canaima-gnu-linux/canaima-estilo-visual
 [3]: http://gitorious.org/canaima-gnu-linux/canaima-escritorio-gnome
 [4]: http://es.wikipedia.org/wiki/Control_de_versiones
 [5]: http://git-scm.com/
 [6]: http://blog.carlosguerrero.com/index.php/2010/11/guia-cheatsheet-de-uso-de-git-como-sistema-de-versionamiento/
 [7]: http://gitorious.org/+canaima-developers