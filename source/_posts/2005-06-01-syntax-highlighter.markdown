---
layout: post
title: Syntax Highlighter
---

C&#243;digo Ruby (lifteado de la web de Why):
<pre lang="ruby">
 class MethodMagic

   alias_method :old_respond_to?, :respond_to?

   def respond_to? (method, include_private=false)
     old_respond_to?(method.to_sym, include_private) || 
     create_dynamic_method(method)
   end

   alias_method :old_method_missing, :method_missing

   def method_missing(method, *args)
     if create_dynamic_method(method)
       send(method.to_sym, *args)
     else
       old_method_missing(method)
     end
   end

   # If the method name conforms to our rigorous specifications, 
   # create a new body on the fly and define the sucker
   def create_dynamic_method(method)
     if method.to_s.match /^find_by_/
       self.class.send(:define_method, method.to_sym) { |*args|
         puts "Called #{method}(#{args.join ", "})" 
       } 
       true
     else
       false
     end
   end

   # just here as an example of a normal method
   def find; end

end
</pre>

C&#243;digo ECMAScript (de la especificaci&#243;n): 
<pre lang="jscript">
function A() {
function B(x) {return x*x;}
return B;
}
function C() {
return eval("(function (x) {return x*x;})");
}
var b1 = A();
var b2 = A();
function b3(x) {return x*x;}
function b4(x) {return x*x;}
var b5 = C();
var b6 = C();
</pre>
