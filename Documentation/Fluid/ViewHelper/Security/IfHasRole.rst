.. include:: ../../../Includes.txt

f:security.ifHasRole
====================

With this ViewHelper you are able to set a block condition which is only shown
if there is a frontend user logged in **and** is in the given usergroup.

Properties
----------

role
~~~~

:aspect:`Variable type`
    String

:aspect:`Description`
    The usergroup, either as the usergroup UID or as the usergroup title

:aspect:`Default value`

:aspect:`Mandatory`
    Yes


Examples
--------

Role by number:

.. code-block:: html

   <f:security.ifHasRole role="7">
      <f:then>
         This is being shown in case the current FE user belongs to a
         FE usergroup (aka role) with the uid "7"
      </f:then>
      <f:else>
         This is being displayed in case you do not have the role or
         you are not logged in.
      </f:else>
   </f:security.ifHasRole>


Role by usergroup title:

.. code-block:: html

   <f:security.ifHasRole role="Administrator">
      <f:then>
         This is being shown in case the current FE user belongs to a
         FE usergroup (aka role) with the title "Administrator"
      </f:then>
      <f:else>
         This is being displayed in case you do not have the role or
         you are not logged in.
      </f:else>
   </f:security.ifHasRole>
