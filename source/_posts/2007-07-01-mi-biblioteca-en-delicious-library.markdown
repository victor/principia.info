---
layout: post
title: Mi biblioteca en Delicious Library
---

Hela aqui:

<a href="http://www.flickr.com/photos/vich/685694960/" title="Mi biblioteca"><img src="http://farm2.static.flickr.com/1258/685694960_210c8bd717.jpg" width="462" height="500" alt="Mi biblioteca" /></a>

No están todos los que son, pero si son todos los que están. Cuantos libros tenemos en común?

Y lo que tal vez sea más interesante para mis amados lectores... como conseguir este pantallazo con la biblioteca propia?

Pues muy sencillo. Solo hay que lanzar [F-Script Anywhere](http://www.fscript.org/), instalar su código en Delicious Library, y entonces: 

1. En el menú FSA que se ha añadido a DL, seleccionar "New F-Script Workspace"
1. Clicar en "open browser for target" y clicar en la vista de la estanteria de Delicious Library. Se nos abrirá un menu contextual mostrándonos la jerarquía de vistas que tenemos disponibles desde ese punto. Seleccionaremos CoverView, con lo que se nos abrirá un browser centrado en esa vista
1. Clicaremos el primer elemento de la primer columna (debería decir algo del tipo `<CoverView: 0x3f2ec40>` y seleccionaremos la opción **name** (asignar nombre) y le daremos un nombre a esa vista, por ejemplo, coverview.
1. Si todavia no lo hemos hecho, ahora es un buen momento para cambiar el tamaño de la ventana (y de las portadas) para que el pantallazo nos quede bien. Es interesante desplazarse por toda la vista para asegurarse que todas las portadas queden nítidas.
1. En la ventana de consola, introduciremos las siguientes líneas interactivamente:

&nbsp;

	rep := coverview bitmapImageRepForCachingDisplayInRect:coverview frame
	coverview cacheDisplayInRect:coverview frame toBitmapImageRep:rep
	data := rep representationUsingType:NSPNGFileType properties:NSDictionary dictionary
	data writeToFile:('~/Desktop/library.png' stringByExpandingTildeinPath) atomically:YES

Presto! Ya tenemos en nuestro escritorio un fichero con toda nuestra biblioteca! Naturalmente, podemos seleccionar cualquier otro nombre y directorio que queramos, tan solo hace falta modificar la última línea de código.
