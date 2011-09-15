---
layout: post
title: "CP, Capítulo 2: Generador de números aleatorios"
---

Bueno, pongámonos a ello. Tal como dije en el post anterior, hacer este ejempo con Objective-C es algo que no tiene más interés que empezar a ver las herramientas, así que lo reimplementaremos usando Ruby.

Siguiendo el texto, lo primero que hay que hacer es iniciar Xcode y crear un nuevo proyecto. Como [hemos instalado RubyCocoa](http://www.principia.info/2007/2/16/instalacion-de-rubycocoa), dispondremos de un nuevo tipo de proyecto, *Cocoa-Ruby Application*:

![New Cocoa-Ruby Application](http://principia.info/assets/2007/2/17/CP_2_1_New_CocoaRuby.png)

Después de indicar qué nombre queremos para el proyecto, Xcode generará el esqueleto. Como vemos, se ha generado un script `rb_main.rb` que es llamado por el  punto de entrada (en `main.m`); y además se ha añadido el framework para RubyCocoa. Si compilamos y lanzamos el proyecto, podemos ver que se ejecuta con normalidad.

![Ficheros del proyecto](http://principia.info/assets/2007/2/17/CP_2_2_XCode_RbRandomApp.png)

Si examinamos el código generado en el esqueleto de la aplicación, vemos que `main.m`, en lugar de llamar a `NSApplicationMain`, llama a `RbApplicationMain` con el nombre del script. 

El script, por su parte, es aparentemente algo más complejo:


    require 'osx/cocoa'

    def rb_main_init
      path = OSX::NSBundle.mainBundle.resourcePath.fileSystemRepresentation
      rbfiles = Dir.entries(path).select {|x| /\.rb\z/ =~ x}
      rbfiles -= [ File.basename(__FILE__) ]
      rbfiles.each do |path|
        require( File.basename(path) )
      end
    end

    if $0 == __FILE__ then
      rb_main_init
      OSX.NSApplicationMain(0, nil)
    end

Lo primero que hace el script es incluir las librerias de Cocoa (para Ruby). Luego define una función, `rb_main_init`, que es llamada si el propio script es el que se pasó como parámetro, para despues llamar al método `NSApplicationMain`, que carga los ficheros NIB e inicia el bucle principal de cualquier aplicación en Cocoa.

Qué es lo que hace esta función? Recorre el paquete (el *bundle*) de la aplicación, buscando todos los ficheros de ruby que hay en ella, y hace un `require` sobre ellos, presumiblemente para que estén disponibles antes de ser usados desde la aplicación.

Una vez analizado esto, podemos seguir con la aplicación, lanzando Interface Builder y definiendo la interfaz, tal como se explica en el texto. Una vez creada la ventana principal de la aplicación, se supone que hemos de definir una clase `Foo` con un *outlet* y una acción, y a continuación que Xcode genere el código para esta clase. Pero Xcode aún no genera código en Ruby, asi que solo podemos obtenerlo en Objective-C. Yo  he seguido este procedimiento para luego convertirlo en Ruby, pero usando el código así obtenido, que presento a continuación, te puedes saltar ese paso.

    #
    #  Foo.rb
    #  RbRandomApp
    #
    #  Created by Victor Jalencas on 18/02/07.
    #

    require 'osx/cocoa'

    class Foo < OSX::NSObject

    	ib_outlets :textField
	
    	def generate(sender)
    	end
	
    	def seed(sender)
    	end

    end


Ahora ya podemos instanciar Foo. Si observamos el inspector de conexiones, veremos que existe un outlet, que está ahi gracias al método de clase que hemos usado para declararlo,`ib_outlets` (que es, de hecho, un alias de `attr_writer`). Sin embargo no hay un método para declarar las acciones, con lo que hay que añadirlas a mano en Interface Builder. Me ha dicho un pajarito que pronto habrá un método de clase para esto.

A continuación, conectamos los outlets y las acciones normalmente. Solo resta implementar los métodos que tenemos declarados:


    #
    #  Foo.rb
    #  RbRandomApp
    #
    #  Created by Victor Jalencas on 18/02/07.
    #

    require 'osx/cocoa'

    class Foo < OSX::NSObject

    	ib_outlets :textField
	
    	def generate(sender)
    	  generated = (rand(100))+1
    	  @textField.setIntValue(generated)
    	end
	
    	def seed(sender)
    	  srand(Time.now.to_i)
    	  @textField.setStringValue "Generator seeded"
    	end

    end


Si compilamos y ejecutamos el código ahora, veremos que funciona perfectamente. Donde en el código original se llamaba a funciones en C (`random`, `srand`y `time`), he usado los equivalentes en Ruby.
También vemos que los outlets son variables de instancia, y que no es necesario convertir los strings de ruby a `NSString` (ésta es una de las pocas conversiones automáticas que nos ofrece RubyCocoa)

Para finalizar el ejemplo, añadiremos el método `awakeFromNib`:

	def awakeFromNib
	  now = OSX::NSCalendarDate.calendarDate
	  @textField.setObjectValue now
	end

Y con esto, terminamos la aplicación. Podríamos ejecutar las aplicaciones hechas con Ruby y con ObjC lado a lado y obtendríamos los mismos resultados, excepto por el hecho de que en Ruby, si no se siembra el generador de números aleatorios, se inicializa por defecto con un valor dependiente de la fecha y el PID, mientras que la función `random` de C no lo hace y repetirá siempre los mismos números mientras no sea inicializada.
