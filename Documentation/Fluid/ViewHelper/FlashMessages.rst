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

queueIdentifier
~~~~~~~~~~~~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
   Flash-message queue to use.

:aspect:`Default value`
   null

:aspect:`Mandatory`
    No

as
~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The name of the current flashMessage variable for rendering inside.

:aspect:`Default value`
    null

:aspect:`Mandatory`
    No


Examples
--------

**Standard Usage**

::

 <f:flashMessages />

**Self Rendered Template**

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
