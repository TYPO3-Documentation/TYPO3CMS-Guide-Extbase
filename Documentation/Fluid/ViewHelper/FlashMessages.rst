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

renderMode
~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Should the error messages be displayed as a list (UL) or wrapped in a container (DIV)?

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

Example
-------

::

 <f:flashMessages />

Example with output contained in a DIV
--------------------------------------

::

 <f:flashMessages renderMode="div" />