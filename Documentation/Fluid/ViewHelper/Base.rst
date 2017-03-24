.. include:: ../../Includes.txt

f:base
======

This ViewHelper embeds the `base-Tag <http://de.selfhtml.org/html/kopfdaten/basis.htm>`_ into your HTML template.

Properties
----------

This ViewHelper doesn't accept any properties.

Example
--------

::

 <f:base />

**Output**

::

 <base href="http://introgit:8080/" />

.. tip::

   Using this ViewHelper only makes sense when you're building a website template - including the <head> - using 
   Fluid. If there's no <head> in the template, this HTML tag will be added to the <body> and that's not where it belongs.
