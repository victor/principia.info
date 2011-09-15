---
layout: post
title: Como paliar la inestabilidad de Safari 3 para Windows
---

El problema reside, en parte, en como Apple implementa la I18N i la L10N de recursos. En OS X, los recursos que utiliza una aplicación, como imágenes, ficheros NIB y cadenas de texto, que son susceptibles de ser internacionalizados, se hallan en una carpeta de la aplicación llamada Resources, clasificados segun el idioma para el que están destinados en carpetas llamadas, por ejemplo, `en.lproj` o `English.lproj` para recursos en inglés, que es el idioma utilizado por defecto.

En Windows, sucede lo mismo. Si abrís la carpeta de aplicación de Quicktime, por ejemplo, o de iTunes, veréis que existen los recursos correspondientes al lenguaje español.

Sin embargo, la beta de Safari no los tiene. Y ahí radica el problema, en que Safari trata de acceder a los recursos correspondientes al idioma que estamos utilizando en Windows, y al no encontrarlos, o bien peta, como en el caso del menú de favoritos, o bien no carga el plugin de flash correctamente.

Lo primero que se me ha ocurrido, es duplicar las carpetas `en.lproj` esparcidas en la carpeta de Safari, y duplicarlas con el nombre de `es.lproj` (y `Spanish.lproj`). Este es el mecanismo que se utiliza normalmente al proceder a la localización de una aplicación a un idioma determinado: partes de la versión en inglés y vas traduciendo. De esta manera puedes ir probando la aplicación parcialmente traducida hasta que esté toda.

Pues bien, esto no ha funcionado. Lo que si que ha funcionado, es ir al panel de control de windows, e indicarle que el idioma deseado por defecto para las aplicaciones es el inglés (de Estados Unidos, aunque sospecho que cualquier inglés serviría). A continuación, he lanzado Safari y... presto! Ahi estaba el menu de favoritos, el de sitios Bonjour, y podía acceder con normalidad al contenido en flash.

De momento, el problema de los textos que desaparecen, sigue presente. Este problema, por lo que he visto en diversos blogs, también les sucede a los usuarios angloparlantes, así que no creo que esté tan relacionado.

Es posible que modificando adecuadamente los recursos en `es.lproj`, la aplicación funcione sin necesidad de poner el sistema en inglés. Pero no conozco tan bien como hacer esto en Windows, ya que no es algo que esté precisamente documentado, al ser Apple los únicos que portan sus aplicaciones a Windows utilizando sus herramientas de desarrollo.

<ins>*Update* Umm... después de hacer esto que he dicho, he vuelto a poner el sistema en español (y sin quitar las carpetas `es.lproj`), y los favoritos funcionaban pero el plugin de flash, por el contrario, no... conclusión? hay que seguir investigando...</ins>
