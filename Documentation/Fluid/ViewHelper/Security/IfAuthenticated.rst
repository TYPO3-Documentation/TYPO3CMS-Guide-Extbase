.. include:: ../../../Includes.txt

f:security.ifAuthenticated
==========================

With this ViewHelper you are able to set a block condition which is only shown if there
is a frontend user logged in. In this case it does not matter to which usergroup the user belongs.

Example
-------

.. code-block:: html

   <f:security.ifAuthenticated>
     <f:then>
        This part is shown if there is a frontend user logged in.
     </f:then>
     <f:else>
        This part is shown if the current user is not logged in.
     </f:else>
   </f:security.ifAuthenticated>
