---
title: Sistema de Paquetería totalmente trabado.
author: guerrerocarlos
layout: post
permalink: /sistema-de-paqueteria-totalmente-trabado/
categories:
  - Uncategorized
---
Si alguna vez tienen un error que dice algo como &#8220;list file for package \____ is missing final newline&#8217; for every package&#8221; y no te permite actualizar, instalar ni desinstalar ningun paquete de tu sistema Linux, puede ser debido a que tienes algun error en los scripts que se encuentran en el directorio /var/lib/dpkg/info/ que son todos los scripts de instalacion y desinstalación de todos los paquetes que has instalado, y que aveces necesitan volverse a ejecutar para poder funcionar. La solución mas elegante que encontré fue en [este sitio][1] y lo que hacen es ejecutar el siguiente script en python que se encarga de revisar cada script y corregirlo en caso de tener alguna falla:

> `<code>#!/usr/bin/python<br />
import os`</code>
> 
> dpkg_path = &#8217;/var/lib/dpkg/info/&#8217;  
> paths = os.listdir(dpkg_path)  
> for path in paths:  
> path = dpkg_path + path  
> f = open(path, &#8217;a+&#8217;)  
> data = f.read()  
> if len(data) > 1 and data[-1:] != &#8217;\n&#8217;:  
> f.write(&#8216;\n&#8217;)  
> print &#8217;Corregido el script del paquete:&#8217;, path  
> f.close()

 [1]: http://ubuntuforums.org/showthread.php?t=1319791