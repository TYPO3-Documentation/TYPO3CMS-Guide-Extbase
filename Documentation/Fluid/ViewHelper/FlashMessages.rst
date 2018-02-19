.. highlight:: html

===============
f:flashMessages
===============

This viewhelper is for use in extensions you program yourself, as it is
intended to output error messages which are shown to the website user. For
example, a user has forgotten to fill out a required field and the relevant
Action method is connected to a server-side validator. The input is passed to
an errorAction method, which collates each error messages as a 'Flash Message'
in turn, then outputs them all as a “bundle” at the place where you have
inserted this viewhelper.


Usage
=====

Minimal usage:
   ::

      <f:flashMessages />


All parameters:
   ::

      <f:flashMessages queueIdentifier="myQueue" as="flashMessages"></f:flashMessages>


Parameters
==========

All the :ref:`universal tag attributes <UniversalTagAttributes>`

plus

.. rst-class:: dl-parameters

queueIdentifier
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   Flash-message queue to use.


as
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   The name of the current flashMessage variable for rendering inside.


Examples
========

Example: Standard Usage
-----------------------

::

    <f:flashMessages />

Example: Self Rendered Template
-------------------------------

::

   <f:flashMessages queueIdentifier="myQueue" as="flashMessages">
      <f:for each="{flashMessages}" as="flashMessage">
         <div class="alert {flashMessage.class}">
            <f:if condition="{flashMessage.title}">
               <strong>{flashMessage.title}</strong><br>
            </f:if>
            <p>{flashMessage.message -> f:format.html()}</p>
         </div>
      </f:for>
   </f:flashMessages>
