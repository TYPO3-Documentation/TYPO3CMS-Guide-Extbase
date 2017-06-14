.. include:: ../../Includes.txt

**Link for german translation**

http://docs.typo3.org/typo3cms/drafts/github/froemken/ExtbaseGuide/Fluid/ViewHelper/Switch.html

f:switch
=========

This ViewHelper was introduced in v6.2, to allow a multi-case comparison to be made within a single ViewHelper. This
is much simpler than using a series of stacked `f:if` ViewHelpers.

Properties
----------

expression
~~~~~~~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
    A value or variable to use as the basis of a case comparison.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

Example
-------

::

 <f:switch expression="{person.gender}">
   <f:case value="1">Hello Mr. {person.lastName}</f:case>
   <f:case value="2">Hello Mrs. {person.lastName}</f:case>
   <f:case value="3">Hello Miss {person.lastName}</f:case>
   <f:defaultCase>A person with no specified gender</f:defaultCase>
 </f:switch>

Output for a value of 2
~~~~~~~~~~~~~~~~~~~~~~~

::

 Hello Mrs. Brown

The use of this ViewHelper is often a sign of a weak programming architecture. If the f:switch ViewHelper is used a lot,
then a better approach would be to re-consider the architecture within the Actions and the Controller.

.. tip::

   The example above could alternatively be solved by using a Partial or Section for each gender, although performance issues
   need to be considered. (See f:render.)

::

 <f:render partial="person/{person.gender}" />
