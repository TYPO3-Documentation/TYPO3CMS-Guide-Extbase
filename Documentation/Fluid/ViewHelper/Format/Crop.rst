
.. include:: ../../../Includes.txt

f:format.crop
=============

Crops a string according to the defined properties.

Properties
----------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default
   :Mandatory,10:   Mandatory

 - :Property:    maxCharacters
   :Datatype:    Integer
   :Description: The number of characters to which the string should be abbreviated.
   :Standard:
   :Mandatory:   Yes

 - :Property:    append
   :Datatype:    String
   :Description: A string to be appended to the cropped text.
   :Standard:    ...
   :Mandatory:   No

 - :Property:    respectWordBoundaries
   :Datatype:    Boolean
   :Description: If the value of this property is TRUE, the crop will only happen between complete words. (Before the
   number of characters has been reached.)
   :Standard:    TRUE
   :Mandatory:   Nein

 - :Property:    respectHtml
   :Datatype:    Boolean
   :Description: If the value of this property is TRUE, HTML tags will be taken into account when cropping text. If the
   value is FALSE, then the text may be cropped in the middle of an HTML tag.
   :Standard:    TRUE
   :Mandatory:   No


Examples
--------

Crop
~~~~

.. code-block:: xml

   <f:format.crop maxCharacters="40">
      A bolt of lightning is going to strike the clock tower
      at precisely 10:04pm, next Saturday night.
   </f:format.crop>

If the text is cropped strictly at 40 characters, the end of the string will be in the middle of the word “the”. But
the property 'respectWordBoundaries' is set by default, so the cropped text will read:

.. code-block:: none

   A bolt of lightning is going to strike…


Splitting a word
~~~~~~~~~~~~~~~~

.. code-block:: xml

   <f:format.crop maxCharacters="15" respectWordBoundaries="FALSE">
      A bolt of lightning is going to strike the clock tower
      at precisely 10:04pm, next Saturday night.
   </f:format.crop>


Result:

.. code-block:: none

   A bolt of light...


Don't respect HTML tags
~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: xml

   <f:format.crop maxCharacters="12" respectHtml="FALSE">
      <p>A bolt of <em>lightning</em> is going to strike the clock tower
      at precisely 10:04pm, next Saturday night.</p>
   </f:format.crop>

Result:

.. code-block:: none

   A bolt of...

This result is produced because the individual characters within the paragraph
tag itself are counted as part of the total.
