.. include:: ../../Includes.txt

.. highlight:: html

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

Let's assume `{person.gender}` evaluates to `2` and `{person.lastName}` to `Brown`.

Tag notation
   Given this code in tag notation::
   
      <f:switch expression="{person.gender}">
         <f:case value="1">Hello Mr.  {person.lastName}</f:case>
         <f:case value="2">Hello Mrs. {person.lastName}</f:case>
         <f:case value="3">Hello Miss {person.lastName}</f:case>
         <f:defaultCase>A person with no specified gender</f:defaultCase>
      </f:switch>

   The result will be::
      
      Hello Mrs. Brown

Inline notation
   For inline notation it is a good idea to place the actual switching logic
   into a partial and use only `f:render`::
   
      {f:render(partial:'SwitchItem', arguments:'{employee: employee}')}

