.. include:: ../../../Includes.txt

============
f:be.InfoBox
============

View helper for rendering a styled content infobox markup.

Properties
==========

message
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   The message of the info box, if NULL tag content is used.


title
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   The title of the info box.


state
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       integer
   :sep:`|` :aspect:`Default:`    InfoboxViewHelper::STATE_NOTICE
   :sep:`|`

   The Infobox provides different context sensitive states that can be used to
   provide an additional visual feedback to the to the user to underline the
   meaning of the information. The possible states are::

       InfoboxViewHelper::STATE_NOTICE
       InfoboxViewHelper::STATE_INFO
       InfoboxViewHelper::STATE_OK
       InfoboxViewHelper::STATE_WARNING
       InfoboxViewHelper::STATE_ERROR


iconName
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   The icon name from font awesome, NULL sets default icon.


disableIcon
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       boolean
   :sep:`|` :aspect:`Default:`    false
   :sep:`|`

   If set to TRUE, the icon is not rendered.


Examples
========

Simple
------

::

   <f:be.infobox title="Message title">your box content</f:be.infobox>

All options
-----------

::

   <f:be.infobox title="Message title" 
                 message="your box content" 
                 state="-2" 
                 iconName="check" 
                 disableIcon="true" 
   />
