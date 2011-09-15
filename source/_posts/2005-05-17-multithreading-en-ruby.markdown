---
layout: post
title: Multithreading en Ruby
---

Hace unos dias, necesit&#233; la posibilidad de ejecutar varias peticiones a los servicios web de Amazon en paralelo, debido a que hacerlo secuencialmente hubiese consumido demasiado tiempo, y los usuarios &#250;ltimos, que esperan los resultados tras hacer una petici&#243;n web, se hubiesen impacientado.
As&#237; que resolv&#237; averiguar si Ruby me permitir&#237;a hacer las diferentes peticiones en paralelo sin complicarme mucho la vida -tengo los temas de concurrencia y regiones cr&#237;ticas algo oxidados.
Para mi sorpresa, result&#243; mucho m&#225;s f&#225;cil de lo que me esperaba:

<code lang="ruby">
    def AmazonHelper.find_isbn(isbn)
        reqs=[]
        ['us', 'uk', 'de', 'fr', 'ca' ,'jp'].each do |loc|
          reqs.push Thread.new { Request.new(DEV_TOKEN, ASSOCIATES_ID,loc).asin_search(isbn) }
        end
        response = reqs.collect { |req| req.value rescue nil }
        response.compact![0].products[0]
    end
</code>

Como se puede ver, itero sobre una lista de `locales` y para cada una de ellas creo un nuevo Thread, que guardo en un array (en realidad, lo que guardo es el resultado, como veremos enseguida). El constructor del *thread* recibe un bloque de c&#243;digo, que es lo que debe ejecutar el mismo *thread*. El resultado de la ejecuci&#243;n de este c&#243;digo, siguiendo las convenciones de Ruby, es lo que se devuelve al c&#243;digo llamante, por lo que acaba en el array reqs, una vez hayan finalizado todos los *threads*.
A continuaci&#243;n, para cada resultado de ejecuci&#243;n -para cada *thread* finalizado- le pedimos su valor, que viene a ser el resultado de la petici&#243;n al web service de Amazon. Puede ser que la petici&#243;n haya fallado, en cuyo caso obtendremos `nil`. Entonces, compactamos el array, para eliminar estos `nils`, y obtenemos como resultado un array con todas aquellas respuestas v&#225;lidas.
