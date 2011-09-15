---
layout: post
title: Modificación del entorno de aplicaciones gráficas
---

Cuando queremos cambiar las variables de entorno de un proceso que se ejecuta en la shell, tenemos claro que fichero(s) modificar y como hacerlo. Pero... sabes como hay que hacer para modificar el entorno de aplicaciones que no se lanzan desde la línea de comandos?


![Editor de listas de propiedades](http://www.principia.info/assets/2007/3/5/environment_property_list.png)

Pues es bastante sencillo. Solo hay que crear (si no existe) un fichero llamado `environment.plist` en un subdirectorio de tu directorio inicial llamado `.MacOSX` (ojo al punto). Es decir, `~/.MacOSX/environment.plist`. Esto lo podemos hacer con el editor de listas de propiedades, o bien desde la línea de comandos:

    defaults write ~/.MacOSX/environment FOO -string bar

La opción `-string` no es estrictamente necesaria, pero si vamos a pasar valores susceptibles de ser interpretados de otro modo, es mejor ponerla.
Si quisiéramos eliminar una de las variables, simplemente sería:

    defaults delete ~/.MacOSX/environment FOO

Una vez modificado este fichero, la próxima vez que iniciemos sesión, estas variables tendrán asignado el valor que hayamos especificado. Una de las maneras que podemos comprobarlo es usando el comando `set` desde la propia línea de comandos, dentro de **Terminal.app** (dentro de **xterm**, o con una sesión SSH no funcionaría).
