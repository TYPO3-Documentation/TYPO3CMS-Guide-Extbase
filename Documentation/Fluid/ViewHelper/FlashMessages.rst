.. include:: ../../Includes.txt

f:flashMessages
===============

This ViewHelper is for use in extensions you programme yourself, as it is intended to output error messages which are
shown to the website user. For example, a user has forgotten to fill out a required field and the relevant Action method
is connected to a server-side validator. The input is passed to an errorAction method, which collates each error
messages as a 'Flash Message' in turn, then outputs them all as a “bundle” at the place where you have inserted this
ViewHelper.

Properties
----------

All the :ref:`universal tag attributes <UniversalTagAttributes>`

Example
-------

::

 <f:flashMessages />
