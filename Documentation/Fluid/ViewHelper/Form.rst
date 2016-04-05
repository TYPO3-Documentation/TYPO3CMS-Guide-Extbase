.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:form
======

The f:form ViewHelper looks pretty mighty, when you look at how many parameters it takes. But once you realize that 11 
of them generate the form target page, you'll see that there are only a few others remaining. The big advantages of this 
ViewHelper are security and a lighter workload. We'll take a look at these in the following examples.

Properties
----------

.. include:: ../UniversalTagAttributes.txt

Global properties of this ViewHelper
####################################

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Property
   :Datatype,20:    Variable type
   :Description,40: Description
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    enctype
   :Datatype:    String
   :Description: The format with which the form data should be encoded and submitted.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    method
   :Datatype:    String
   :Description: Transfer method - GET or POST.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    name
   :Datatype:    String
   :Description: The HTML 'name' attribute of the form.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    onreset
   :Datatype:    String
   :Description: The JavaScript to be executed when the reset button in the form is clicked.
   :Standard:    NULL
   :Mandatory:   No

 - :Property:    onsubmit
   :Datatype:    String
   :Description: The JavaScript to be executed when the submit button in the form is clicked.
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

 - :Property:    action
   :Datatype:    String
   :Description: The action method to be called when the form is submitted.
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    arguments
   :Datatype:    Array
   :Description: Additional variables should be sent with each form submission.
   :Standard:    Empty array
   :Mandatory:   Yes

 - :Property:    controller
   :Datatype:    String
   :Description: If the action method isn't in the same Controller, then you'll need to specify the appropriate Controller.
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    extensionName
   :Datatype:    String
   :Description: If the form submission should be handled by a different extension, this property contains the name of 
                 this extension, without the tx\_ prefix and without underline characters.
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    pluginName
   :Datatype:    String
   :Description: If the form submission should be handled by a different plugin, this property should contain the plugin name.
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    pageUid
   :Datatype:    Integer
   :Description: Define the page UID if the form submission should be sent to a different page.
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    object
   :Datatype:    Mixed
   :Description: Contains an object with properties which mirror the input fields in the form.
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    pageType
   :Datatype:    Integer
   :Description: Use the pageType property to define a non-standard page type to handle the form submission. For example, 
                 where the form submission takes place via AJAX.
   :Standard:    0
   :Mandatory:   Yes

 - :Property:    noCache
   :Datatype:    Boolean
   :Description: Can be used to completely deactivate the page cache on the target page.
   :Standard:    FALSE
   :Mandatory:   Yes

 - :Property:    noCacheHash
   :Datatype:    Boolean
   :Description: If this property is activated, the link to the target page won't contain a cHash parameter.
   :Standard:    FALSE
   :Mandatory:   Yes

 - :Property:    section
   :Datatype:    String
   :Description: Define an anchor on the target page, if the target page contains a large amount of content. The browser 
                 will scroll to the indicated anchor.
   :Standard:    Empty string
   :Mandatory:   Yes

 - :Property:    format
   :Datatype:    String
   :Description: The required data format to be delivered on the target page - for example, “xml”. This property only takes 
                 effect if 'actionUri' isn't set.
   :Standard:    Empty string
   :Mandatory:   Yes

 - :Property:    additionalParams
   :Datatype:    Array
   :Description: Additional variables for the target page. Contrary to 'arguments', these variables won't be prefixed 
                 with the extension name. This property only takes effect if 'actionUri' isn't set.
   :Standard:    Empty array
   :Mandatory:   Yes

 - :Property:    absolute
   :Datatype:    Boolean
   :Description: Upon activation, the domain name and full page path will be prefixed to the form action. This property 
                 only takes effect if 'actionUri' isn't set.
   :Standard:    FALSE
   :Mandatory:   Yes

 - :Property:    addQueryString
   :Datatype:    Boolean
   :Description: This property defines whether query parameters on the page containing the form will be passed on to the 
                 target page. This property only takes effect if 'actionUri' isn't set.
   :Standard:    FALSE
   :Mandatory:   Yes

 - :Property:    argumentsToBeExcludedFromQueryString
   :Datatype:    Array
   :Description: If 'addQueryString' is activated, you can use this property to exclude specific query parameters. This 
                 property only takes effect if 'actionUri' isn't set.
   :Standard:    Empty array
   :Mandatory:   Yes

 - :Property:    fieldNamePrefix
   :Datatype:    String
   :Description: Use this property if you want to use an alternative string to prefix the form fields. Mainly for use 
                 if the form submission is handled by a different extension.
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    actionUri
   :Datatype:    String
   :Description: Define a specific form action URL. Using this option disables many of the other properties (above).
   :Standard:    NULL
   :Mandatory:   Yes

 - :Property:    objectName
   :Datatype:    String
   :Description: An object (Model) name, into which the submitted form data will be saved. This allows the data to be 
                 validated once in the Model, instead of in every individual action method.
   :Standard:    NULL
   :Mandatory:   Yes


Example
--------

::

 <f:form object="{feUser}" objectName="newFeUser">
   <f:form.textarea property="firstName" rows="5" cols="50" />
 </f:form>

…will create (approximately) the following output in the form page HTML.

::

 <form action="/typo3/index.php?id=6&amp;tx__%5Bcontroller%5D=Standard&amp;cHash=d1469ddb628871564f3257920c1f6ee8" method="post">
   <div style="display: none">
     <input type="hidden" name="__referrer[extensionName]" value="" />
     <input type="hidden" name="__referrer[controllerName]" value="Standard" />
     <input type="hidden" name="__referrer[actionName]" value="index" />
     <input type="hidden" name="__hmac" value="a:2:{s:9:&quot;newFeUser&quot;;a:1:{s:9:&quot;firstName&quot;;i:1;}s:4:&quot;tx__&quot;;a:1:{s:10:&quot;controller&quot;;i:1;}}ff5ff9b62f7b5c49a696d3f7b1009991853d6533" />
   </div>
   <textarea rows="5" cols="50" name="newFeUser[firstName]"></textarea>
 </form>

If you take a close look at this generated code, you can see the security elements. Fluid builds a hidden section within 
the form, which contains a few values: amongst them, an '_hmac' value, which contains a reference to all allowed form 
fields. This means that in the event of a website attack, in which specific fields are added or omitted, Extbase can 
compare the form data with the _hmac value to see that the form submission is invalid, and stop processing the request 
immediately with an error message.

In the earlier example, we've set the object name “newFeUser”. As you can see, this value is prepended to each field. The 
advantage of this is that all of you form fields are bundled together into an array for the target page. Your action can 
take this array and port it into a Model object, during which the array entries are validated. (Assuming that the Model 
contains the appropriate validation definitions.) The form data will only be accepted into the Model if it can be 
validated, after which a simple, single command could store the data in the database.