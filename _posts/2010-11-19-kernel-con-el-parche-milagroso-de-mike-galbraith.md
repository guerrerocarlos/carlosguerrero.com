---
title: Kernel Linux con el parche milagroso de Mike Galbraith
author: guerrerocarlos
layout: post
permalink: /kernel-con-el-parche-milagroso-de-mike-galbraith/
categories:
  - Canaima
  - Linux
---
Empaqueté el kernel Linux 2.6.37-rc2-1 con el parche &#8220;milagroso de Mike Galbraith&#8221; aplicado, de manera de probarlo y ver la diferencia.

En una prueba sencilla con *glxgears -info* tuvime los siguientes resultados antes de utilizar este nuevo kernel:

*3866 frames in 5.0 seconds = 773.078 FPS  
3861 frames in 5.0 seconds = 771.517 FPS  
3867 frames in 5.0 seconds = 773.301 FPS*  
Y despues de instalar el nuevo kernel:  
*5820 frames in 5.0 seconds = 1163.894 FPS  
5842 frames in 5.0 seconds = 1168.349 FPS  
5793 frames in 5.0 seconds = 1158.497 FP*

Por lo que si parece que tiene buena mejora en el desempeño del equipo.

Para probarlo en Debian **Squeeze** puede descargarlo directamende del [repositorio de desarrollo de Canaima][1] o puede agregar el repositorio de desarrollo de Canaima en su /etc/sources.lst:

> **deb http://repositorio.canaima.softwarelibre.gob.ve/ desarrollo usuarios**

Si utilizan Canaima GNU/Linux, basta con ejecutar:

> **aptitude install linux-image-2.6.37-rc2-1-686-canaima**

[Esté][2] es el archivo de configuracion que utilizé para compilar el kernel, en caso de que quieran revisarlo.

 [1]: http://repositorio.canaima.softwarelibre.gob.ve/pool/usuarios/l/linux-source-2.6.37-rc2-1-686-canaima/
 [2]: http://www.carlosguerrero.com/files/config