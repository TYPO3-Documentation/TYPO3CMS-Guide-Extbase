.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM. ÄÖÜäöüß

.. include:: ../Includes.txt

Dispatcher
==========

The Dispatcher's job is to find a class which can handle the current page request. Once found, the dispatcher executes 
the method *handleRequest* in the matching class and receives the result. This result is then passed out as website 
content.

Here's the dispatcher path, step by step.

RequestHandler
--------------

Extbase innately contains a couple of classes for various webpage requests and makes them available via 
ext_typoscript_setup.txt.::

 config.tx_extbase {
   mvc {
     requestHandlers {
       Tx_Extbase_MVC_Web_FrontendRequestHandler = Tx_Extbase_MVC_Web_FrontendRequestHandler
       Tx_Extbase_MVC_Web_BackendRequestHandler = Tx_Extbase_MVC_Web_BackendRequestHandler
       Tx_Extbase_MVC_CLI_RequestHandler = Tx_Extbase_MVC_CLI_RequestHandler
     }
   }
 }


This is how Extbase provides a *RequestHandler* for requests from the frontend, backend, and Shell/CLI.

Thanks to this TypoScript configuration, you have the possibility of registering your own *RequestHandler*. For 
example, a handler for AJAX requests can be registered here.

The class-specific method *canHandleRequest* decides whether the the request can be handled by its RequestHandler. For 
a *BackendRequestHandler*, the check looks like this::

 canHandleRequest() {
   return TYPO3_MODE === 'BE';
 }
 
 
Because multiple RequestHandlers can be responsible for a request - yours and one from TYPO3 - a prioritisation system 
is necessary. This is because only one RequestHandler can take responsibility. Priority 100 refers to the frontend and 
backend RequestHandler, and 90 to CLI requests. If your RequestHandler needs to take priority, simply set a higher 
numeric priority than the pre-defined options.

RequestBuilder
--------------

Once the definitive RequestHandler has been identified, its method *handleRequest* is executed. This method creates an 
object containing all of the necessary data for the page request, using the *RequestBuilder*. It searches through the 
plugin configuration in ext_localconf.php in order to find out which Controller and Action should be used as standard. 
(Using the method *loadDefaultValues*.) The RequestBuilder also checks the Uri, to check whether an alternative 
Controller or an alternative action should be loaded instead of the entries from ext_localconf.php.

All of the page request data is now collated and made available within the *$reqeust* object.::

 $request = $this->objectManager->create('Tx_Extbase_MVC_Web_Request');
 $request->setPluginName($this->pluginName);
 $request->setControllerExtensionName($this->extensionName);
 $request->setControllerName($controllerName);
 $request->setControllerActionName($actionName);
 $request->setRequestUri(t3lib_div::getIndpEnv('TYPO3_REQUEST_URL'));
 $request->setBaseUri(t3lib_div::getIndpEnv('TYPO3_SITE_URL'));
 $request->setMethod((isset($_SERVER['REQUEST_METHOD'])) ? $_SERVER['REQUEST_METHOD'] : NULL);


Finally, parameters which are specific to the current plugin are added to the $request object as arguments.::

 foreach ($parameters as $argumentName => $argumentValue) {
   $request->setArgument($argumentName, $argumentValue);
 }

RequestHashService
------------------

All data for the current page request is stored in the Request object: now it's time to check that the data is clean. 
The RequestHashService checks whether an argument *hmac* exists in the Request object: this will always be the case 
where data is passed in from a form request. Extbase knows which form data is displayed on the website: if the number 
of fields in the request is different, then the data may have been compromised and so the data processing is prevented. 
If the *hmac* argument isn't present, then the system is dealing with a regular page request and the processing may 
begin.

Response
--------

A Response object is now created, which contains the header data. These include status codes (like *Error 404*), as 
well as the necessary JavaScript and CSS files. This object is empty at this point, ready to be filled by the 
*Dispatcher*.

The Dispatcher
--------------

The Dispatcher fetches the Controller name from the Request object and creates the related object via the method 
*resolveController*. In the example extension *productoverview* referred to within this documentation, the object 
class name is *Tx_Productoverview_Controller_ProductController*.

The object $request and the currently empty object $response are passed to the method *processRequest* in the 
Controller, and the role of the Dispatcher is complete. It waits for the Controller object to return data, then sets 
the appropriate HTTP headers which have been defined during the $response object process. It then returns the 
generated content to the content object *USER* in TypoScript, which returns the content to the client.