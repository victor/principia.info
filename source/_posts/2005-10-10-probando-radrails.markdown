---
layout: post
title: Probando RadRails
---

Recientemente ha hecho mucho ruido en el entorno de Ruby on Rails la aparición de un IDE enfocado al desarrollo de aplicaciones con el mencionado framework llamado [RadRails](http://www.radrails.org/).

He estado probando las dos primeras releases, con el objeto de que la adopten un par de compañeros que no tienen la suerte de poder utilizar TextMate (o yo mismo, en el trabajo) y he aqui mis conclusiones preliminares:

* Para empezar, no nos llevemos a engaño. No es nada más que una distro de Eclipse recortada para tener lo esencial para el desarrollo con Ruby (incluyendo la recién liberada versión 0.6.0 del [Ruby Development Tool](http://rubyeclipse.sourceforge.net/)). Si ya usas Eclipse, lo único que ganas es un entorno un poco más ligero (lo cual ya es bueno de por si) aunque puede que pierdas otras herramientas en Eclipse que te pueden venir bien. Además, no tiene manera de añadir otros plugins (tal vez copiando los /jars/ directamente al directorio? Pero nada de /update sites/, eso seguro. Bueno, si, si añadimos el update site de radrails a Eclipse, tendremos toda la funcionalidad de Eclipse en radrails. Pero, que ganamos con eso, exactamente? Supongo que la comodidad de tenerlo en un solo paquete)
* Todavía le faltan algunas cosas para ser el entorno ideal. No pasa nada, es una versión 0.2 y seguro que tienen muchas ideas en el tintero todav!a. Habrá que seguir vigilándolos de cerca. Qué cosas le faltan? Pues vamos a ver: un wizard para arrancar un proyecto, que automáticamente nos configure el 'database.yml', por ejemplo. Un menú con /generators/. Mejor integración con Rake, también. Incluso un TestRunner gráfico. También una mejor integración con el debugger de rails.
* Eclipse todav!a es algo lento a la hora de editar texto - y las fuentes por defecto son pésimas -, especialmente si tiene que pintarlo de colorines.

No me he hecho muy bien de hasta que punto es más cómodo el trabajo en Eclipse -que es lo que uso bajo Windows- que en RadRails, así que le dedicaré más horas. Desde luego, mejor que Komodo (que en su [beta para OSX](http://www.activestate.com/Products/Komodo/beta.plex) soporta Rails), que funciona muy a trompicones, o [Mondrian](http://www.mondrian-ide.com/), cuya principal pega es que no soporta un proyecto con subdirectorios (algo básico para el desarrollo en Rails). En resumen, una opción interesante que habrá que seguir de cerca -y seguir probando-
