.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.security.ifAuthenticated
=============================

This ViewHelper checks to see whether the current page visitor (backend user) is authenticated or not. According to the 
result of the check, the content of the subsidiary `f:then` or `f:else` ViewHelper will be parsed.

This feature is predominantly used in the front end of the website: you can check whether the website visitor is 
currently authenticated as a backend user. A good example of a possible use case is for a front end editing tool, which 
should only be made available to a validated, logged-in backend user.

Properties
----------

This ViewHelper doesn't accept any properties.

Examples
--------

IF->THEN->ELSE
~~~~~~~~~~~~~~

::

 <f:be.security.ifAuthenticated>
   <f:then>
    You have permission to edit this content.
   </f:then>
   <f:else>
    You must log in if you want to edit this content.
   </f:else>
 </f:be.security.ifAuthenticated>


Status-dependent content
~~~~~~~~~~~~~~~~~~~~~~~~

::

 <f:be.security.ifAuthenticated>
   You are seeing this message because you are logged in as a backend user.
 </f:be.security.ifAuthenticated>