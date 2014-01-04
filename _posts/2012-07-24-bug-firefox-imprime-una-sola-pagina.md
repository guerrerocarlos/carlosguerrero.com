---
title: 'Bug Firefox: imprime una sola pagina'
author: guerrerocarlos
layout: post
permalink: /bug-firefox-imprime-una-sola-pagina/
categories:
  - Internet
---
Si has intentado imprimir una pagina web completa y el navegador está mandando a la impresora solo la primera pagina y olvidandose por completo del resto, no es un problema de código sino de Firefox como tal. Siendo de hecho un problema que tiene mucho tiempo en firefox, pero como no es recurrente sino que sucede es con ciertas paginas o códigos HTML determinados, no ha sido solucionado.

Para solucionarlo tú mismo, solo debes poner &#8220;overflow:visible;&#8221; en los contenedores donde se encuentra lo que debes imprimir.

En mi caso bastó con agregar al archivo donde se encuentran los CSS lo siguiente:

> #oe {  
> overflow:visible;  
> }
> 
> .pos-sale-ticket{  
> overflow:visible;  
> }

Y caso solucionado.