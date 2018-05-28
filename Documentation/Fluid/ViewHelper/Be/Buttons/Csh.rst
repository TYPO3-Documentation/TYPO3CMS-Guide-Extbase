.. include:: ../../../../Includes.txt

================
f:be.buttons.csh
================

This View helper returns a CSH (context sensitive help) button with an icon.
It enables you to include hints into backend forms.

TYPO3 uses this functionality all over the backend, and it is noticeable by the small “question mark” image when hovering
over the element, whilst clicking on the element displays the help text in a small tooltip.

Properties
==========

.. rst-class:: dl-parameters

table
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    null
   :sep:`|`

   Table name ('_MOD_'+module name). If not set, the current module name will
   be used.


field
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   Field name (CSH locallang main key).


wrap
   :sep:`|` :aspect:`Condition:`  optional
   :sep:`|` :aspect:`Type:`       string
   :sep:`|` :aspect:`Default:`    empty string
   :sep:`|`

   Markup to wrap around the CSH, split by `|` .


Special case
------------

There's a special case in which the “table” property doesn't need to be
defined. This is the case when there are form fields in the module, but when
there is no 1:1 column in the database. For example, in the Scheduler, which
stores its information in a serialized format in a single field, or in the case
of a search field, whose value isn't sent to the database. Such fields can be
assigned a csh icon through the addition of an entry in
:file:`ext_tables.php`::

   \TYPO3\CMS\Core\Utility\ExtensionManagementUtility::addLLrefForTCAdescr(
      '_MOD_FullModuleName',
      'Path to a language file'
   );


Note the reference to the fully-formed module name. This is comprised of the
category (e.g. “web”), the upper-camel-cased extension name and the upper-
camel-cased module name. In the example of an extension named “sfextbase” and a
module named “extbase”, the complete name would be::

   web_SfextbaseExtbase


Here's an example of how the configuration might appear::

   \TYPO3\CMS\Core\Utility\ExtensionManagementUtility::addLLrefForTCAdescr(
      '_MOD_web_SfextbaseExtbase',
      'EXT:ext_key/Resources/Private/Language/locallang_extbase.xlf'
   );


The entry for the email address in the XLF file would be as follows:

.. code-block:: xml

    <trans-unit id="email.alttitle" xml:space="preserve">
      <source>Email</source>
    </trans-unit>
    <trans-unit id="email.description" xml:space="preserve">
      <source>Enter your email address</source>
    </trans-unit>
    <trans-unit id="email.details" xml:space="preserve">
      <source>
         I am a really long description, which gives plenty of detail about 
         this field relating to an email address, as well as what you need to 
         note and that you need to add a valid email address in this field.
      </source>
    </trans-unit>


Examples
========

Example: database fields
------------------------

In the majority of TYPO3 tables, the language file key is usually the same as
the column name:

.. code-block:: html

   <f:be.buttons.csh table="tt_content" field="header" />


Example: Icons for form fields without a 1:1 database structure
---------------------------------------------------------------

This example relates to the special case mentioned above, in which the table
name may not be indicated:

.. code-block:: html

   <f:be.buttons.csh field="email" />

