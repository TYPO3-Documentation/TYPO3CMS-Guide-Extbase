.. include:: ../../Includes.txt

f:spaceless
===========

Removes redundant spaces between HTML tags while preserving the whitespace that may be inside HTML tags. Trims the final result before output.

Properties
----------

This ViewHelper doesn't accept any properties.

Example
-------

::

 <f:spaceless>
   <div>
       <div>
           <div>text

   text</div>
       </div>
   </div>
 </f:spaceless>

Output
------

::

 <div><div><div>text

 text</div></div></div>
