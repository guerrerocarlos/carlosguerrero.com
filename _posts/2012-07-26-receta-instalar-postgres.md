---
title: 'Receta: Instalar Postgres'
author: guerrerocarlos
layout: post
permalink: /receta-instalar-postgres/
categories:
  - Linux
---
Instalar paquetes básicos de postgres:

> \# sudo aptitude install postgresql-X.X postgresql-client-X.X

Definir una contraseña al usuario *&#8216;postgres&#8217;*

> \# sudo passwd postgres

Definir contraseña para el usuario postgres dentro de postgres:

> \# sudo su postgres -c &#8220;psql template1&#8243;  
> template1=# ALTER USER postgres WITH PASSWORD &#8216;nueva_contraseña&#8217;;  
> template1=# \q

Editar el archivo **/etc/postgresql/X.X/main/postgresql.conf** y reemplazar:

> *#listen_addresses = &#8216;localhost&#8217;* ***por** listen_addresses = &#8216;*&#8217;*  
> *#password_encryption = on* **por** *password_encryption = on*

Agregar al final del archivo** /etc/postgresql/X.X/main/pg_hba.conf** para poder acceder desde *PgAdminIII*

> host    all         all         AAA.BBB.CCC.DDD/32          md5

Donde AAA.BBB.CCC.DDD es tu IP pública.

Opcional, instalar PgAdmin III:

> \# aptitude install pgadmin3

Reiniciar el servicio:

> sudo /etc/init.d/postgresql-X.X restart

Al reiniciar debe mostrar algo como

> * Restarting PostgreSQL X.X database server                              [ OK ]

De lo contrario usar [esta guia][1] para arreglar cualquier problema con los &#8216;locales&#8217;.

 [1]: http://blog.carlosguerrero.com/problemas-con-locales-en-vps-de-linode/