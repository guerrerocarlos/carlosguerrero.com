---
title: Paypal con Python
author: guerrerocarlos
layout: post
permalink: /paypal-con-python/
categories:
  - Internet
  - Linux
---
Después de pasar muchos días e incluso semanas tratando de descifrar como hacer funcionar el pago con Paypal en sitios hechos con Python (Django en mi caso) examinando el código de repositorios como [django-paypal][1] sin ningún éxito.

Finalmente logré realizarlo, pero tuve que crear mi propia función, basándome en lo que sale en la críptica documentación actual de Paypal:  


En el lado de Paypal debes modificar la siguiente configuración, entrar en &#8220;Preferencias del sitio Web&#8221;:

[<img class="aligncenter" title="Entrar en Preferencias del sitio Web" src="http://blog.carlosguerrero.com/wp-content/uploads/2012/11/Entrar-Aqui-300x182.png" alt="" width="300" height="182" />][2]

Y activar &#8220;Transferencia de datos de pago&#8221; para luego copiar el campo &#8220;Código personal de identidad&#8221; que servira para el mecanismo de pago que se va a implementar con Django.

[<img class="aligncenter size-medium wp-image-531" title="Copiar este codigo" src="http://blog.carlosguerrero.com/wp-content/uploads/2012/11/Copiar-este-codigo1-300x158.png" alt="" width="300" height="158" />][3]

Una vez guardada esta configuración en el sitio de Paypal. Se puede aprovechar para crear un botón de pago, en el cual se especifica cual será la URL a la que se debe devolver al usuario justo despues de que se logra el pago con Paypal, en &#8220;3: Customize advanced features&#8221; de la siguiente manera:

[<img class="aligncenter" title="BotonNuevo" src="http://blog.carlosguerrero.com/wp-content/uploads/2012/11/BotonNuevo1-300x234.png" alt="" width="300" height="234" />][4]

Una vez se ha puesto el botón en la pagina web, al usarlo, se redirigirá al cliente a la URL que hayamos especificado para ese botón, por lo cual debemos tener esa URL especificada en nuestro urls.py y con una funcion correspondiente en la cual usaremos la funcion paypal_check de la siguiente manera:

> success , info = paypal_check(request.GET['tx'],&#8217;<Código personal de identidad>&#8217;)  
> if success:  
> #Código donde se procesa el pago, recibiendo toda la información que paypal te da en la variable info

Cuando Paypal te redirecciona, envia un campo GET con el nombre &#8216;tx&#8217;, con él y tu codigo personal de identidad, paypal_check realiza un request a paypal verificando si realmente es un pago que acaba de realizarse y fue exitoso. De ser así, se obtiene &#8216;SUCCESS&#8217; y una serie de campos adicionales muy utiles:

**info** contiene: {&#8216;protection\_eligibility&#8217;: &#8216;Ineligible&#8217;, &#8216;last\_name&#8217;: &#8216;Guerrero&#8217;, &#8216;txn\_id&#8217;: &#8217;8YG081780W&#8217;, &#8216;store\_id&#8217;: &#8221;, &#8216;shipping\_discount&#8217;: &#8217;0.00&#8242;, &#8216;receiver\_email&#8217;: &#8216;guerrerocarlos%40gmail.com&#8217;, &#8216;payment\_status&#8217;: &#8216;Completed&#8217;, &#8216;payment\_gross&#8217;: &#8217;5.00&#8242;, &#8216;terminal\_id&#8217;: &#8221;, &#8216;tax&#8217;: &#8217;0.00&#8242;, &#8216;residence\_country&#8217;: &#8216;VE&#8217;, &#8216;payer\_status&#8217;: &#8216;verified&#8217;, &#8216;txn\_type&#8217;: &#8216;web\_accept&#8217;, &#8216;pos\_transaction\_type&#8217;: &#8221;, &#8216;handling\_amount&#8217;: &#8217;0.00&#8242;, &#8216;shipping\_method&#8217;: &#8216;Default&#8217;, &#8216;payment\_date&#8217;: &#8217;19%3A44%3A48+Sep+09%2C+2012+PDT&#8217;, &#8216;first\_name&#8217;: &#8216;Carlos&#8217;, &#8216;btn\_id&#8217;: &#8217;50793&#8242;, &#8216;item\_name&#8217;: &#8217;1+Month&#8217;, &#8216;charset&#8217;: &#8216;windows-1252&#8242;, &#8216;receipt\_reference\_number&#8217;: &#8221;, &#8216;custom&#8217;: &#8221;, &#8216;transaction\_subject&#8217;: &#8217;1+Month&#8217;, &#8216;item\_number&#8217;: &#8217;1M&#8217;, &#8216;receiver\_id&#8217;: &#8216;YPQJZFV6U4U&#8217;, &#8216;business&#8217;: &#8216;guerrerocarlos%40gmail.com&#8217;, &#8216;payer\_business\_name&#8217;: &#8216;Other&#8217;, &#8216;payer\_id&#8217;: &#8216;A6E56SJCUQ&#8217;, &#8216;discount&#8217;: &#8217;0.00&#8242;, &#8216;num\_offers&#8217;: &#8217;0&#8242;, &#8216;payment\_fee&#8217;: &#8217;0.57&#8242;, &#8216;insurance\_amount&#8217;: &#8217;0.00&#8242;, &#8216;mc\_fee&#8217;: &#8217;0.57&#8242;, &#8216;mc\_currency&#8217;: &#8216;USD&#8217;, &#8216;shipping&#8217;: &#8217;0.00&#8242;, &#8216;payer\_email&#8217;: &#8216;client%40carlosguerrero.com&#8217;, &#8216;payment\_type&#8217;: &#8216;instant&#8217;, &#8216;mc_gross&#8217;: &#8217;5.00&#8242;, &#8216;quantity&#8217;: &#8217;1&#8242;}

Ya con eso se tiene toda la informacion necesaria para procesar el pago del cliente, guardar su correo, el monto de su pago e incluso darle de una vez el producto que compró, si es entregable por vía digital.

Espero les sirva, cualquier pregunta estoy a la orden [@guerrerocarlos][5]

&nbsp;

 [1]: https://github.com/johnboxall/django-paypal
 [2]: http://blog.carlosguerrero.com/wp-content/uploads/2012/11/Entrar-Aqui.png
 [3]: http://blog.carlosguerrero.com/wp-content/uploads/2012/11/Copiar-este-codigo1.png
 [4]: http://blog.carlosguerrero.com/wp-content/uploads/2012/11/BotonNuevo1.png
 [5]: http://twitter.com/guerrerocarlos