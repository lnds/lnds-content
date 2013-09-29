---
comments: true
date: 2005-11-14 17:49:35
layout: post
slug: cripto-biometria
title: Cripto Biometria
wordpress_id: 2015
categories:
- Biometría
tags:
- biometría
- criptobiometría
- criptografía
---

La conjunción de Biometría con Criptografía ha dado un nuevo paso con la publicación del paper [Fuzzy Vault for Fingerprints](http://biometrics.cse.msu.edu/fuzzy-fingerprint-avbpa05.pdf) por U. Uludag, S. Pankanti y A. Jain. del [Michigan State University Biometrics Research Group](http://biometrics.cse.msu.edu/index.html).

Esencialmente el algoritmo oculta una llave de 128 bits en una nueva estructura, el fuzzy vault, un almacén virtual que no contiene la llave en sí, sino que los coeficientes de un polinomio, que sólo puede ser reconstruido con la adquisición de las minucias de las huellas.

El siguiente es un diagrama del algoritmo (haz click en él para verlo en detalle):





[![](http://www.lnds.net/blog/wp-content/uploads/2011/07/fuzzy-fingerprint-vault.png)](http://www.lnds.net/blog/wp-content/uploads/2011/07/fuzzy-fingerprint-vault.png)

Escribí una descripción en inglés la que se puede leer en [darksideprogramming](http://web.archive.org/web/20060616110839/http://www.darksideprogramming.net/2005/11/the_keys_in_your_fingers.html).
