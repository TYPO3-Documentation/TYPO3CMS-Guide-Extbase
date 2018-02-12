.. include:: ../../../Includes.txt

.. highlight:: html

.. _viewhelper-uri-typolink:

==============
f:uri.typolink
==============

Usage
=====

Minimal usage
   Code: `<f:uri.typolink parameter="{link}" />`
   
   Assumption: `{link}` contains string `"19 - - - &X=y"`.
      
   Result: `index.php?id=19&X=y`

All parameters
   `<f:uri.typolink parameter="…" additionalAttributes="…" additionalParams="…" useCacheHash="false" />`

*Note:* The string denoted by `{link}` has to be given with a full set of parameters as expected by the
:ref:`TypoScript typolink standard <t3tsref:stdwrap-typolink>`.
Fluid will not use the parts 'target', 'class' and 'title' within the typolink viewhelper.



Parameters
==========

:parameter:
   **required**, *type:* **string**, *default value:* **NULL**

   The UID of the target page to link to. :ref:`TypoScript syntax <t3tsref:stdwrap-typolink>`
   is expected, for example like `19 _blank`.


:additionalAttributes:
   **not required**, *type:* **array**, *default value:* **empty array**

   To add attributes to the a-tag. The array will automatically be converted 
   to :ref:`TypoScript-Syntax <t3tsref:stdwrap-typolink>` :ts:`param1=value&param2=value`

:additionalParams:
   **not required**, *type:* **string**, *default value:* **empty string**

   Add more parameters to the link. Opposed to `arguments` these names will not be
   prefixed with the extension name.

:useCacheHash:
   **not required**, *type:* **boolean**, *default value:* **false**
   
   See :ref:`t3tsref:typolink-usecachehash`
   

Examples
========

Example 1
---------

Code
   `<f:uri.typolink parameter="{link}" additionalParams="&u=b" />`

Assumption
   `{link}` contains string `"19 - - - &X=y"`

Output
   `index.php?id=19&X=y&u=b`


Example 2
---------

((correct?))

Tag code::

   <f:uri.typolink parameter="{link}" additionalParams="''">
   	<!-- tag content - may (will?) be ignored! -->
   </f:uri.typolink>

Inline code::

   {f:uri.typolink(parameter: "{link}", additionalParams: '''')}


Example 99: ...
---------------

((to be written))

