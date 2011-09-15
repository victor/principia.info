---
layout: post
title: Nuevo RubyCocoa 0.11.0
---

<ins>*Update* El dia 4 de Junio Laurent anuncia la aparición de la release 0.11.1, básicamente corrigiendo algunos bugs pero también introduciendo nuevas capacidades, como algunos atajos a la hora de puentear Ruby y Obj-C, y algún nuevo ejemplo</ins>


Laurent Sansonetti, el *Release Manager* de RubyCocoa, anunció hace un par de dias la liberación de RubyCocoa 0.11.0 y del nuevo website donde aprender como usarlo.

Las características de la nueva versión son:

* Documentación en formato RDoc de los frameworks Cocoa soportados.
* Mejor integración con las partes en C (en contraposición a Objective-C) de Cocoa.
* Bindings para ActiveRecord. IMHO, esto es uno de los cambios más jugosos para los desarrolladores en RubyCocoa. Esto significa que podremos usar como si fuera CoreData cualquiera de los backends de ActiveRecord. 
* Se añade soporte para sobreescribir métodos de clase, y para *aliasear* métodos en Obj-C desde Ruby.
* Nueva API RBBundle, para usar RubyCocoa en un bundle.
* Nueva APi para manejar listas de propiedades, cual si fuera YAML.
* Mejor interface entre tipos básicos en Obj-C y en Ruby.
* Soporte para APIs C y Obj-C usando cadenas de formateo. No estoy muy seguro de qué significa esto.... creo que  permite interpolar variables en cadenas, y entonces usar el resultado en una llamada a código nativo.
* Mejor soporte a punteros gracias a la API ObjcPtr.
* Nueva herramienta **rb_nibtool**, que permite sincronizar ficheros nib (es decir, que contienen los objetos de una GUI) con código fuente en Ruby, tal como se hacía hasta ahora solo con Obj-C. Ya se pueden declarar *IBAction*s usando `#ib_action`
* Nueva herramienta **standalonify**, para desplegar una aplicación en Ruby con todas sus dependencias en un ejecutable normal y corriente que se puede portar a otro sistema sin RubyCocoa.
* Plantillas para Xcode que permiten hacer tests unitarios
* Soporte preliminar pra 64bit.
* Nuevos ejemplos. Va a haber que estudiarlos...


Yo, por mi parte, miraré de retomar los tutoriales de RubyCocoa cuando tenga un poco más de tiempo libre. Me quedé atascado en un punto mientras preparaba la nueva entrega, y luego ya no he podido volver a dedicar tiempo suficiente. Tal vez pueda echar un vistazo al nuevo código de ejemplo y comentarlo, pero como poco, contad que dentro de un mes ni puedo ni planteármelo... lo siento.

Mientras tanto, os dejo con una interesante [colección de videos](http://technorati.com/videos/tag/rubycocoa)... :-)

