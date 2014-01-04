---
title: Script init.d para control de instancias Django
author: guerrerocarlos
layout: post
permalink: /script-init-d-para-control-de-instancias-django/
categories:
  - Internet
  - Linux
---
Si necesitas correr muchas aplicaciones basadas en [Django][1] en un mismo servidor y estas cansado de abrir un [screen][2] o un [tmux][3] para cada instancia, entonces esto es lo que necesitas, un script init.d que automaticamente inicie, detenga o reinicie todas las instancias Django que tengas en una carpeta determinada:



Copia ese archivo en **/etc/init.d/** con el nombre &#8220;django-fastcgi&#8221; y luego ejecuta:

> \# chmod +x /etc/init.d/django-fastcgi  
> \# update-rc.d django-fastcgi defaults

Con eso ya tendrás a la disposición estos comandos:

**Iniciar** todas las instancias Django:

> \# /etc/init/django-fastcgi start

**Detener** todas las instancias Django:

> \# /etc/init/django-fastcgi stop

**Reiniciar** todas las instancias Django:

> \# /etc/init/django-fastcgi restart

Teniendo eso ya solo tendrías que configurar NGINX para que sirva apropiadamente cada una de las aplicaciones para su acceso web, usando los puertos del 8080 en adelante, pero para eso tienes también esta guía: [Configuración NGINX para Django][4]

 [1]: http://djangoproject.com/
 [2]: http://es.wikipedia.org/wiki/GNU_Screen
 [3]: http://tmux.sourceforge.net/
 [4]: http://blog.carlosguerrero.com/entrada-nginx-para-django-fastcgi/