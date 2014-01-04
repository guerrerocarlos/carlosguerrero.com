---
title: Restricciones de acceso en NGINX
author: guerrerocarlos
layout: post
permalink: /restricciones-de-acceso-en-nginx/
categories:
  - Internet
  - Linux
---
Para restringir el acceso a cualquier sitio en nginx, basta con agregar las siguientes lineas a cualquier servidor &#8220;nginx&#8221;:

> auth_basic &#8220;Acceso restringido, solo permitido mediante credencial&#8221;;  
> auth\_basic\_user_file /var/www/archivo.access;

Quedando algo parecido a esto:



De manera que solo puedan acceder los usuarios y contraseñas especificados en el archivo **/var/www/archivos.access**, cuyo contenido deberá ser por ejemplo:

> \# usuario:contraseña:comentario  
> carlos:saEZ6MlWYV9nQ:bienvenido  
> andres:saUbI5w9Auf32

La contraseña se genera usando una de dos opciones:

1.- Comando en Perl:

> perl -le &#8216;print crypt(&#8220;contraseña&#8221;, &#8220;salt-hash&#8221;)&#8217;

2.- Script en python:

Descargar el script: <https://gist.github.com/3191120> (original: <http://trac.edgewall.org/browser/trunk/contrib/htpasswd.py>) y para ejecutarlo sería: htpasswd.py -b archivoaccess usuario password

Y el script se encarga de automaticamente revisar si el usuario ya existe y de ser así, no agrega otra entrada sino que simplemente actualiza su contraseña.

Así que queda a elección de lo que te sea mas practico/útil.