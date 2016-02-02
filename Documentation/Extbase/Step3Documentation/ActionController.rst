.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM. ÄÖÜäöüß

.. include:: ../Includes.txt

The Controller
==============

The *Controller* stands between the *Model* and the *View* (according to MVC principles). A data request - for example 
to a database - can be made through the Model; the Controller passes this data - with or without manipulation - to the 
View (*Fluid*), which is responsible for preparing the actual output. The main role of a Controller is therefore to 
coordinate the flow of information between the Model and the View.

The ActionController
--------------------
The *ActionController* contains one or more methods whose names begin with *action*. Depending on the configuration in 
ext_localconf.php or upon URI parameters, an appropriate action will be executed to modify or control the output. For 
example, there might be an *action* for a list view, with a second action for a detail view. There might also be actions 
which are responsible for the creation, modification or deletion of data via the front end.

The path to the execution of an action
--------------------------------------
The choice of action is decided by the information in the $request object, which is passed to the ActionController via 
the Dispatcher::

 $controller->processRequest($request, $response);

Each request has to be parsed - the process reaches the Dispatcher only once the request has been parsed. The following 
code example creates a repeating loop, which will continue indefinitely until the $request object is marked as having 
been parsed. One pass is usually sufficient and the $request object is marked as parsed within the *processRequest* 
method. There may be situations in which the information is re-marked as unparsed - this can happen when an action 
redirects to a second action.

Some actions expect definite parameters, which must be defined or which must be of a certain type. Wherever this 
criteria isn't matched, Extbase falls back to the former action and runs it a second time, which in turn runs the second 
action again; thereby creating an endless loop.

In order to avoid such situations, Extbase only allows a maximum of 99 executions per website request and extension. 
If this limit is reached, the system stops processing the script and throws an exception message::

 while (!$request->isDispatched()) {
   if ($dispatchLoopCount++ > 99) throw new Tx_Extbase_MVC_Exception_InfiniteLoop('Could not ultimately dispatch the request after '  . $dispatchLoopCount . ' iterations. Most probably, a @dontvalidate annotation is missing on re-displaying a form with validation errors.', 1217839467);
   $controller = $this->resolveController($request);
   try {
     $controller->processRequest($request, $response);
   } catch (Tx_Extbase_MVC_Exception_StopAction $ignoredException) {
   }
 }

UriBuilder
::::::::::

The *UriBuilder* offers you the possibility to create links. Any configuration defined in TypoScript are respected, so 
that (for example) the configuration in the extension RealUrl is implemented, if it's installed.

The *ActionController* needs the *UriBuilder* to create links to a secondary *action*, which should be loaded via an 
alternative Uri: $this->redirect();

The Action
::::::::::

All allowed Actions are registered in ext_localconf.php and thenceforth only referenced by name. For example, *list*, 
*show*, *detail*, *update*, *edit*, *delete*. These names are also used within the page Uri. Within the 
ActionController, a lowerCamelCase name is required for every action: for example, the action *list* refers to the 
method *listAction*::

 $actionMethodName = $this->request->getControllerActionName() . 'Action';

initializeActionMethodArguments
:::::::::::::::::::::::::::::::

This method reads out the parameters of the requested action and makes them available as arguments. Here's an example, 
based on a *showAction*::

 /**
  * action show
  *
  * @param Tx_Productoverview_Domain_Model_Product $product
  * @return void
  */
 public function showAction(Tx_Productoverview_Domain_Model_Product $product) {
   $this->view->assign('product', $product);
 }

*initializeActionMethodArguments* reads out the method parameters using the *ReflectionService*, even before the method 
is called - in this case, $product. This parameter is analysed and amongst other parsing, its type is identified. (For 
example, *String*, *Integer*, *Array* or object types like *DateTime*. The parameter is then stored along with its 
type information in the collective object *Tx_Extbase_MVC_Controller_Arguments*, which is available within the 
controller (and hence action methods) as **$this->arguments**.

.. note::

 The *arguments* in this array don't contain their values at this stage: just the parameter name and data type.

initializeActionMethodValidators
::::::::::::::::::::::::::::::::

You have the opportunity to add *validators* to each parameter within each action. For example, you can instruct Extbase 
to test parameter *x* and make sure its data type is *y*. If an invalid parameter type has been passed in, then the 
action won't be executed. Here's an example.::

 /**
  * action show
  *
  * @param Tx_Productoverview_Domain_Model_Product $product
  * @param String $manufacturer
  * @validate $manufacturer String, StringLength(minimum=3,maximum=20)
  * @return void
  */
 public function showAction(Tx_Productoverview_Domain_Model_Product $product, $manufacturer) {
   $this->view->assign('product', $product);
 }

Extbase is told, through the PHPDoc annotation "@validate", that the parameter $manufacturer should be checked. In this 
example, it must be a valid String, with a length of between three and twenty characters.

Not all validators will be executed at this point: only the ones that apply to parameters which are to be added to the 
array **$this->arguments**.

initializeAction
::::::::::::::::

The content of this action is up to you: all all of the code in this action will be executed before EVERY specific 
action method.

initializeXXXAction
:::::::::::::::::::

This action method is yours, too. Replace XXXX with your own action name: for example, *initializeDetailAction*. This 
method will then be executed before the related action. (In this example, *detailAction*.)

mapRequestArgumentsToControllerArguments
::::::::::::::::::::::::::::::::::::::::

As the name suggests, this method reads the values from the $request objects and assigns them as method parameters to 
the applicable action.::

 foreach ($this->arguments as $argument) {
   $argumentName = $argument->getName();
   if ($this->request->hasArgument($argumentName)) {
     $argument->setValue($this->request->getArgument($argumentName));
   } elseif ($argument->isRequired()) {
     throw new Tx_Extbase_MVC_Controller_Exception_RequiredArgumentMissingException('Required argument "' . $argumentName  . '" is not set.', 1298012500);
   }
 }


A whole load of magic takes place within *setValue*: have a look at the following action.::

 /**
  * action show
  *
  * @param Tx_Productoverview_Domain_Model_Product $product
  * @return void
  */
 public function showAction(Tx_Productoverview_Domain_Model_Product $product) {
   $this->view->assign('product', $product);
 }


Whatever gets passed via form or Uri, you can't transfer objects. In order to bypass this rule, an array containing 
details of the object - or the UID of the object, if it already exists - are passed instead. The method *setValue* 
checks and identifies the data type being passed and the data type to which it must be converted.

**Data type: Integer**

Where the parameter $product is passed as a number, a matching database entry is fetched and transferred to the data 
type Tx_Productoverview_Domain_Model_Product via *DataMappers*.

**Data type: Array**

There is no UID when creating a new product. Instead, all parameters are passed as an array. The *DataMapper* is active 
here too, porting all array entries to the attributes of the required object. Whichever data type is passed, the 
*PropertyMapper* attempts to convert it into the correct data type for the object attribute. Through this, the 
programmer has the advantage of a complete, correctly configured object within the *action*.

resolveView
:::::::::::

You can define a unique *View* for every action - in order to do so, you need to create the view with its own class 
name, according to the following format::

 Tx_@extension_View_@controller_@action@format

An example class name would therefore be Tx_Productoverview_View_Product_ShowHtml

If this class isn't created, the standard *View* class takes effect: *Tx_Fluid_View_TemplateView*. In short: if you 
don't create your own class, then the standard process takes over and Extbase loads the appropriate Fluid template 
automatically.

callActionMethod
::::::::::::::::

Finally, this method handles any errors which have been thrown by the validators. If so, then ErrorHandling kicks in 
and a suitable error message is displayed in the front end. If there are no errors, the action method is executed. If 
the method returns a value, this will be shown in the front end. If no value is returned, then **$this->view->render** 
is executed: this leads to the Fluid Templating Engine parsing the template/s and returning the result to the 
Dispatcher.