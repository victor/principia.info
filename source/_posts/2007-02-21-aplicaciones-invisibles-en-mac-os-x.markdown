---
layout: post
title: Aplicaciones invisibles en Mac OS X
---

Cuando yo empezaba en esto de la informática, algunos juegos tenían una tecla de pánico (o tecla *boss*) que ocultaba lo que estabas haciendo y te mostraba una pantalla ficticia de una aplicación de productividad (estamos hablando de cuando no había conmutación de tareas, en DOS). Hoy en día es fácil cambiar de una aplicación a otra con Cmd-Tab (o alt-tab en windows/linux), pero los iconos nos pueden traicionar todavía.

Existe alguna manera en OS X de ocultar los iconos de una aplicación mientras se está ejecutando, como por ejemplo [Quinn](http://simonhaertel.de/quinn) o algún cliente P2P?

Pues resulta que si. Para hacerlo, debemos ir al Finder y buscar la aplicación. Le haremos click con el botón derecho y seleccionaremos 'Mostrar contenido del paquete'. Esto nos abrirá el directorio, normalmente oculto, donde está contenida la aplicación y sus ficheros auxiliares. Uno de ellos, `Info.plist`, es el que buscamos. Lo abriremos con la aplicación por defecto, que es el editor de propiedades, y buscaremos si existe una propiedad llamada `LSUIElement`. Si no existe, la podemos crear y darle un nuevo valor de tipo `string` y que sea `"1"` (sin las comillas).

Hecho esto, podemos guardar el fichero y la próxima vez que ejecutemos esa aplicación, no se mostrará en el dock ni cuando hagamos Cmd-Tab, o sea que hay que ir con un poco de cuidado. Si cambiamos de aplicación en primer plano y queremos volver a la aplicación oculta, puede que no nos quede otro remedio que volver a lanzarla de nuevo.

Precaución: Hay que tener en cuenta que hacer esto implica también que no podremos forzar la salida de la aplicación si fuera necesario, ni con el icono del dock (ya que no está) ni con la combinación de teclas (*Option-Command-Esc*): no nos quedará otro remedio que ir a la Terminal y matarla desde allí.

Si queremos devolver la aplicación a su modo normal, basta con volver a abrir el fichero `Info.plist` y eliminar esa propiedad.
