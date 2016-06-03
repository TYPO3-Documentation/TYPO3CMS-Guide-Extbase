.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.security.ifHasRole
=======================

This ViewHelper checks to see whether a logged-in backend user has been assigned the indicated role, through use of a 
user group. The general use is the same as with the `f:if` ViewHelper: if the check is true, then the code within the 
subsidiary `f:then` ViewHelper will be parsed. If not, then the content of the optional `f:else` ViewHelper will be 
parsed.

Properties
----------

role
~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Either the (case-sensitive) user group name or (preferentially) the user group UID.

:aspect:`Default value`
     NULL

:aspect:`Required`
     Yes

Examples
--------

IF->THEN->ELSE
~~~~~~~~~~~~~~

::

 <f:be.security.ifHasRole role="Administrator">
   <f:then>
     You have permission to edit this content.
   </f:then>
   <f:else>
     Only backend users with administration rights may edit this content.
   </f:else>
 </f:be.security.ifHasRole>

Status-dependent content
~~~~~~~~~~~~~~~~~~~~~~~~

::

 <f:be.security.ifHasRole role="2">
   Welcome, Administrator.
 </f:be.security.ifHasRole>
