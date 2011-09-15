---
layout: post
title: Ya tenemos los nightlies de WebKit para Windows
---

Solo hay que ir a buscarlos a [http://nightly.webkit.org/](http://nightly.webkit.org/builds/win/1).

Para ejecutarlo, descargar el archivo y descomprimirlo en alguna parte (no hace falta machacar la instalación estable de Safari). Entonces, hacemos doble clic sobre el fichero de comandos que encontraremos, y este ya se encarga de lanzar el Safari del sistema pero indicándole que debe usar las DLL del directorio desde donde lo lanzamos. Por que los nightlies de WebKit son básicamente esto, solo el motor de renderizado y deben usar la aplicación Safari ya preinstalada para que los contenga.

De momento, parece que los favoritos ya funcionan sin el hack que comenté ayer...

Para los más aventureros, podemos descargar el código fuente desde SVN y compilarlo nosotros mismos. Las instrucciones, en [http://webkit.org/building/tools.html](http://webkit.org/building/tools.html). Como se ve, con el compilador gratuito Visual C++ Express de Microsoft es suficiente, no hace falta el full monty que es Visual Studio.
