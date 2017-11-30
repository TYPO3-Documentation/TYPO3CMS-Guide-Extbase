.. include:: ../../../Includes.txt

f:uri.image
===========

Properties
----------

src
~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Path and file name to the source image. The path must be relative to the project's webroot folder.
    You can also use paths which feature the EXT: convention.

:aspect:`Mandatory`
    Either 'this' or 'image' parameter
    
image
~~~~~

:aspect:`Variable type`
    Object
    
:aspect:`Description`
    An image object.
    
:aspect:`Mandatory`
    Either 'this' or 'src' parameter

width
~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Width of the image. In addition to a numeric value (pixels), you can also add the suffix “c” or “m” in 
    order to crop or scale the generated image. (Check out the imgResource documentation for details.)
    Cropping is changed since Typo3 7.2! Use crop="offsetX,offsetY,width,height" to crop images instead 
    of suffix "c".
    `Learn more. <https://docs.typo3.org/typo3cms/extensions/core/Changelog/7.2/Feature-65584-AddImageCropping.html>`__

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

height
~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Height of the image. In addition to a numeric value (pixels), you can also add the suffix “c” or “m” in
    order to crop or scale the generated image. (Check out the imgResource documentation for details.)
    Cropping is changed since Typo3 7.2! Use crop="offsetX,offsetY,width,height" to crop images instead 
    of suffix "c".
    `Learn more. <https://docs.typo3.org/typo3cms/extensions/core/Changelog/7.2/Feature-65584-AddImageCropping.html>`__

:aspect:`Default value`
    NULL

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
~~~~~~~~~~~
:aspect:`Variable type`
    string

:aspect:`Description`
    Select a cropping variant, in case multiple croppings have been specified or stored in FileReference

:aspect:`Default value`
    'default'

:aspect:`Mandatory`
    No

minWidth
~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    A minimum width for the generated image, in pixels. Smaller images will be scaled up, as long as the
    Install Tool setting ``[GFX][im_noScaleUp]`` isn't activated.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

minHeight
~~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    A minimum height for the generated image, in pixels. Smaller images will be scaled up, as long as the 
    Install Tool setting ``[GFX][im_noScaleUp]`` isn't activated.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

maxWidth
~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Maximum width for the generated image. If the source image is wider than this value, it will be 
    scaled down.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

maxHeight
~~~~~~~~~
:aspect:`Variable type`
    Integer

:aspect:`Description`
    Maximum height for the generated image. If the source image is taller than this value, it will be 
    scaled down.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

treatIdAsReference
~~~~~~~~~~~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If this value is set to TRUE, then the ViewHelper expects the value given by ``src`` to be a 
    `sys_file_reference`. If not, then it expects a ``sys_file`` or regular file path. Not required if `image` parameter is used.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No
