---
title: Respaldar servidor completo
author: guerrerocarlos
layout: post
permalink: /respaldar-servidor-completo/
categories:
  - Linux
tags:
  - linux
---
Para enviar el contenido completo de un servidor a una carpeta en otro servidor a modo de respaldo, la mejor opción es rsync:

***rsync &#8211;progress &#8211;rsh=&#8217;ssh -pPUERTO&#8217; -qzaH &#8211;exclude=/proc/\* &#8211;exclude=/tmp/\* &#8211;exclude=/lost+found/* / usuario@servidor\_destino:carpeta\_destino/***