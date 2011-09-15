---
layout: post
title: Migrado a lighttpd
---

Desde ayer, este sitio [funciona](http://uptime.netcraft.com/up/graph?site=principia.info) sobre el servidor web lighttpd en lugar del omnipresente Apache. De hecho, para ser exactos, funciona con ambos, ya que Apache *proxyea* la conexi&#243;n y es un proceso de lighttpd aparte el que la sirve.
Como efecto secundario, y no se realmente por que, al visitarlo con Firefox en Windows, la CPU se empieza a cargar y hay que matar el proceso del navegador. Curiosamente, con la Alpha [Deer Park](http://www.mozilla.org/projects/deerpark/releases/alpha1.html) no sucede esto, asi que asumo que es un bug de Firefox (aunque bastante inconveniente, eso si), y probablemente disparado por mi script de syntax highlighting. Lo que no acabo de entender es por qu&#233; solo se dispara al ser servidor desde lighttpd... o tal vez es solo una coincidencia, quien sabe.
Adem&#225;s de eso, ya he redirigido el dominio www. principia.info para que tambi&#233;n apunte al servidor de TextDrive, con lo cual tal vez a algunos visitantes que entraban por este subdominio, de repente les aparezcam ahora todos los posts nuevos desde que migr&#233;. Tratar&#233; de redirigir tambi&#233;n los feeds antiguos hacia la direcci&#243;n de los nuevos, ya que estoy.

Y eso es todo por ahora....

*Update* Parece ser que lighhtpd no implementa la cabecera Expect, asi que los clientes .NET de XML-RPC no funcionan correctamente con &#233;l. Consecuentemente, he deshabilitado lighttpd para esta URL concreta que seguir&#225; siendo servida directamente por Apache.
