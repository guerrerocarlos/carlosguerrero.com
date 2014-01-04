---
title: Problemas con locales en VPS de Linode
author: guerrerocarlos
layout: post
permalink: /problemas-con-locales-en-vps-de-linode/
categories:
  - Internet
  - Linux
---
Resulta que las imagenes que usa [Linode.com][1] para sus VPS basados en Ubuntu dan errores muy peculiares de locales (incluso recién instalados), generando mensajes como estos:

> Error: The locale requested by the environment is invalid.

o

> bash: warning: setlocale: LC_ALL: cannot change locale (loquesea.UTF-8)

o un poco mas elaborados:

> perl: warning: Setting locale failed.  
> perl: warning: Please check that your locale settings:  
> LANGUAGE = &#8220;en_US:en&#8221;,  
> LC_ALL = (unset),  
> LC_CTYPE = &#8220;UTF-8&#8243;,  
> LANG = &#8220;en_US.UTF-8&#8243;  
> are supported and installed on your system.  
> perl: warning: Falling back to the standard locale (&#8220;C&#8221;).  
> Error: The locale requested by the environment is invalid. 

o para hacerlo mas divertido e inentendible:

> perl: warning: Setting locale failed.  
> perl: warning: Please check that your locale settings:  
> LANGUAGE = (unset),  
> LC_ALL = (unset),  
> LANG = “en_US.UTF-8″  
> are supported and installed on your system.  
> perl: warning: Falling back to the standard locale (“C”).  
> locale: Cannot set LC_CTYPE to default locale: No such file or directory  
> locale: Cannot set LC_MESSAGES to default locale: No such file or directory  
> locale: Cannot set LC_ALL to default locale: No such file or directory 

Ocasionando incomodos problemas para utilizar [mosh][2] e incluso **postgres** 

**SOLUCION:**  
Ejecutar los siguientes comandos en secuencia (reemplazar es_ES por su idioma de preferencia):

> export LANGUAGE=es_ES.UTF-8  
> echo &#8216;LANGUAGE=&#8221;es_ES.UTF-8&#8243;&#8216; >> /etc/default/locale  
> echo &#8216;LC\_ALL=&#8221;es\_ES.UTF-8&#8243;&#8216; >> /etc/default/locale  
> export LANG=es_ES.UTF-8  
> export LC\_ALL=es\_ES.UTF-8  
> locale-gen es_ES.UTF-8  
> dpkg-reconfigure locales 

Eso es todo, fue un placer.

 [1]: http://linode.com/
 [2]: http://mosh.mit.edu/