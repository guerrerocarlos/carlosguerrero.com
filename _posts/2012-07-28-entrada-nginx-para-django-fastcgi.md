---
title: Entrada NGINX para Django (fastcgi)
author: guerrerocarlos
layout: post
permalink: /entrada-nginx-para-django-fastcgi/
categories:
  - Internet
  - Linux
---
Una de las maneras mas prácticas en las que se puede poner a funcionar Django mediante NGINX es mediante **fastcgi**, siento dan sencillo como lanzar la aplicación de Django con un comando como el siguiente: 

> ./manage.py runfcgi method=threaded host=127.0.0.1 port=8080

Ese sencillo comando se encarga de lanzar la aplicación Django en modo fastcgi bastando simplemente guardar en NGINX un archivo como el siguiente &#8220;nginx-fastcgi-app&#8221;



que deberá guardarse en /etc/nginx/sites-available y posteriormente ser activado con:

> \# cd /etc/nginx/sites-enabled  
> \# ln -s ../sites-available/nginx-fastcgi-app

Y listo, ya podrémos acceder a la aplicación de Django sin tener que poner el puerto 8080, sino simplemente poniendo la URL que se configuró en NGINX.

Si deseas ponerle seguridad de manera que no cualquiera pueda aún entrar a la aplicación, puedes [agregarle seguridad mediante archivo access de nginx][1]

 [1]: http://blog.carlosguerrero.com/restricciones-de-acceso-en-nginx/