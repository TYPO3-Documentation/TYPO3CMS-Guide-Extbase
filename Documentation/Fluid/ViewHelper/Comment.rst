.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:comment
=========

Evrything inside an f:comment view helper will be removed. View helpers within an f:comment block will not be executed. 
This view helper is most useful when debugging a website: for example, you can temporarily wrap a f:for loop with an 
f:comment view helper to stop it from being executed.

Properties
----------

This view helper has no properties.

Example
-------

::

 <f:comment>
   <p>This text will not be displayed</p>
   <p>My name is: {address.firstName}</p>
 </f:comment>
 <p>{address.firstName} lives in city xyz</p>
 <![CDATA[<p>This text was made by {address.firstName} and will be displayed but not processed.</p>]]>

**Output**

::

 <p>Stefan lives in city xyz</p>
 <p>This text was made by {address.firstName} and will be displayed but not processed.</p>

.. tip::

   The last row in this example is a special case. By using CDATA notation, you can stop the processing of variable 
   placeholders from being executed. The text will be output, but the placeholder {address.firstName} won't be 
   replaced. This is most common when working with JavaScript in your template, where you may want to output a 
   string containing curly quotes.
