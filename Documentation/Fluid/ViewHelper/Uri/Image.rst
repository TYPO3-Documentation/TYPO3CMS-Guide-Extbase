.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:uri.image
===========

Properties
----------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Default value
   :Mandatory,10:   Mandatory

 - :Property:    src
   :Datatype:    String
   :Description: Path and file name to the source image. The path must be relative to the project's webroot folder. 
                 You can also use paths which feature the EXT: convention.
   :Standard:
   :Mandatory:   Yes

 - :Property:    width
   :Datatype:    String
   :Description: Width of the image. In addition to a numeric value (pixels), you can also add the suffix “c” or “m” in 
                 order to crop or scale the generated image. (Check out the imgResource documentation for details.)
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    height
   :Datatype:    String
   :Description: Height of the image. In addition to a numeric value (pixels), you can also add the suffix “c” or “m” in 
                 order to crop or scale the generated image. (Check out the imgResource documentation for details.)
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    minWidth
   :Datatype:    Integer
   :Description: A minimum width for the generated image, in pixels. Smaller images will be scaled up, as long as the 
                 Install Tool setting ``[GFX][im_noScaleUp]`` isn't activated.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    minHeight
   :Datatype:    Integer
   :Description: A minimum height for the generated image, in pixels. Smaller images will be scaled up, as long as the 
                 Install Tool setting ``[GFX][im_noScaleUp]`` isn't activated.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    maxWidth
   :Datatype:    Integer
   :Description: Maximum width for the generated image. If the source image is wider than this value, it will be 
                 scaled down.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    maxHeight
   :Datatype:    Integer
   :Description: Maximum height for the generated image. If the source image is taller than this value, it will be 
                 scaled down.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    treatIdAsReference
   :Datatype:    Boolean
   :Description: If this value is set to TRUE, then the ViewHelper expects the value given by ``src`` to be a 
                 ``sys_file_reference``. If not, then it expects a ``sys_file`` or regular file path.
   :Standard:    FALSE
   :Mandatory:   No

