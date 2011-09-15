---
layout: post
title: Google presenta su servicio de hospedaje de aplicaciones
---

A remolque de Amazon y sus webservices, Google presentó ayer el [Google App Engine](http://code.google.com/appengine/), un servicio integrado de hosting de aplicaciones donde cualquiera (bueno, de momento los 10,000 primeros desarrolladores que se den de alta) puede ejecutar sus aplicaciones a través de un entorno de ejecución virtual.

De momento, parece ser que la API inicial de trabajo es Python, aunque se prevé que en el futuro cualquier lenguaje (o los más comunes) estará soportado. Al contrario que Amazon, que ofrece sus servicios bastante desacoplados, aquí la integración (por lo primero que he podido leer) es más fuerte. Se pueden usar el gfs ([Google filesystem](http://en.wikipedia.org/wiki/Google_File_System)) y [BigTable](http://en.wikipedia.org/wiki/BigTable), sistemas nacidos en google para gestionar de manera distribuida el espacio en disco y el acceso a datos.

Parece que la tónica en cuanto a aplicaciones escalables va a ser esta clase de servicios, y los servicios de hosting tradicionales se quedarán para aplicaciones "legacy" (entendiendo como legacy todo lo que existe hasta dia de hoy) o hobbystas que se lo quieran currar ellos solos. Las facilidades y la alta disponibilidad que ofrecerán frente a los entornos tradicionales harán que estos sean no desbancados, pero si relegados a un segundo lugar.

Eso si, todos estos servicios -por el momento- utilizan entornos abiertos (o sea, linux). Me pregunto cual es la estrategia de Microsoft en este sentido, ya que montar entornos de estas caracterísitcas en plataformas windows, será un poco más complicado, no ya por cuestiones técnicas (estoy seguro que los de VMWare tienen el know-how) si no por licencias. Me aventuro a decir que, si sale una plataforma de hosting de aplicaciones que entienda de .NET, será sobre Mono antes que sobre Windows tradicional.
