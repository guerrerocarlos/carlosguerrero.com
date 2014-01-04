---
title: 'HTML: &#8220;Copiar al portapapeles&#8221; (Ctrl+C)'
author: guerrerocarlos
layout: post
permalink: /html-copiar-al-portapapeles/
categories:
  - Internet
  - Linux
---
[  
<img src="http://blog.carlosguerrero.com/wp-content/uploads/2012/08/no_flash.jpg" alt="" title="no_flash" width="100" height="100" style="float:left" />  
<img src="http://blog.carlosguerrero.com/wp-content/uploads/2012/08/logo_haxe.png" alt="" title="logo_haxe" width="74" height="100" style="float:left" />  
][1]  
</br>  
</br></br>  
Los navegadores no pueden acceder a la portapapeles directamente por razones de seguridad, lo cual imposibilita crear un botón Javascript que realize esta acción, por lo que no queda otra alternativa que usar Flash, pero no se preocupen que gracias a el lenguaje de programación [Haxe][1] y herramientas como [swfmill][2] no hace falta usar ningun software privativo para generar el .swf que se necesita para crear este botón:

[<img src="http://blog.carlosguerrero.com/wp-content/uploads/2012/08/Copiar.png" alt="" title="Copiar" width="134" height="28" class="aligncenter size-full wp-image-465" />][3]  
que es el mismo que usan en github.com ya que fue de hecho, creado por uno de sus desarrolladores  
[<img src="http://blog.carlosguerrero.com/wp-content/uploads/2012/08/copy_to_clipboard-300x28.png" alt="" title="copy_to_clipboard" width="300" height="28" class="aligncenter size-medium wp-image-466" />][4]

Lamentablemente el código del repositorio del creador no se encuentra actualizado para funcionar con las últimas versiones de sus dependencias (haXe y swfmill), pero entre los pull request ya se encuentra la solución, a la cual ya hice &#8220;merge&#8221; y puse a la disposición en este repositorio (ya también con el botón traducido a español por cierto): 

**Repositorio:** <https://github.com/guerrerocarlos/clippy>  
**En .zip:** [Descargar][5]

Al descargar el código, se puede copiar directamente el archivo **clippy.swf** a su carpeta pública y solo faltaría incluir el siguiente objeto HTML en el lugar donde quieras que vaya el botón, además de reemplazar la etiqueta {text} por el texto que quieres que se copie a la portapapeles al presionar el botón, y {bgcolor} por el color de fondo que quieres que tenga el botón.

 [1]: http://haxe.org/
 [2]: http://swfmill.org/doc/using-swfmill.html
 [3]: http://blog.carlosguerrero.com/wp-content/uploads/2012/08/Copiar.png
 [4]: http://blog.carlosguerrero.com/wp-content/uploads/2012/08/copy_to_clipboard.png
 [5]: https://github.com/guerrerocarlos/clippy/zipball/master