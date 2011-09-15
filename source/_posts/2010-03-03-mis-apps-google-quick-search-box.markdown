---
layout: post
title: "Mis Apps: Google Quick Search Box"
---

Hace tiempo, salió un lanzador de aplicaciones revolucionario para la época, QuickSilver. Un lanzador de aplicaciones es una utilidad que nos permite iniciar otras aplicaciones fácilmente, sin necesidad de ir navegando por `/Applicaciones` ni sobrecargar el *Dock* con iconos de aplicaciones que usamos esporádicamente.

QuickSilver estuvo en una perpetua beta, y tenía tantas funcionalidades y plugins que resultaba difícil sacarle todo el partido. Durante mucho tiempo no hubo releases nuevas, y a pesar de estar disponible el código fuente, el propio desarrollador advertía que era un poco ofuscado. Con lo cual, los usuarios de QuickSilver estaban en un estado más o menos precario, en especial al actualizar a Snow Leopard.

Pues bien, el desarrollador de QuickSilver [pasó a trabajar para Google](http://arstechnica.com/apple/news/2009/01/quicksilvers-jitkoff-moves-on-to-google-quick-search-box.ars). Y el proyecto en el que trabaja es el heredero de QuickSilver, [Quick Search Box](http://www.google.com/quicksearchbox/). Quick Search Box es una evolución de QuickSilver, mucho más sencilla y más estable pero igualmente potente.

![screenshot de QSB](http://principia.info/assets/2010/3/3/qsb.png)

Y como funciona QSB? pues lo primero, es invocarlo. Cuando QSB está funcionando, normalmente no aparece su icono en el Dock (es una opción, pero la más habitual). Lo que tenemos que hacer es pulsar ⌘+⌘ (o bien ⌃-espacio) y aparece una caja de texto en el centro de la pantalla.

A partir de aquí, las posibilidades se multiplican. QSB está esperando que le introduzcamos un texto, y a medida que vamos tecleando irá ofreciendo posibilidades mostrándonos objetos del sistema o acciones que podamos hacer con ese texto.

Por ejemplo, si queremos hacer un cálculo rápido y no queremos esperar a que se lance la calculadora, podemos invocar QSB e introducir una fórmula sencillita: `20*0.76`. QSB nos ofrecerá un menú de opciones, con el resultado de la operación como primera opción, y a continuación otras opciones. La primera opción, si la seleccionamos, nos abrirá la calculadora. Otras opciones que nos pueden salir - según como hayamos configurado QSB- son buscar ese texto en Google, utilizarlo directamente como URL, o bien, si existe algún fichero en el sistema cuyo nombre coincida con lo introducido, abrir ese fichero. Algunas acciones, como la última que he mencionado, pueden tener diferentes variaciones: cuando QSB determina que nos estamos refiriendo al nombre de un fichero, si pulsamos TAB en lugar de Return para confirmar la selección, navegaremos a un submenú donde nos aparecen varias opciones más: abrir el fichero, abrir el directorio que contiene ese fichero en el Finder, moverlo a la papelera, obtener información...

QSB utiliza Spotlight para encontrar ficheros, documentos, correo, etc. que pueda estar relacionado con el texto introducido. Luego, las opciones posibles dependerán del tipo de objeto seleccionado: enviar por correo, mostrar texto en letras grandes, y así un sinfín de opciones, que podemos tunear a nuestro gusto.

Quick Search Box tiene documentación extensiva y código fuente disponible en la [página del proyecto en Google Code](http://code.google.com/p/qsb-mac/).
