.. include:: ../../../Includes.txt

f:uri.action
============

This ViewHelper creates a link to a given action.

Properties
----------

action
~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Here you set the action name without appending "Action".
    If not given the *current* action will be used.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No


arguments
~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Additional parameters for the link.
    They will be prefixed with the plugin name.

:aspect:`Default value`
    Empty array

:aspect:`Mandatory`
    No


controller
~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Here you can set a controller. If it's not specified,
    the current controller will be used.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No


extensionName
~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Here you can set an extension name.
    If not given the *current* extension name will be used.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No


pluginName
~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Here you can set a plugin name.
    If not given the *current* plugin name will be used.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No


pageUid
~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Here you can set a page UID.
    If not specified the action will return to the *current* page.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No


pageType
~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Here you can set a page type.

:aspect:`Default value`
    0

:aspect:`Mandatory`
    No


noCache
~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Sets the `?no_cache=1` parameter

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No


noCacheHash
~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set then the *cHash parameter* will not be added to the link.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No


section
~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Here you can set an anchor to be linked to.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No


format
~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Sets the format of the target page. It can be set to "xml" alternatively.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No


linkAccessRestrictedPages
~~~~~~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set the link will be set to restricted pages even if the user is not logged in.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No


additionalParams
~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Adds parameters to the link. The difference to `arguments` is that
    these parameters are not prefixed with the plugin name.

:aspect:`Default value`
    Empty array

:aspect:`Mandatory`
    No


absolute
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set the link will be absolute including scheme and domain.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No


addQueryString
~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set the current parameters of the URL will be appended to the generated link.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No


argumentsToBeExcludedFromQueryString
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    If set and `addQueryString` activated, the listed parameters will be removed.

:aspect:`Default value`
    Empty array

:aspect:`Mandatory`
    No


Example
-------

.. code-block:: html

   {f:uri.action(action: 'show', arguments: '{foo: \'bar\'}')}

