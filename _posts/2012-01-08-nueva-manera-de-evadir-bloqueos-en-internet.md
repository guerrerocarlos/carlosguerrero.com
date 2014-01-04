---
title: Nueva manera de evadir bloqueos en Internet.
author: guerrerocarlos
layout: post
permalink: /nueva-manera-de-evadir-bloqueos-en-internet/
categories:
  - Internet
  - Linux
---
<p style="text-align: left;">
  Si algunas vez intentaste entrar a <a href="http://hulu.com">hulu.com</a>, <a href="http://cbs.com">cbs.com</a>, <a href="http://abc.com">abc.com</a>, <a href="http://spotify.com/">spotify</a>, <a href="http://thewb.com/">warner brothers</a> o muchos otros como <a href="http://pandora.com">pandora.com</a> la excelente estación de radio que resulto del proyecto <a href="http://www.pandora.com/corporate/mgp">The Music Genome Project</a> y se encontraste con un muy &#8220;cordial&#8221;:
</p>

<p style="text-align: center;">
  <strong><em>&#8220;Lo sentimos pero este sitio solo esta disponible en EEUU&#8221;</em></strong>
</p>

<p style="text-align: center;">
  <a href="http://blog.carlosguerrero.com/wp-content/uploads/2012/01/Imagen-55.png"><img class="aligncenter size-medium wp-image-335" title="Bloqueo de Pandora.com" src="http://blog.carlosguerrero.com/wp-content/uploads/2012/01/Imagen-55-300x125.png" alt="" width="300" height="125" /></a>
</p>

<p style="text-align: center;">
  o cuando no pudiste <strong>ni siquiera</strong> mediante dispositivos que deberían poder hacerlo como el Roku, Xbox 360, etc:
</p>

<p style="text-align: center;">
  <a href="http://blog.carlosguerrero.com/wp-content/uploads/2012/01/20111207_235244.jpg"><img class="aligncenter size-medium wp-image-340" title="Netflix Roku Bloqueado" src="http://blog.carlosguerrero.com/wp-content/uploads/2012/01/20111207_235244-300x225.jpg" alt="" width="300" height="225" /></a>
</p>

<p style="text-align: left;">
  Quizá puedas incluso sentir de nuevo esa sensación de bloqueo, como si las fronteras del mundo real, estuviesen invadiendo los terrenos de internet, como si tu libertad fuese coartada. Que paso con aquella red de redes que yo conocí y que no tenia fronteras?
</p>

<p style="text-align: left;">
  Resulta que ese mundo en el que vivíamos (antes de la revolución del software libre) en la que el licenciamiento era la regla, y coartaba la mayoría de las libertades de los usuarios a nivel mundial, aun se encuentra presente en el mundo de la música y la TV. Y deriva en cosas como estas; sitios web que solo permiten ser usados dentro de determinado país, estableciendo fronteras geográficas dentro de un espacio que nunca ha tenido de esas.
</p>

<p style="text-align: left;">
  Pero no desesperemos, existen diferentes tecnologías que nos permiten saltar esas fronteras:
</p>

*   **Proxy**

Usando un &#8220;software proxy&#8221; podemos hacer que todo nuestro trafico sea enviado a este &#8220;servidor proxy&#8221; que pasa a ser tu &#8220;puerta de enlace&#8221; a internet. Es una solución, pero los proxys son costosos, y comparten su ancho de banda entre todos los usuarios, por lo que pueden llegar ser muy lentos, ademas de la inseguridad que resulta de que toda tu navegación sea enrutada hacia un lugar que realmente no conoces. **Es muy importante no realizar transacciones bancarias mediante proxys, a menos que sea uno de muy alta confianza.**

*   **VPN**

Una VPN es como conectarte otras computadoras en una red local dentro de tu casa o edificio, pero en la que los demás computadoras en realidad están afuera en internet, en cualquier rincón del mundo. Ya que esta es entonces una &#8220;Red Privada Virtual&#8221; tiene su propia puerta de enlace a internet, como la tendrías en tu red local, esta puerta de enlace es el servidor central de la VPN y al navegar mediante la VPN, es como si estuvieras en una LAN dentro de EEUU. Las VPN son bastante seguras, pero complicadas de instalar y configurar. **Son mucho mas seguras que un Proxy** y previenen que nadie pueda ver tu trafico, ya que esta todo encriptado, solo puede ser visto en el servidor VPN. Pero de nuevo, todo el trafico de todos los usuarios pasa por la misma puerta de enlace y aveces puede poner lenta tu conexión.

<p style="text-align: center;">
  <strong>Cansado de estas limitaciones, problemas de ancho de banda y fallas de seguridad, decidi hacer algo al respecto:</strong>
</p>

*   ****[**ProxyDNS**][1]

Es como un hibrido entre un DNS y un Proxy, pero no tienes que instalar ningún software, sino simplemente configurar la dirección ip del ProxyDNS como tu DNS (74.207.242.213), y navegar como siempre lo has hecho. La unica diferencia sera que cuando intentes acceder a paginas bloqueadas o que no podrías acceder por estar afuera de EEUU, el DNS se encarga de redirigirte a un Servidor Proxy en la nube, configurado para que puedas ver esa pagina sin ninguna restricción en absoluto, tan facil y transparente que ni te das cuenta cuando sucede. Al DNS no entrometerse en todo tu trafico, hace que **sigas navegando sin afectar tu velocidad** y al estar en la nube, tiene **ancho de banda mas que suficiente** para todas las personas que usen el &#8220;Cloud-based Proxy&#8221;. Y **sin preocuparte por tu seguridad** ya que tu trafico en su mayoría sigue siendo direccionado como lo haría cualquier otro DNS. Funciona ademas en Linux, Mac o Windows sin ningún problema.

Sitio web oficial: <http://proxydns.co/>  
Yo lo estoy usando actualmente y me funciona de maravilla, ya no necesito la TV por cable en absoluto <img src='http://blog.carlosguerrero.com/wp-includes/images/smilies/icon_smile.gif' alt=':)' class='wp-smiley' /> veo los programas y películas que quiero, en el momento que quiero y mucho mas pronto que lo que llegan a la tv por cable en el país en que me encuentro. (De lo contrario el [Roku][2] habría sido una total perdida de dinero.) Aun estoy haciendo las pruebas con amigos que tienen Xbox 360 y equipos similares, espero sus comentarios!

<p style="text-align: center;">
  <img class="alignnone" title="cbs.com" src="http://dl.dropbox.com/u/5864262/proxydns/cbs.png" alt="" width="600" height="323" />
</p>

<p style="text-align: center;">
  <img class="alignnone" title="hulu.com" src="http://dl.dropbox.com/u/5864262/proxydns/hulu.png" alt="" width="600" height="369" />
</p>

<img class="alignnone aligncenter" title="Bing Bang Theory" src="http://dl.dropbox.com/u/5864262/proxydns/bingbangtheory2.png" alt="" width="500" height="323" />

Y el Roku funcionando de maravillas:

[<img class="aligncenter size-medium wp-image-333" title="Pandora.com en Roku, fuera de Estados Unidos" src="http://blog.carlosguerrero.com/wp-content/uploads/2012/01/IMG-20120108-00314-300x225.jpg" alt="" width="300" height="225" />][3]

[<img class="aligncenter size-medium wp-image-334" title="Crackle en Roku sin bloqueo fuera de Estados Unidos" src="http://blog.carlosguerrero.com/wp-content/uploads/2012/01/IMG-20120108-00315-300x225.jpg" alt="" width="300" height="225" />][4]

Espero que les sirva a ustedes también!

&nbsp;

&nbsp;

 [1]: http://proxydns.co
 [2]: http://roku.com/
 [3]: http://blog.carlosguerrero.com/wp-content/uploads/2012/01/IMG-20120108-00314.jpg
 [4]: http://blog.carlosguerrero.com/wp-content/uploads/2012/01/IMG-20120108-00315.jpg