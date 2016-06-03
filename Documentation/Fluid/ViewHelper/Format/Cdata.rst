.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

.. _f-format-cdata:

f:format.cdata
==============

This ViewHelper wraps a text or variable output with CDATA tags. This is most useful for generating outputs like an RSS 
feed via Fluid. Because these format is based on an XML structure, HTML content within its tags need to be appropriately 
masked using CDATA tags.

Properties
----------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    value
   :Datatype:    String
   :Description: The string to be wrapped with CDATA tags.
   :Standard:    NULL
   :Mandatory:   Nein

Examples
--------


With text
#########

::

 <f:format.cdata>Text to be wrapped</f:format.cdata>

**Output**

::

 <![CDATA[Text to be wrapped]]>

With variables
##############

We'll pass an unusual combination of HTML and text back from our Controller as an example.

 $this->view->assign('variable', '<strong>Stefan</strong>');

We'll wrap the variable with CDATA tags in our Fluid template::

 <f:format.cdata>{variable} is his name</f:format.cdata>

which produces the result::

 <![CDATA[<strong>Stefan</strong> is his name]]>

.. important::

   As you can see, the variable in this example is output 1:1 instead of being parsed using htmlspecialchars and without 
   any kind of other masking. Be aware of this, especially taking care against cross site scripting attacks.