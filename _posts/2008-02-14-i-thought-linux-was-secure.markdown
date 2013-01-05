---
comments: true
date: 2008-02-14 16:42:12
layout: post
slug: i-thought-linux-was-secure
title: I thought Linux was secure
wordpress_id: 49
categories:
- Seguridad
---

No sé si el comentario [_I thought Linux was secure](http://www.theregister.co.uk/2008/02/14/claranet_linux_security_hole/comments/#c_155656_), tomado aisladamente, es inocente, o provocador.  
Pero deben haber usuarios que se sorprenderán al darse cuenta que linux sí puede ser atacado seriamente, y la seguridad se puede comprometer.

Lo que pasó es que [un grupo de crackers británico](http://www.theregister.co.uk/2008/02/14/claranet_linux_security_hole/) usaron el exploit [vmsplice](http://www.lnds.net/2008/02/vmsplice_exploit_para_acceder_a_la_cuent.htmlpara) ganar el acceso a la cuenta root en varios servidores de Claranet, en Gran Bretaña.

En realidad es bien sencillo, seguramente muchas personas tienen acceso a un servidor compartido (shared hosting), y desde sus cuentas ejecutan el código y ganan los privilegios de root.

Este es un esquema, de los muchos posibles, para usar este exploit.

Lo mismo se debe estar repitiendo en muchas partes, y vamos a tener varias noticias parecidas en las próximas semanas.

El problema es que aunque el parche es trivial, y fácil de instalar los procedimientos, y los recursos no siempre están para poder responder a tiempo, y ese lapso es el que es usado por los vándalos.

Por supuesto, veremos tontas guerras entre los linuxeros y los usuarios windows sobre que sistema es más seguro.

De todas maneras, Linux tiene un tiempo de respuesta y corrección de este tipo de fallas cási instantáneo, si esto pasara en Windows o en MAc OS, primero tendríamos un mes en que se negaría el problema, otro mes de silencio, y varios meses más para obtener una respuesta.

Pero a pesar de ese tremendo tiempo de respuesta de la comunidad linux para resolver un problema serio, se tropieza con la capacidad de respuesta, que tiene una inercia, y esta inercia la que es usada por los que quieren hacer daño.

De todas maneras, aunque se haya aplicado el parche, ¿se puede estar seguro de que el computador no fue atacado antes, y ya hay un malware o alguna cuenta extraña creada? Así que no basta con aplicar el parche, hay que auditar el sistema, son horas extras de los operadores y administradores de sistema, plata, plata, plata....

La seguridad no consiste sólo en instalar parches y tener los firewalls al máximo...



