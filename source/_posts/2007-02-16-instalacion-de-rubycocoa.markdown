---
layout: post
title: Instalación de RubyCocoa
---

Como el primer ejercicio del libro -en el capítulo 2- consiste simplemente en seguir las instrucciones y construir una sencillita aplicación, voy a empezar haciendo ese mismo ejercicio con Ruby. Para ello, es necesario tener instalado el *bridge* [RubyCocoa](http://rubycocoa.sourceforge.net/doc/), así que lo primero de todo es instalárselo.

Yo utilizo el ruby que viene con los [MacPorts](http://www.macports.org/) (antiguamente llamados DarwinPorts), así que el binario que puede descargarse desde el site de RubyCocoa no me sirve, ya que es para el ruby que viene instalado por defecto con Mac OS X Tiger. Si ese fuera tu caso, simplemente descárgate ese binario, pero ten en cuenta que la versión de ruby instalada por Apple tiene un bug.

Instalar el bridge desde Mac Ports es tan sencillo como:

    sudo port install rb-cocoa

El sistema de ports descargará e instalará entonces la versión más reciente del bridge. Si apareciese un mensaje como:

>Error: Target com.apple.activate returned: Image error: /Developer/Documentation/RubyCocoa/build.en.html already exists and does not belong to a registered port.  Unable to activate port rb-cocoa.

significa que ya teníamos el paquete instalado para el ruby de Apple y al tratar de instalarlo se encuentra que algunos ficheros ya existen (los ejecutables y librerías se instalan en sitios diferentes, pero la documentación y las plantillas para Xcode van en el mismo sitio y, por tanto, hay conflicto). En ese caso, simplemente tendríamos que usar el siguiente comando para activar el port:

    sudo port -f activate rb-cocoa

Para comprobar que funciona, invocaremos el intérprete interactivo:

    $ irb
    irb(main):001:0> require 'osx/cocoa'
    => true


