---
comments: true
date: 2006-03-04 12:14:25
layout: post
slug: email-de-ricardo-galli
title: Email de Ricardo Galli
wordpress_id: 1357
categories:
- Sin categoría
---

Me ha llegado este email de Ricardo Galli.
Juzguen ustedes.

-----Mensaje original-----
De: Ricardo Galli [-- borrado --]
Enviado el: Saturday, March 04, 2006 10:16 AM
Para: -- borrado --
Asunto: Problemas de seguridad en Blogmemes

Hola Eduardo,
veo que en blogmemes cada vez dedican palabras más "agradables" contra mí. En especial con el tema del ataque al menéame, donde no se han cortado un pelo.

Pues bien, perdí 15 minutos para ver el código del Blogmemes (versión
0.4.2.21) y me encontré con problemas y bugs de seguridad muy graves (muchos más de los que tenía el menéame). Sobre todo de inyección de SQL por la falta de verificación de los variables del GET o POST.

Por ejemplo en profile_edit.php
if ($bm_users->update_profile($_POST))
que llama a:
function update_profile($data)
{
$sql = ' update users set ';
$sql .= ' email = \''.$data['email'].'\',';
$sql .= ' fullname= \''.$data['fullname'].'\',';
$sql .= ' website = \''.$data['website'].'\',';
$sql .= ' blog = \''.$data['blog'].'\' ';
$sql .= ' where ID = '.$data['user_id'];
$this->db->execute($sql);

o en memes.php
function do_login($user, $pass)
{
$user = $this->db->fetch_object("select ID, username, password, email,join_date,admin,website,blog,fullname from users where
lower(username)='".strtolower($user)."'")

Así está plagado de este tipo de errores, en ningún momento sanitizas o controlas esas variables y luego las usas directamente para crear el sql.
Podría haberte modificado la base de datos, o cambiar las claves con métodos de inyección muchos más sencillos de los que han usado para el menéame (ni siquiera hace falta que los sepa, me basta con "copiar" los que han usado contra el menéame).

Además tengo la impresión que tienes que tener el "register global variables"
en el php del servidor. Espero que no sea así, porque sino el problema es aún más grave.

Supongo que ya te servirá de ejemplo para darte cuenta de los problemas.
Aunque estoy muy mosqueado por cómo me han tratado en Blogmemes sin que venga a cuento, no publicaré estos problemas ni este mensaje. Al menos no por ahora, pero es urgente que lo arregles, si han probado con el Menéame, en poco tiempo lo harán con Blogmemes, hay gente cabreada de ambos "lados".

Pero espero que lo soluciones y pongas un artículo en blogmemes de los problemas resueltos y _quién_ y _cómo_ te ha informado.

Si necesitas más ayuda para solucinarlos, encantado (aunque tendría que estudiarme el Smarty, que no lo conozco), pero antes espero ver una respuesta pública de "desagravio", que las contrarias ya hubo demasiadas.

Un abrazo.

--
ricardo galli GPG id C8114D34
http://mnm.uib.es/gallir/
