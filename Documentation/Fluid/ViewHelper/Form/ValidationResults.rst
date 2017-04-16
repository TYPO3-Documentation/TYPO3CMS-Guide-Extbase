.. include:: ../../../Includes.txt

f:form.validationResults
========================

This is a validation results view helper.

Properties
----------

for
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The name of the error name (e.g. argument name or property name). This can also be a property path (like blog.title),
    and will then only display the validation errors of that property.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No

as
~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The name of the variable to store the current error.

:aspect:`Default value`
    validationResults

:aspect:`Mandatory`
    No

Examples
========

Output error messages as a list

::

 <f:form.validationResults>
   <f:if condition="{validationResults.flattenedErrors}">
     <ul class="errors">
       <f:for each="{validationResults.flattenedErrors}" as="errors" key="propertyPath">
         <li>{propertyPath}
           <ul>
           <f:for each="{errors}" as="error">
             <li>{error.code}: {error}</li>
           </f:for>
           </ul>
         </li>
       </f:for>
     </ul>
   </f:if>
 </f:form.validationResults>

Output error messages for a single property

::

 <f:form.validationResults for="someProperty">
   <f:if condition="{validationResults.flattenedErrors}">
     <ul class="errors">
       <f:for each="{validationResults.errors}" as="error">
         <li>{error.code}: {error}</li>
       </f:for>
     </ul>
   </f:if>
 </f:form.validationResults>
