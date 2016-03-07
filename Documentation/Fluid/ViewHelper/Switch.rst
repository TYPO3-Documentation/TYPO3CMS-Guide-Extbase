.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

**Link for german translation**

http://docs.typo3.org/typo3cms/drafts/github/froemken/ExtbaseGuide/Fluid/ViewHelper/Switch.html

f:switch
=========

This ViewHelper was introduced in v6.2, to allow a multi-case comparison to be made within a single ViewHelper. This 
is much simpler than using a series of stacked f:if ViewHelpers.

Properties
---------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    expression
   :Datatype:    Mixed
   :Description: A value or variable to use as the basis of a case comparison.
   :Standard:    NULL
   :Mandatory:   Yes

Example
-------

::

 <f:switch expression="{person.gender}">
   <f:case value="1">Hello Mr. {person.lastName}</f:case>
   <f:case value="2">Hello Mrs. {person.lastName}</f:case>
   <f:case value="3">Hello Miss {person.lastName}</f:case>
   <f:case default="TRUE">A person with no specified gender</f:case>
 </f:switch>
 
 **Output for a value of 2**
 
::

 Hello Mrs. Brown
 
The use of this ViewHelper is often a sign of a weak programming architecture. If the f:switch ViewHelper is used a lot, 
then a better approach would be to re-consider the architecture within the Actions and the Controller.

.. tip::

   The example above could alternatively be solved by using a Partial or Section for each gender, although performance issues 
   need to be considered. (See f:render.)
 
::

 <f:render partial="person/{person.gender}" />