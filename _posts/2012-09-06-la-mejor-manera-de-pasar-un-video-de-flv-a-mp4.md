---
title: La mejor manera de pasar un video de FLV a MP4 (y sin pérdida)
author: guerrerocarlos
layout: post
permalink: /la-mejor-manera-de-pasar-un-video-de-flv-a-mp4/
categories:
  - Internet
  - Linux
---
Normalmente cuando se pasa de un formato a otro con un programa tan popular como como [ffmpeg][1], se utilizan valores que vienen con el programa por defecto que obligan renderizar de nuevo el audio y el stream del vídeo, en una nueva calidad y resolución para poder obtener el video en el formato nuevo (.mp4) tardando muchos minutos en este proceso.

Afortunadamente tanto los FLV como MP4, no son mas que &#8216;[contenedores][2]&#8216; y cuyo contenido en realidad se encuentra en variedad de formatos, por ejemplo un video bajado de youtube viene normalmente con el stream de video en formato h264 y audio en AAC.

Por lo tanto, la mejor manera de pasar un .flv a .mp4 es indicandole a ffmpeg que simplemente copie todo lo que está dentro del contenedor FLV y lo ponga dentro de un contenedor MP4 de la siguiente manera:

> ffmpeg -i video.flv **-acodec copy -vcodec copy** video.mp4

Logrando con esto que la conversión dure menos de un segundo, en vez de lo que normalmente duraba (varios minutos), sin mencionar que la conversión será completamente sin pérdida.

Y si quieres pasar todos los archivos .flv de una carpeta determinada a .mp4, solo tienes que ejecutar esto en la linea de comandos:

> find /carpeta/ -name &#8216;*.flv&#8217; -exec ffmpeg -i {} -acodec copy -vcodec copy /carpeta/{}.mp4 \;

 [1]: http://ffmpeg.org/
 [2]: http://es.wikipedia.org/wiki/Formato_contenedor