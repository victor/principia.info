---
layout: post
title: Subversion (I)
---

Subversion es un gestor de versiones de código fuente bastante potente. Tiene <span lang="en">features</span> como permitir la eliminación y renombrado de archivos (conservando la historia), integración con Apache (lo que nos permite navegar por la última versión del código y acceder al mismo desde cualquier parte), meta-datos en los archivos (como el tipo MIME, por ejemplo) o acciones configurables disparadas por eventos como el solicitar un checkout o realizar un commit.

Tanto la parte de servidor como la cliente son multiplataforma. La base de datos con la que trabaja es Berkeley DB, que es un <acronym title="sistema gestor de base de datos">SGBD</acronym> embebido (es decir, no se ejecuta como un proceso servidor si no que es una biblioteca enlazada).

La forma más completa de acceder como cliente es a través de la línea de comandos, ya que pone al alcance del usuario todas las funciones disponibles. Pero veamos primero como debemos utilizar Subversion.



# Uso de Subversion

Al contrario que otros sistemas de gestión de versiones como SourceSafe, SVN no bloquea los ficheros que un usuario pueda estar modificando. Al contrario, más de un usuario puede estar modificando los ficheros concurrentemente. Cuando llega la hora de hacer el commit, Subversion comprueba que los ficheros no hayan sido modificados por otro usuario y si es así, trata de resolver los conflictos que puedan haber, permitiendo al usuario resolverlos por si mismo en caso de duda.

La forma habitual de trabajar con Subversion es la siguiente:

1. Un usuario **crea** un repositorio (una nueva base de datos) para el código de su proyecto.

1. Entonces, hace una **importación** de su base de código existente. Puede hacerlo desde diferentes localizaciones, ya que cuando hace la importación puede especificar el destino dentro de la estructura de directorios del repositorio.

1. A partir de entonces, cualquier usuario que quiera trabajar en el proyecto, hace un **checkout** del proyecto en su área de trabajo.

1. El desarrollador edita los ficheros en su área de trabajo. Puede también **añadir** más ficheros que vaya creando, **renombrarlos**, o **eliminarlos**.

1. Cuando está satisfecho con los cambios realizados y quiere incorporarlos al repositorio, hace un **commit**. Si por el contrario quiere volver a la versión con la que empezó, efectúa un **revert**.

1. Periódicamente los usuarios **refrescarán** su copia de trabajo con la versión más actualizada que haya en el repositorio. También pueden consultar el **status** de su área de trabajo con respecto al repositorio (es decir, pueden ver que ficheros se verán afectados en el siguiente **commit**) y ver las **diferencias** particulares de cada fichero.

1. Si hay algún conflicto (que puede detectarse al consultar el **status** o al **actualizar**) Subversion alertará al usuario. Un conflicto se produce cuando otro usuario ha modificado el fichero en el que trabajamos y los cambios se solapan (si no se solapan, Subversion los integra sin problemas). Entonces, es responsabilidad del usuario que efectúa los últimos cambios el comprobar los cambios del otro usuario e integrarlos. Una vez **resueltos**, el usuario notifica de ello al servidor de Subversion para que proceda a hacer el **commit**.

1. Cuando se quiere extraer una *cata* del código (para liberar una versión por ejemplo), se puede **exportar** una instantánea del código en una revisión determinada. También podemos **etiquetar** una revisión determinada para que sirva como referencia o para explorar una **rama** de modificaciones experimentales, sin afectar a la **rama principal**

