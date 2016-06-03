.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:uri.image
===========

Properties
----------

 - :Property:    src
:aspect:`Variable type`
    String

:aspect:`Description`
    Path and file name to the source image. The path must be relative to the project's webroot folder. 
                 You can also use paths which feature the EXT: convention.
   :Standard:

:aspect:`Mandatory`
    Yes

 - :Property:    width
:aspect:`Variable type`
    String

:aspect:`Description`
    Width of the image. In addition to a numeric value (pixels), you can also add the suffix “c” or “m” in 
                 order to crop or scale the generated image. (Check out the imgResource documentation for details.)

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

 - :Property:    height
:aspect:`Variable type`
    String

:aspect:`Description`
    Height of the image. In addition to a numeric value (pixels), you can also add the suffix “c” or “m” in 
                 order to crop or scale the generated image. (Check out the imgResource documentation for details.)

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

 - :Property:    minWidth
:aspect:`Variable type`
    Integer

:aspect:`Description`
    A minimum width for the generated image, in pixels. Smaller images will be scaled up, as long as the 
                 Install Tool setting ``[GFX][im_noScaleUp]`` isn't activated.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

 - :Property:    minHeight
:aspect:`Variable type`
    Integer

:aspect:`Description`
    A minimum height for the generated image, in pixels. Smaller images will be scaled up, as long as the 
                 Install Tool setting ``[GFX][im_noScaleUp]`` isn't activated.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

 - :Property:    maxWidth
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Maximum width for the generated image. If the source image is wider than this value, it will be 
                 scaled down.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

 - :Property:    maxHeight
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Maximum height for the generated image. If the source image is taller than this value, it will be 
                 scaled down.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

 - :Property:    treatIdAsReference
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If this value is set to TRUE, then the ViewHelper expects the value given by ``src`` to be a 
                 ``sys_file_reference``. If not, then it expects a ``sys_file`` or regular file path.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

