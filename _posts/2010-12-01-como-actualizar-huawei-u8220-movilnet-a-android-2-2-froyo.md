---
title: Como actualizar Huawei U8220 (Movilnet) a Android 2.2 (Froyo)
author: guerrerocarlos
excerpt: 'Huawei no lanza aún una actualización oficial para este equipo y tampoco parece que vaya a hacerlo, a pesar de las muchas mejoras que trae la versión 2.2  de modo que no quedamos que recurrir a vías alternativas para actualizar nuestro U8220 a lo último en Android, nosotros podemos hacerlo de todas maneras:'
layout: post
permalink: /como-actualizar-huawei-u8220-movilnet-a-android-2-2-froyo/
categories:
  - Android
  - Linux
---
Huawei no lanza aún una actualización oficial para este equipo y tampoco parece que vaya a hacerlo, a pesar de las [muchas mejoras que trae la versión 2.2][1] de modo que no quedamos que recurrir a vías alternativas para actualizar nuestro U8220 a lo último en Android, nosotros podemos hacerlo de todas maneras:

La gente de [cyanogenmod][2] se especializa en generar firmware especialmente diseñado para sacarle el máximo provecho (desempeño y estabilidad) a tu equipo, basados el en proyecto Open Source **Android**, siendo en la mayoria de los casos, mucho mejor que el propio firmware que trae el equipo de fabrica. Estas imagenes incluyen además sistemas sin limitaciones o ya &#8220;rooteados&#8221; de manera que puedes instalar aplicaciones que normalmente no puedes si usas el sistema original, como por ejemplo para hacer &#8220;tether&#8221; es decir convertir tucelular en un router para compartir internet.

Lamentablemente el U8220 o &#8220;Pulse&#8221;como se conoce internacinonalmente, aún no es mantenido oficialmente por [cyanogenmod][3] pero un miembro de la comunidad [Modaco.com][4] llamado [&#8220;Tom G.&#8221;][5] a hecho el mod para poder instalar Froyo en el U8220.

**Los pasos para instalar Android 2.2 en tu Huawei U8220 (de Movilnet):**

Descarga todos los siguientes archivos: [[1]Recovery][6], [[2]Time Machine][7], [[3]Mod Froyo][8], [[4]GoogleApps][9]. Opcionalmente puedes descargar la [[5]ROM original de Movilnet][10], en caso de que luego quieras devolver tu sistema a Android 2.1 (muy poco probable que quieras eso).

Aprovecho para copiarme la advertencia que traen estos proyectos:

> A pesar de que estos proyectos te ayudan a sacar mayor provecho a tu Android, ***NO ME HAGO RESPONSABLE*** por equipos bloqueados, tarjetas SD muertas, ni por la guerra termonuclear ni por la crisis economica actual. Por favor investiga acerca de las caracteristiacs incluidas en estas ROM antes de flashearlas. USTED esta eligiendo hacer estas modificaciones y si me señalas a mi por dañar tu equipo, me reiré.

Descomprime el archivo [1] que descargaste.

1.- Apaga el U8220 y enciendelo de nuevo presionando la combinación de botones [Bajar Volumen + Colgar + Encender] hasta que veas la siguiente pantalla:

<div id="attachment_183" class="wp-caption aligncenter" style="width: 310px">
  <a href="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/serial.jpg"><img class="size-medium wp-image-183" title="serial" src="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/serial-300x224.jpg" alt="Modo Comunicación Serial" width="300" height="224" /></a><p class="wp-caption-text">
    Modo Comunicación Serial
  </p>
</div>

2.- Conecta el celular al puerto USB de tu computadora y si estas en *Linux*: ejecuta el script **./install-recovery-linux.sh** (con permisos de root). Si estas en *Windows* tienes que correr es el archivo **install-Clockwork-windows.bat** si estas en mac, **./install-recovery-mac.sh**  
2.1.- Espera unos segundos a que diga **OK**  
3.- Reinicia el U8220 quitandole la batería unos 4 segundos y vuelvela a poner.  
4.- Si se enciende automaticamente, espera y vuelvelo a apagar.  
5.- Copia en la la raiz de la memoria SD de tu celular los archivos [[3]][11] y [[4]][9] y vuelve a insertarla en el U8220. (los .zip, no los descomprimas)  
6.- Enciende U8220 presionando la combinación [Menu + Colgar + Encender]  
7.- Espera a que salga la siguiente pantalla:

<div id="attachment_185" class="wp-caption aligncenter" style="width: 310px">
  <a href="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/Reboot-system-now.jpg"><img class="size-medium wp-image-185" title="Reboot-system-now" src="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/Reboot-system-now-300x224.jpg" alt="ClockworkMod funcionando" width="300" height="224" /></a><p class="wp-caption-text">
    ClockworkMod funcionando
  </p>
</div>

8.- Selecciona la opción** install zip from sdcard**

9.- Selecciona la opción **choose zip from sdcard**

<div id="attachment_189" class="wp-caption aligncenter" style="width: 310px">
  <a href="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/choose-zip-sdcard.jpg"><img class="size-medium wp-image-189" title="choose-zip-sdcard" src="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/choose-zip-sdcard-300x224.jpg" alt="Choose Zip from SDCard" width="300" height="224" /></a><p class="wp-caption-text">
    Choose Zip from SDCard
  </p>
</div>

10.- Selecciona instalar el archivo [[3]][11] existente en la SD y luego acepta descomprimirlo, presionando la tecla verde. PRIMERO DEBE SER INSTALADO CM6.1-RC0-Pulse-beta-&#8230; luego si gapps&#8230; pendientes de eso.

<div id="attachment_187" class="wp-caption aligncenter" style="width: 310px">
  <a href="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/contenido_sd.jpg"><img class="size-medium wp-image-187" title="contenido_sd" src="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/contenido_sd-300x224.jpg" alt="Seleccionando el archivo .zip" width="300" height="224" /></a><p class="wp-caption-text">
    Seleccionando el archivo .zip
  </p>
</div>

11.- Selecciona instalar el archivo [[4]][9] existente en la SD y luego acepta descomprimirlo, presionando la tecla verde.  
12.- Selecciona la opción **wipe data/factory reset**

** **

<div id="attachment_182" class="wp-caption aligncenter" style="width: 310px">
  <strong><strong><a href="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/wipe-reset.jpg"><img class="size-medium wp-image-182" title="wipe-reset" src="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/wipe-reset-300x224.jpg" alt="Wipe data/factory reset" width="300" height="224" /></a></strong></strong><p class="wp-caption-text">
    Wipe data/factory reset
  </p>
</div>

** **

13.- Confirma que estas seguro** (YES).**

** **

<div id="attachment_184" class="wp-caption aligncenter" style="width: 310px">
  <strong><strong><a href="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/SeleccionaYES.jpg"><img class="size-medium wp-image-184" title="SeleccionaYES" src="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/SeleccionaYES-300x224.jpg" alt="Confirmación" width="300" height="224" /></a></strong></strong><p class="wp-caption-text">
    Confirmación
  </p>
</div>

** **

14.- Selecciona la opción **reboot system now**  
15.- Preparate para disfrutar de Froyo en tu U8220 despues del arranque <img src='http://blog.carlosguerrero.com/wp-includes/images/smilies/icon_smile.gif' alt=':-)' class='wp-smiley' /> 

En el siguiente video se puede ver el resultado que obtuve en mi Huawei U8220, sin duda una mejora muy grande en desempeño.

**POR FAVOR QUIENES SIGAN ESTAS INSTRUCCIONES TOMAR FOTOS Y/O VIDEOS PARA COMPLEMENTAR AUN MAS ESTE MANUAL. GRACIAS.**



Video de [@machavez84][12]:  


<div id="attachment_153" class="wp-caption aligncenter" style="width: 234px">
  <a href="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/2010-12-01_08-32-17_126_Caracas.jpg"><img class="size-medium wp-image-153" title="Información del Sistema U8220 con Android 2.2" src="http://blog.carlosguerrero.com/wp-content/uploads/2010/12/2010-12-01_08-32-17_126_Caracas-224x300.jpg" alt="Información del Sistema U8220 con Android 2.2" width="224" height="300" /></a><p class="wp-caption-text">
    Información del Sistema U8220 con Android 2.2
  </p>
</div>

 [1]: http://www.youtube.com/watch?v=yAZYSVr2Bhc&feature=player_embedded
 [2]: http://cyanogenmod.com
 [3]: http://cyanogenmod.com/
 [4]: http://android.modaco.com/
 [5]: http://android.modaco.com/content/t-mobile-pulse-pulse-modaco-com/319785/cyanogenmod-6-port-for-pulse/
 [6]: http://dl.dropbox.com/u/5864262/Blog/Recovery_HuaweiU8220.zip
 [7]: http://dl.dropbox.com/u/5864262/Blog/Time_Machine.zip
 [8]: http://dl.dropbox.com/u/5864262/Blog/CM6.1-Pulse-beta-0.40.zip
 [9]: http://dl.dropbox.com/u/5864262/Blog/gapps-mdpi-20100930-signed.zip
 [10]: http://dl.dropbox.com/u/5864262/Blog/ROM_U8220_V100R001C32B820_Venezuela_Movilnet.zip
 [11]: http://dl.dropbox.com/u/5864262/Blog/CM6.1-RC0-Pulse-beta-0.30.zip
 [12]: http://twitter.com/machavez84