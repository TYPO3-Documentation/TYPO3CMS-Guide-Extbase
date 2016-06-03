.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../../Includes.txt

f:be.buttons.csh
================

This ViewHelper is rarely used, but very helpful nonetheless. It enables you to include hints into backend forms.

TYPO3 uses this functionality all over the backend, and it is noticeable by the small “question mark” images. Hovering 
over the element reveals help text in a small tooltip, whilst clicking on the element displays the help text in a popup 
window. A user configuration setting is available, to allow or disallow the popup window.

Properties
----------

table
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Database table name.

:aspect:`Default value`
     NULL

:aspect:`Required`
     No

field
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The key from the locallang file.

:aspect:`Default value`
     Empty string

:aspect:`Required`
     No

iconOnly
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Display the icon, but not the text.

:aspect:`Default value`
     FALSE

:aspect:`Required`
     No

styleAttributes
~~~~~~~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Additional style attribute to be added to the containing table.

:aspect:`Default value`
     Empty string

:aspect:`Required`
     No


Special case
------------

There's a special case in which the “table” property doesn't need to be defined. This is the case then there are 
form fields in the module, but when there is no 1:1 column in the database. For example, in the Scheduler, which 
stores its information in a serialized format in a single field, or in the case of a search field, whose value isn't 
sent to the database. Such fields can be assigned a csh icon through the addition of an entry in ext_tables.php.::

 \TYPO3\CMS\Core\Utility\ExtensionManagementUtility::addLLrefForTCAdescr(
   '_MOD_FullModuleName',
   'Path to a language file'
 );


Note the reference to the fully-formed module name. This is comprised of the category (e.g. “web”), the 
upper-camel-cased extension name and the upper-camel-cased module name. In the example of an extension named 
“sfextbase” and a module named “extbase”, the complete name would be::

 web_SfextbaseExtbase


Here's an example of how the configuration might appear::

 \TYPO3\CMS\Core\Utility\ExtensionManagementUtility::addLLrefForTCAdescr(
   '_MOD_web_SfextbaseExtbase',
   'EXT:' . $_EXTKEY . '/Resources/Private/Language/locallang_extbase.xlf'
 );


The entry for the email address in the XLF file would be as follows::

 <trans-unit id="email.alttitle" xml:space="preserve">
   <source>Email</source>
 </trans-unit>
 <trans-unit id="email.description" xml:space="preserve">
   <source>Enter your email address</source>
 </trans-unit>
 <trans-unit id="email.details" xml:space="preserve">
   <source>I am a really long description, which gives plenty of detail about this field relating to an email address, 
   as well as what you need to note and that you need to add a valid email address in this field.</source>
 </trans-unit>


Examples
--------

.. caution::

 There is a request to the backend user option edit_showFieldHelp within the source code of the csh API. This isn't 
 set by default, which therefore blocks the output of the csh help text. In order to see a working version of this 
 ViewHelper, you'll need to ensure that the following option is set within the TS config for the active user or user 
 group.::

  setup.override.edit_showFieldHelp = text


Example: database fields
########################

In the majority of TYPO3 tables, the language file key is usually the same as the column name::

 <f:be.buttons.csh table="tt_content" field="header" />


Example: style attributes
#########################

::

 <f:be.buttons.csh table="tt_content" field="header" styleAttributes="background-color: red;" />


Example: Icons for form fields without a 1:1 database structure
###############################################################

This example relates to the special case mentioned above, in which the table name may not be indicated.::

 <f:be.buttons.csh field="email" />