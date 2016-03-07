.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:image
=======

The work which was formerly carried out in an extension or in TypoScript is now available as a complete view helper. 
You don't have to just compress your images: you can re-size them on the server using PHP's GDlib or using ImageMagick.

Properties
----------

.. include:: ../UniversalTagAttributes.txt

Exclusive properties of the HTML tag
####################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    alt
   :Datatype:    String
   :Description: An alternative text to be used in browsers which cannot display the image for any reason.
   :Standard:
   :Mandatory:   Yes

 - :Property:    ismap
   :Datatype:    String
   :Description: Specifies an image as a server-side image-map.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    longdesc
   :Datatype:    String
   :Description: An URI which references a web page containing a detailed explanation of the image.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    usemap
   :Datatype:    String
   :Description: Specifies an image as a client-side image-map.
   :Standard:    NULL
   :Mandatory:   No

Exclusive properties of this ViewHelper
#######################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory
   
 - :Property: absolute
   :Datatype: boolean
   :Description: Force an absolute URL, including the protocol, domain name and full image path.
   :Standard: FALSE
   :Mandatory: No

 - :Property: accesskey
   :Datatype: string
   :Description: Keyboard shortcut to access this element
   :Standard: Empty string
   :Mandatory: No

 - :Property: additionalAttributes	
   :Datatype: array
   :Description: Additional tag attributes. They will be added directly to the resulting HTML tag.
   :Standard: NULL
   :Mandatory: No

 - :Property: alt	
   :Datatype: string
   :Description: Specifies an alternate text for an image. If the FAL entry has an alternative text, this will be 
   output automatically.
   :Standard: Empty string
   :Mandatory: No

 - :Property: class	
   :Datatype: string
   :Description: CSS class(es) for this element
   :Standard: empty string
   :Mandatory: No

 - :Property: crop	
   :Datatype: anySimpleType
   :Description: Overrule cropping of image (setting to FALSE disables the cropping set in FileReference)
   :Standard: NULL
   :Mandatory: No

 - :Property: data	
   :Datatype: array
   :Description: Additional data-* attributes. They will each be added with a "data-" prefix.
   :Standard: NULL
   :Mandatory: No

 - :Property: dir	
   :Datatype: string
   :Description: Text direction for this HTML element. Allowed strings: "ltr" (left to right), "rtl" (right to left)
   :Standard: empty string
   :Mandatory: No

 - :Property: height	
   :Datatype: string
   :Description: Height of the image. This can be a numeric value representing the fixed height of the image in pixels. But you can also perform simple calculations by adding "m" or "c" to the value. See imgResource.width for possible options.
   :Standard: NULL
   :Mandatory: No

 - :Property: id	
   :Datatype: string
   :Description: Unique (in this file) identifier for this HTML element.
   :Standard: empty string
   :Mandatory: No

 - :Property: image	
   :Datatype: anySimpleType
   :Description: A FAL object
   :Standard: NULL
   :Mandatory: No

 - :Property: ismap	
   :Datatype: string
   :Description: Specifies an image as a server-side image-map. Rarely used. Look at usemap instead
   :Standard: empty string
   :Mandatory: No

 - :Property: lang	
   :Datatype: string
   :Description: Language for this element. Use short names specified in RFC 1766
   :Standard: empty string
   :Mandatory: No

 - :Property: longdesc	
   :Datatype: string
   :Description: Specifies the URL to a document that contains a long description of an image
   :Standard: empty string
   :Mandatory: No

 - :Property: maxHeight	
   :Datatype: integer
   :Description: The maximum height of the generated image
   :Standard: NULL
   :Mandatory: No

 - :Property: maxWidth	
   :Datatype: integer
   :Description: The maximum width of the generated image
   :Standard: NULL
   :Mandatory: No

 - :Property: minHeight	
   :Datatype: integer
   :Description: The minimum height of the generated image
   :Standard: NULL
   :Mandatory: No

 - :Property: minWidth	
   :Datatype: integer
   :Description: The minimum width of the generated image
   :Standard: NULL
   :Mandatory: No

 - :Property: onclick	
   :Datatype: string
   :Description: JavaScript evaluated against the onclick event
   :Standard: empty string
   :Mandatory: No

 - :Property: src	
   :Datatype: string
   :Description: A path to a file, a combined FAL identifier or an UID (int). If $treatIdAsReference is set, the integer 
   is considered the uid of the sys_file_reference record. Because we're dealing with an IMG_RESOURCE, you can also work 
   with EXT: paths. If you already have a FAL object, consider using the $image parameter instead.
   :Standard: NULL
   :Mandatory: Yes

 - :Property: style	
   :Datatype: string
   :Description: Individual CSS styles for this element
   :Standard: empty string
   :Mandatory: No

 - :Property: tabindex	
   :Datatype: integer
   :Description: Specifies the tab order of this element
   :Standard: NULL
   :Mandatory: No

 - :Property: title	
   :Datatype: string
   :Description: Tooltip text of element
   :Standard: empty string
   :Mandatory: No

 - :Property: treatIdAsReference	
   :Datatype: boolean
   :Description: Given src argument is a sysfilereference record
   :Standard: FALSE
   :Mandatory: No

 - :Property: usemap	
   :Datatype: string
   :Description: Specifies an image as a client-side image-map
   :Standard: FALSE
   :Mandatory: No

 - :Property: width	
   :Datatype: string
   :Description: Width of the image. This can be a numeric value representing the fixed width of the image in pixels. But you can also perform simple calculations by adding "m" or "c" to the value. See imgResource.width for possible options.
   :Standard: NULL
   :Mandatory: No

Example to output the image in its original resolution
------------------------------------------------------

::

 <f:image src="fileadmin/user_upload/landscape.jpg" />

Example to respect the output a smaller image
---------------------------------------------

The proportions of the original image will be respected.

::

 <f:image src="fileadmin/user_upload/landscape.jpg" width="50" />

Example to re-size and crop an image
------------------------------------

::

 <f:image src="fileadmin/user_upload/landscape.jpg" alt="Landscape" width="100c" height="100c" />

The shorter side of the image will be set to 100px and the longer side will be cropped to 100px. Cropping takes place 
from the centre of the image by default. Use 100c-100 to crop from the top (or left), or 100c+100 to crop from the right 
(or bottom). In these examples, the value '100' after the 'c' is a percentage value.