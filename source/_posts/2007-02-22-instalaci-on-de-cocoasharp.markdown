---
layout: post
title: Instalación de CocoaSharp
---

Siguiendo con la serie de artículos que he iniciado sobre Cocoa, voy a documentar el proceso de instalación de Cocoa#.

Antes que nada, si se da el caso de que habíamos instalado el paquete de [Mono](http://www.go-mono.com) (la implementación de .NET para Unixes) con anterioridad, sería interesante desinstalarlo, para evitar conflictos:

    sudo /Library/Receipts/MonoFramework\
    -1.1.15_1.macos10.novell.ppc.pkg/Contents/Resources/uninstallMono.sh 

La localización exacta del script de desinstalación variará en función de la versión instalada. haciendo un `locate uninstallMono` veremos qué versiones hay  y donde encontrarlas (en mi caso, por ejemplo, había hasta 3 versiones diferentes del script)

 Lo siguiente es descargarnos el paquete de Mono de su site. La página de descargas está en [http://www.mono-project.com/Downloads](http://www.mono-project.com/Downloads), y naturalmente deberemos descargarnos la versión para Mac OS X. 

## Qué es Mono exactamente, y para qué lo queremos?
Pues Mono es una implementación libre de las herramientas de desarrollo - el SDK- para .NET, asi como el runtime para ejecutarlo, y está disponible en una variedad de plataformas (incluso Windows). En el caso de OS X se instala como un framework, como el de Java. Además, también viene con Cocoa#, para poder acceder al framework de Cocoa desde aplicaciones escritas con .NET.

El instalador de Mono no tiene ningún misterio: siguiente, siguiente, siguiente...

Una vez instalado el instalador, para comprobar que esté disponible podemos hacer:

    $ mcs --version
    Mono C# compiler version 1.2.3.1

Mono no instala ningún soporte específico para Xcode. Existe un plugin por ahí para ello, pero puesto que  no aporta *Intellisense*, podemos usar cualquier editor de texto (mi favorito es [TextMate](http://www.macromates.com)) para editar el código, o incluso aquellos de vosotros que uséis [Parallels](http://www.parallels.com/), Visual Studio.
