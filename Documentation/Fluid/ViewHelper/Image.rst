.. include:: ../../Includes.txt

f:image
=======

The work which was formerly carried out in an extension or in TypoScript is now available as a complete ViewHelper.
You don't have to just compress your images: you can re-size them on the server using PHP's GDlib or using ImageMagick.

Properties
----------

All the :ref:`universal tag attributes <UniversalTagAttributes>`

Inline usage example
--------------------

::

   {f:image(additionalAttributes: {foo: 'bar'}, data: {foo: 'bar'}, src: 'NULL', width: 'NULL', height: 'NULL', minWidth: 123, minHeight: 123, maxWidth: 123, maxHeight: 123, treatIdAsReference: 1, image: [anySimpleType], crop: [anySimpleType], cropVariant: 'default', absolute: 1, class: 'NULL', dir: 'NULL', id: 'NULL', lang: 'NULL', style: 'NULL', title: 'NULL', accesskey: 'NULL', tabindex: 123, onclick: 'NULL', alt: 'NULL', ismap: 'NULL', longdesc: 'NULL', usemap: 'NULL')}


Exclusive properties of the HTML tag
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

alt
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    An alternative text to be used in browsers which cannot display the image for any reason.

:aspect:`Default value`

:aspect:`Mandatory`
    Yes

ismap
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Specifies an image as a server-side image-map.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

longdesc
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    An URI which references a web page containing a detailed explanation of the image.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

usemap
~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Specifies an image as a client-side image-map.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Exclusive properties of this ViewHelper
########################################

absolute
~~~~~~~~
:aspect:`Variable type`
    boolean

:aspect:`Description`
    Force an absolute URL, including the protocol, domain name and full image path.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

accesskey
~~~~~~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Keyboard shortcut to access this element

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No

additionalAttributes
~~~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    array

:aspect:`Description`
    Additional tag attributes. They will be added directly to the resulting HTML tag.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

alt
~~~
:aspect:`Variable type`
    string

:aspect:`Description`
   Specifies an alternate text for an image. If the FAL entry has an alternative text, this will be
   output automatically.

:aspect:`Default value`
    Empty string

:aspect:`Mandatory`
    No

class
~~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    CSS class(es) for this element

:aspect:`Default value`
    empty string

:aspect:`Mandatory`
    No

crop
~~~~
:aspect:`Variable type`
    anySimpleType

:aspect:`Description`
    Overrule cropping of image (setting to FALSE disables the cropping set in FileReference)

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

cropVariant
~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Select a cropping variant, in case multiple croppings have been specified or stored in FileReference

:aspect:`Default value`
    'default'

:aspect:`Mandatory`
    No

data
~~~~
:aspect:`Variable type`
    array

:aspect:`Description`
    Additional data-* attributes. They will each be added with a "data-" prefix.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

dir
~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Text direction for this HTML element. Allowed strings: "ltr" (left to right), "rtl" (right to left)

:aspect:`Default value`
    empty string

:aspect:`Mandatory`
    No

height
~~~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Height of the image. This can be a numeric value representing the fixed height of the image in pixels. But you can also perform simple calculations by adding "m" or "c" to the value. See imgResource.width for possible options.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

id
~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Unique (in this file) identifier for this HTML element.

:aspect:`Default value`
    empty string

:aspect:`Mandatory`
    No

image
~~~~~
:aspect:`Variable type`
    anySimpleType

:aspect:`Description`
    A FAL object

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

ismap
~~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Specifies an image as a server-side image-map. Rarely used. Look at usemap instead

:aspect:`Default value`
    empty string

:aspect:`Mandatory`
    No

lang
~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Language for this element. Use short names specified in RFC 1766

:aspect:`Default value`
    empty string

:aspect:`Mandatory`
    No

longdesc
~~~~~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Specifies the URL to a document that contains a long description of an image

:aspect:`Default value`
    empty string

:aspect:`Mandatory`
    No

maxHeight
~~~~~~~~~
:aspect:`Variable type`
    integer

:aspect:`Description`
    The maximum height of the generated image

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

maxWidth
~~~~~~~~
:aspect:`Variable type`
    integer

:aspect:`Description`
    The maximum width of the generated image

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

minHeight
~~~~~~~~~
:aspect:`Variable type`
    integer

:aspect:`Description`
    The minimum height of the generated image

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

minWidth
~~~~~~~~
:aspect:`Variable type`
    integer

:aspect:`Description`
    The minimum width of the generated image

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

onclick
~~~~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    JavaScript evaluated against the onclick event

:aspect:`Default value`
    empty string

:aspect:`Mandatory`
    No

src
~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    A path to a file, a combined FAL identifier or an UID (int). If `treatIdAsReference` is set, the integer is
    considered the uid of the sys_file_reference record. Because we're dealing with an `IMG_RESOURCE`, you can also work
    with `EXT:` paths. If you already have a FAL object, consider using the `image` property instead.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

style
~~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Individual CSS styles for this element

:aspect:`Default value`
    empty string

:aspect:`Mandatory`
    No

tabindex
~~~~~~~~
:aspect:`Variable type`
    integer

:aspect:`Description`
    Specifies the tab order of this element

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

title
~~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Tooltip text of element

:aspect:`Default value`
    empty string

:aspect:`Mandatory`
    No

treatIdAsReference
~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    boolean

:aspect:`Description`
    Given src argument is a sys_file_reference record

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

usemap
~~~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Specifies an image as a client-side image-map

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

width
~~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Width of the image. This can be a numeric value representing the fixed width of the image in pixels. But you can
    also perform simple calculations by adding "m" or "c" to the value. See `imgResource.width` for possible options.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

Examples
--------

Output the image in its original resolution
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

 <f:image src="fileadmin/user_upload/landscape.jpg" />

Output a smaller image
~~~~~~~~~~~~~~~~~~~~~~

The proportions of the original image will be respected in this example.

::

 <f:image src="fileadmin/user_upload/landscape.jpg" width="50" />

Re-size and crop an image
~~~~~~~~~~~~~~~~~~~~~~~~~

::

 <f:image src="fileadmin/user_upload/landscape.jpg" alt="Landscape" width="100c" height="100c" />

The shorter side of the image will be set to 100px and the longer side will be cropped to 100px. Cropping takes place
from the centre of the image by default. Use 100c-100 to crop from the top (or left), or 100c+100 to crop from the right
(or bottom). In these examples, the value '100' after the 'c' is a percentage value.
