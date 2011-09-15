---
layout: post
title: Subversion (II)
---

Creación de un Repositorio

Para crear un repositorio, escogeremos un directorio en el que situar los archivos de datos correspondientes.

Normalmente en UNIX, se usa un directorio dentro de <code>/usr/local/svn</code>, aunque esto depende especialmente del sabor de UNIX que estemos utilizando. Para crearlo utilizamos el comando <code>svnadmin</code>:

<code lang="shell">
svnadmin create /usr/local/svn/ejemplo
</code>

Esto creará un repositorio llamado ejemplo en el directorio <code>/usr/local/svn/ejemplo</code>. Si listamos el directorio, veremos algo como esto:

<code lang="shell">
ls /usr/local/svn/ejemplo
</code>

En realidad, como podemos ver, lo que se ha creado es una estructura de directorios que auxiliarán a la BBDD Berkeley cuando hagamos transacciones con el código. En principio, no tenemos que tocar nada de estos directorios, ya que es el servicio svn el que se encarga de hacer las gestiones oportunas por nosotros.

Uno de los pocos directorios en que podemos hacer algo es el directorio <code>hooks</code>. Este directorio está pensado para albergar una serie de scripts que se ejecutarán al suceder determinados eventos, como por ejemplo al tratar de acceder al repositorio o cuando se acaba de <strong>cometer</strong> un cambio en el mismo. Pero ya lo detallaré más adelante.

Una vez creado el directorio, es interesante poner algo de código en él. La estructura recomendada, y la que se sigue por convención, es tener 3 directorios en la raíz del proyecto:


    +-branches
    +-trunk
    \-tags


La idea es que la rama principal de código, se sitúa en el directorio <code>trunk</code>. Las ramas experimentales, en <code>branches</code>. Y el código que se libera en una versión determinada (y, en principio, inmutable) va en el directorio <code>tags</code>.

Por tanto, para empezar un proyecto, lo crearíamos dentro del directorio <code>trunk</code> (o bien branches, si no es funcional aún). Para ello, suponiendo que tengamos ya un código creado, nos situaríamos en la raíz de nuestro proyecto, y para subir este código inicial, efectuaríamos un <strong>import</strong>:

<code lang="shell">
cd ~/devel/proyecto
svn import  file:///usr/local/svn/ejemplo .
</code>

Aquí ya hay un punto donde debemos fijar nuestra atención, que es la URL del repositorio. A excepción de operaciones de mantenimiento como <code>svnadmin create</code> o <code>recover</code>, la mayoría de ordenes se ejecutan contra un repositorio, que especificamos mediante una URL. Si bien esta URL puede ser local, en muchos casos (especialmente si desarrollamos con un equipo distribuido geográficamente) será una URL de internet, cuyo esquema será http:// (o https://)
