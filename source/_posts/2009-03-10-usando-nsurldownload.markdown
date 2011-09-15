---
layout: post
title: Usando NSURLDownload
---

He estado un par de días peleándome con esto, así que voy a postearlo por si puede servir a alguien que se esté topando contra el mismo muro: Al tratar de usar `NSURLDownload`, obtenía siempre el mismo mensaje de error justo después de conectar con éxito con el servidor web remoto:


    cannot open file http://example.com/​file


Al final, me he dado cuenta que el directorio de destino del fichero no existía. Para crearlo, hay que hacerlo de la siguiente manera (el siguiente código funciona solo en Leopard, por cierto):


<script src="http://gist.github.com/76603.js"></script>


Lo que hace la llamada a `createDirectoryAtPath:​withIntermediateDirectories:​attributes:​error:` es crear el directorio especificado y todos los intermedios, lo cual es bastante práctico. Si el directorio ya existe dará un error, pero se puede ignorar como lo he hecho yo, pasando un `NULL` al argumento error.
