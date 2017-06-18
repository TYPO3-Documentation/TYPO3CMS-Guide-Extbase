.. include:: ../../Includes.txt

.. _viewhelper-switch:

========
f:switch
========

This ViewHelper was introduced in v6.2 to allow multi-case comparison within a single ViewHelper. This
is much simpler than using a series of stacked `f:if` ViewHelpers.

Properties
==========

expression
----------

:aspect:`Variable type`
   Mixed

:aspect:`Description`
   A value or variable to use as the basis of a case comparison.

:aspect:`Default value`
   NULL

:aspect:`Mandatory`
   Yes

Example
=======

.. highlight:: xml

Let's assume `{person.gender}` evaluates to `2` and
`{person.lastName}` to `Brown`. Given this code::

   <f:switch expression="{person.gender}">
      <f:case value="1">Hello Mr. {person.lastName}</f:case>
      <f:case value="2">Hello Mrs. {person.lastName}</f:case>
      <f:case value="3">Hello Miss {person.lastName}</f:case>
      <f:defaultCase>A person with no specified gender</f:defaultCase>
   </f:switch>

We get as result::

   Hello Mrs. Brown

The frequent use of this ViewHelper may indicate a "weak programming architecture".
The better approach may be to reconsider the architecture within the Actions and the Controller.

.. tip::

   The example above could alternatively be solved by using a
   Partial or Section for each gender, although performance issues
   need to be considered. (See f:render.)

::

   <f:render partial="person/{person.gender}" />


Hint: See the `german translation
<http://docs.typo3.org/typo3cms/drafts/github/froemken/ExtbaseGuide/Fluid/ViewHelper/Switch.html>`__.
