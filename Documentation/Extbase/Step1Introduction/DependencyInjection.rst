.. include:: ../Includes.txt

Dependency Injection
====================

In development environments, objects are very often dependent upon other objects. 
For example, content elements are dependent upon pages. This means that when we 
instantiate a content element, we also need to instantiate the dependent page object. 
This happens through a constructor on the dependent object, which may also control 
further initialisation objects. In our example of a *Page*, this could be a *page tree* 
or a *rootline object*.

Because of these fixed dependencies, you would have formerly run into problems when you 
tried to test individual methods within the page object - without a related page tree 
object, you couldn't run your tests. This problem has been overcome through the 
implementation of *dependency injections*. Many constructors have been removed or 
re-written for Extbase, and relationships to other classes moved out into smaller, 
dedicated methods. This means that an object can be instantiated without always needing 
to instantiate the dependent objects.

There is an additional advantage when it comes to phpUnit: you have the ability to bind 
a completely separate object to your page tree. For example, if you're working with a 
database object, you can instruct phpUnit to bind a database object which reads from and writes 
to RAM-based tables. This allows you to run tests on your system without running 
into the danger of accessing and potentially corrupting “real” data.