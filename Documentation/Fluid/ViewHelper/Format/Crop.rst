
.. include:: ../../../Includes.txt

f:format.crop
=============

Crops a string according to the defined properties.

maxCharacters
-------------

:aspect:`Datatype`
      Integer

:aspect:`Description`
      The number of characters to which the string should be abbreviated.

:aspect:`Required`
      Yes

append
------

:aspect:`Datatype`
      String

:aspect:`Description`
      A string to be appended to the cropped text.


respectWordBoundaries
---------------------

:aspect:`Datatype`
      boolean

:aspect:`Description`
      If the value of this property is TRUE, the crop will only
      happen between complete words, before the number of
      characters has been reached.

:aspect:`Default`
      True


respectHtml
-----------

:aspect:`Datatype`
      boolean

:aspect:`Description`
      If the value of this property is TRUE, HTML tags will be taken
      into account when cropping text. If the value is FALSE, then
      the text may be cropped in the middle of an HTML tag.

:aspect:`Default`
      True


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
