---
title: 'Receta: Instalar OpenERP 6.1 en Ubuntu/Debian'
author: guerrerocarlos
layout: post
permalink: /receta-instalar-openerp-6-1-en-ubuntudebian/
categories:
  - Linux
---
Primero que nada, instalar todo lo básico para compilar paquetes:

> \# aptitude install gnulib

Segundo hay que instalar Postgres, pero para eso ya hice esta otra guia: [Receta para Instalar Postgres][1]

Ahora instalamos lo básico para instalar paquetes python:

> \# aptitude install python-setuptools

Inmediatamente instalamos [pip][2] para no ir a la caer en la instalación de seguir usando easy_install:

> \# easy_install pip

Procedemos a instalar todos los paquetes necesarios, usando los paquetes en los repositorios de ubuntu:

> \# aptitude install postgresql-server-dev-8.4 python2.7-dev python-lxml python-yaml python-reportlab python-mako python-pychart python-werkzeug python-babel python-dateutil python-openid

Instalamos el modulo que permitirá a python comunicarse con postgres usando [pip][2]:

> \# pip install psycopg2

Por ultimo una librería que se llama [pytz][3] muy útil para manejar múltiples zonas horarias en las aplicaciones basadas en python:

> \# pip install pytz

Nos conectamos a postgres mediante PgAdminIII como y creamos un nuevo usuario dedicado para postgres, yo lo llamé &#8220;openerp1&#8243;, no olviden de darle permiso para crear tablas:

[<img class="aligncenter size-medium wp-image-416" title="Crear nuevo usuario de Postgres" src="http://blog.carlosguerrero.com/wp-content/uploads/2012/07/Captura-de-pantalla-2012-07-26-a-las-17.07.41-300x185.png" alt="" width="300" height="185" />][4]

Luego de creado el usuario que usará *OpenERP* para acceder a *postgres*, descargamos el código fuente desde [OpenERP Downloads][5]:

> \# wget http://nightly.openerp.com/6.1/releases/openerp-6.1-latest.tar.gz

Descomprimimos el tar.gz que se descargó:

> \# tar zxvf http://nightly.openerp.com/6.1/releases/openerp-6.1-latest.tar.gz

Nos movemos al interior de esa carpeta y **sin ser root** ejecutamos:

> ./openerp-server &#8211;database=openerp1 &#8211;db\_user=openerp1 &#8211;db\_password=contraseñaopenerp1 &#8211;db_host=127.0.0.1

Y ya podemos acceder a nuestra instancia de OpenERP, abriendo en el navegador http://127.0.0.1:8069/ o la ip pública del servidor donde lo estén instalando.

Una vez allí, lo primero a hacer es crear una nueva base de datos para OpenERP, haciendo clic en el enlace &#8220;Manage Databases&#8221;:

[<img class="aligncenter size-medium wp-image-418" title="Botón Manage Databases" src="http://blog.carlosguerrero.com/wp-content/uploads/2012/07/Captura-de-pantalla-2012-07-26-a-las-21.32.19-300x218.png" alt="" width="300" height="218" />][6]

Habiendo entrado al &#8220;Database Manager&#8221; basta con rellenar los campos para darle una contraseña al que será el Administrador de esa instancia, y ponerle un nombre a esa instancia. La contraseña que dice &#8220;Master password&#8221; no hace falta cambiarla, es la que viene por defecto y se define es en los archivos de configuración internos de OpenERP.

[<img class="aligncenter size-medium wp-image-419" title="Database Manager" src="http://blog.carlosguerrero.com/wp-content/uploads/2012/07/Captura-de-pantalla-2012-07-26-a-las-21.33.25-300x141.png" alt="" width="300" height="141" />][7]Se le da ahora &#8220;Create&#8221; y a esperar un par de minutos que OpenERP se encargue de inicializar todo, luego basta con seleccionar con qué modulos desea comenzar su instalación, y empezar a disfrutar de las bondades de este tremendo Framework para empresas:

<p style="text-align: center;">
  <a href="http://blog.carlosguerrero.com/wp-content/uploads/2012/07/Captura-de-pantalla-2012-07-26-a-las-17.26.03.png"><img class="aligncenter size-medium wp-image-420" title="Modulos OpenERP 6.1" src="http://blog.carlosguerrero.com/wp-content/uploads/2012/07/Captura-de-pantalla-2012-07-26-a-las-17.26.03-300x131.png" alt="" width="347" height="151" /></a><strong>(clic para ampliar)</strong>
</p>

&nbsp;

&nbsp;

 [1]: http://blog.carlosguerrero.com/receta-instalar-postgres/
 [2]: http://www.pip-installer.org
 [3]: http://pytz.sourceforge.net/
 [4]: http://blog.carlosguerrero.com/wp-content/uploads/2012/07/Captura-de-pantalla-2012-07-26-a-las-17.07.41.png
 [5]: http://www.openerp.com/downloads
 [6]: http://blog.carlosguerrero.com/wp-content/uploads/2012/07/Captura-de-pantalla-2012-07-26-a-las-21.32.19.png
 [7]: http://blog.carlosguerrero.com/wp-content/uploads/2012/07/Captura-de-pantalla-2012-07-26-a-las-21.33.25.png