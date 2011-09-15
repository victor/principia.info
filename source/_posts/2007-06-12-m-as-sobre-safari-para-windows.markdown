---
layout: post
title: Más sobre Safari para Windows
---

Para los que todavia quieren saber más sobre Safari para windows, he aquí un par de datos interesantes:

## Nightly build de WebKit para windows
Como sabéis, el motor de rendering de Safari está basado en el proyecto Open Source [Webkit](http://webkit.org) (a su vez, basado en el motor khtml de Konqueror). Este proyecto libera cada noche la última versión recién compilada del kit, integrada en la interfaz del propio Safari, para que cualquiera pueda probarla y reportar bugs.

Bueno, pues David Hyatt (el líder del proyecto) ha anunciado en [Surfin' Safari](http://webkit.org/blog), que también habrá en breve nightlies para windows. Bien! 


## Popularización de Bonjour (Zeroconf) para Windows

Hasta ahora, y debido a la flagrante omisión de que no exista una extensión para Firefox que aporte esta funcionalidad, la única manera que había en windows de utilizar [Zeroconf](http://zeroconf.org) (conocido en el mundo Apple como Rendez-vous primero, y [Bonjour](http://apple.com/bonjout) a posteriori) para la navegación, era el plugin para Internet Explorer proporcionado por la propia Apple. Digo navegación porque iTunes utiliza este mecanismo para descubrir música compartida.

Zeroconf es un protocolo para aumentar la descubribilidad (es eso una palabra?) de servicios en la red local. Funciona mediante un mecanismo muy parecido al del DNS, pero de manera que cada host en una red ejecuta un servicio que se encarga de responder a consultas de tipo broadcast (en lugar de un solo host que responde a consultas dirigidas a ese host directamente). Zeroconf permite anunciar casi cualquier tipo de servicio en una red IP, ya sea mediante TCP o UDP, y asignarle un nombre local a nuestra red con suma facilidad.

Safari (y Camino, y Konqueror, entre otros) son capaces de descubrir servicios HTTP y HTTPS (e incluso FTP) anunciados en la red local, mediante el uso de este protocolo. Esto permite que servicios como interfaces de administración de impresoras, de routers o webcams sean utilizados desde este navegador sin necesidad de saber ni qué IP tienen asignadas. El caso de uso típico, por ejemplo, sería estar en una convención, abrir el portátil, y automáticamente descubrir la intranet del evento sin necesidad de conocer detalles como qué IP o que nombre de host utilizar.

Debido a que muy poca gente nos instalamos este plugin a propósito, y quienes nos lo instalamos somos más de usar Firefox que Explorer, el uso de Zeroconf en windows no se ha popularizado todavía. Ahora, gracias a Safari, es de esperar que más servicios se anuncien y sean utilizados que utilicen este mecanismo. O eso espero, por que la verdad es que es un mecanismo muy útil. Prometo escribir un par de tutoriales sobre como explotarlo en provecho propio (incluso a través de Internet!)
