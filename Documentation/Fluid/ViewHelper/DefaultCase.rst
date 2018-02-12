.. include:: ../../Includes.txt

f:defaultCase
=============

A view helper which specifies the "default" case when used within the SwitchViewHelper.
Returns the contents of this view helper if no other "Case" view helper of the surrounding switch view helper matches.

Properties
----------

This ViewHelper has no properties.

Example
-------

::

 <f:switch expression="{person.gender}">
   <f:case value="1">Hello Mr.  {person.lastName}</f:case>
   <f:case value="2">Hello Mrs. {person.lastName}</f:case>
   <f:case value="3">Hello Miss {person.lastName}</f:case>
   <f:defaultCase>A person with no specified gender</f:defaultCase>
 </f:switch>
