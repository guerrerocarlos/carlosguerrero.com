---
title: 'Receta: Habilitar php en NGINX'
author: guerrerocarlos
layout: post
permalink: /receta-habilitar-php-en-nginx/
categories:
  - Internet
  - Linux
---
Luego de instalar nginx:

> \# sudo aptitude install nginx

solo hace falta instalar php:

> sudo aptitude install php5-cgi

y crear este archivo **/etc/init.d/php-fastcgi** con el siguiente contenido:  


Se le dan permisos de ejecución al script:

> \# chmod +x /etc/init.d/php-fastcgi

Y se levanta el interprete de php:

> \# /etc/init.d/php-fastcgi start

Sin olvidar incluirlo en la lista de servicios a arrancar automaticamente al iniciar el servidor:

> \# update-rc.d php-fastcgi defaults

Para probar que todo está funcionando bien, basta con agregar esto en la configuración de tu sitio en nginx:

> location ~ \.php$ {  
> fastcgi_pass 127.0.0.1:9000;  
> fastcgi_index index.php;  
> fastcgi\_param SCRIPT\_FILENAME /var/www/nginx-default$fastcgi\_script\_name;  
> include fastcgi_params;  
> }

Colocar un archivo de ejemplo **/var/www/nginx-default/test.php**

> < ?php
> 
> phpinfo();
> 
> ? >

Y reiniciar nginx:

> \# /etc/init.d/nginx restart 

Si al entrar al sitio por el navegador, ves el contendio de Php Info, estas listo <img src='http://blog.carlosguerrero.com/wp-includes/images/smilies/icon_smile.gif' alt=':)' class='wp-smiley' />