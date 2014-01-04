---
title: CheatSheet para Empaquetar con git-buildpackage
author: guerrerocarlos
layout: post
permalink: /cheatsheet-para-empaquetar-con-git-buildpackage/
categories:
  - Uncategorized
---
> <pre><strong>git add .
git commit -a
git-dch --release -a --id-length=7 --full
(directorio renombrado)
cd ../nuevo-directorio/
git commit -a
git checkout upstream
git merge master
git checkout master
dh_make -r -b -c gpl -e correo@gmail.com
cd ..
(para crear las fuentes formato 1.0)
dpkg-source --format="1.0" -i.git/ -I.git -b nuevo-directorio
cd nuevo-directorio
git-buildpackage -k******* -tc --git-tag -j5</strong></pre>

*Este es el procedimiento que utilizo para empaquetar utilizando git-buildpackage, \***\**** se refiere a llave secreta, pero es opcional, se puede quitar todo el argumento -k. Probado con paquetes de lenny y squeeze.*