.. include:: ../../../Includes.txt

f:be.InfoBox
============

View helper for rendering a styled content infobox markup.

Properties
----------

message
~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The message of the info box, if NULL tag content is used.

:aspect:`Default value`
    Empty string

:aspect:`Required`
    No

title
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The title of the info box.

:aspect:`Default value`
    Empty string

:aspect:`Required`
    No

state
~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    The Infobox provides different context sensitive states that can be used to provide an additional visual feedback
    to the to the user to underline the meaning of the information.
    The possible states are:
    InfoboxViewHelper::STATE_NOTICE
    InfoboxViewHelper::STATE_INFO
    InfoboxViewHelper::STATE_OK
    InfoboxViewHelper::STATE_WARNING
    InfoboxViewHelper::STATE_ERROR

:aspect:`Default value`
    InfoboxViewHelper::STATE_NOTICE

:aspect:`Required`
    No

iconName
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The icon name from font awesome, NULL sets default icon.

:aspect:`Default value`
    Empty string

:aspect:`Required`
    No

disableIcon
~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If set to TRUE, the icon is not rendered.

:aspect:`Default value`
    FALSE

:aspect:`Required`
    No


Examples

Simple
~~~~~~

::

    <f:be.infobox title="Message title">your box content</f:be.infobox>

All options
~~~~~~~~~~~

::

    <f:be.infobox title="Message title" message="your box content" state="-2" iconName="check" disableIcon="true" />
