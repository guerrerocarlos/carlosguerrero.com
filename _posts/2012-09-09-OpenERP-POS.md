---
layout: post-en
title: OpenERP Point of Sale
description: "OpenERP is usefull not only for getting companies organized, but also for using it as a selling machine"
category: articles
tags: [experience]
flickr_image:
  feature: 12356686963 
  small_feature: 12356686963 
  top: -110px 
  bottom: -130px
  small_top: -558px
---

With an initial setup of two stores (that later grew to 6) and after adapting it to local regulations (auditory tape printed daily, etc), OpenERP performed greatly after modifying some core modules, for it to work with many selling stores directly from one central instance.  

There was a problem, OpenERP POS had to to use a (COM port connected) led-display that is basic for selling machines working, and the software runs on Javascript inside the browser, wich has no access to COM ports at all. So a Javascript+WSGI_Web_Socket+COM_Port bridge was done, and the result is now here:

[OpenERP web POS connection to COM serial port for Led Display access (GITHUB)](https://github.com/guerrerocarlos/OpenERP-ledDisplay)

This is how the led-Display looks working with OpenERP POS:
{% flickr_photo 12356358963 %}
