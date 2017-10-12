.. include:: ../../../Includes.txt

f:form.checkbox
===============

This ViewHelper creates a checkbox element for use in an HTML form.

Properties
----------

All the :ref:`universal tag attributes <UniversalTagAttributes>`

All the :ref:`universal form field attributes <UniversalFormFieldAttributes>`

Exclusive properties for the HTML-Element
#########################################

disabled
~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Allows the checkbox to appear in an inactive (non-responsive) state.

:aspect:`Default value`

:aspect:`Mandatory`
    No

Exclusive properties of this ViewHelper
#######################################

checked
~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    When active, the checkbox will appear in a checked (active) state.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

multiple
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    Specifies whether the checkbox belongs to a grouped set of multiple checkboxes.

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No



Workaround for an invalid Form object
-------------------------------------

.. tip::

   The following text was pre-existing at the time of this page's translation to English. It may no longer be
   current or relevant in more up-to-date versions of Fluid/Extbase.

Checkbox handling is a catastrophe in Fluid/Extbase. It took me quite a bit of time to get checkboxes working, because
their use requires an empty but available Model if they are to be bound to an object by means of a property::

   No value found for key `Tx_Fluid_ViewHelpers_FormViewHelper->formObject`

In order to get rid of an error message like this one, you'll need to ensure that the object isn't NULL. You'll need to
create an empty object in the relevant Action. You could achieve this using code according to the following example,
which is taken from the extension_builder.

::

 /**
  * action new
  *
  * @param $newCar
  * @dontvalidate $newCar
  * @return void
  */
 public function newAction(Tx_Sffluid_Domain_Model_Car $newCar = NULL) {
   if ($newCar == NULL) { // workaround for fluid bug ##5636
     $newCar = t3lib_div::makeInstance('Tx_Sffluid_Domain_Model_Car');
   }
   $this->view->assign('newCar', $newCar);
 }

The checkbox will only appear once this amendment is in place.

Example without a property
--------------------------

The problem with this method is that you'll have to find out yourself if the checkbox is active or not. You will need
to have already set the values in your Controller, and then apply the state by means of the `checked` attribute. Valid
values at this point are either TRUE (or 1) or  FALSE (or 0).

As this example uses a grouped set of multiple checkboxes, you'll need to add the empty square brackets to the field
name, in order to ensure that the group is maintained and so that the values are submitted as a grouped Array.

::

 <f:form.checkbox name="myExtName[pizza][]" checked="{data.salami}" value="Salami" />
 <f:form.checkbox name="myExtName[pizza][]" checked="{data.hawaii}" value="Hawaii" />
 <f:form.checkbox name="myExtName[pizza][]" checked="{data.tuna}" value="Tuna" />


Example with a property
-----------------------

If you want to avoid the problem above - you should - then bind the checkboxes to an Object property you've defined
in the encompassing `f:form` ViewHelper. Then, your code will look like this.::

 <f:form.checkbox property="pizza" value="Salami" />
 <f:form.checkbox property="pizza" value="Hawaii" />
 <f:form.checkbox property="pizza" value="Tuna" />


Somewhat more elegant, I'm sure you'll agree.

Example of grouped checkboxes
-----------------------------

At the present time, the extension_builder can only create individual checkboxes. This happens when you choose the
field type “Boolean”. If you want to create multiple checkboxes which act together as a group, as in the examples
above, then you'll have to move away from the boolean field type.

This might be a good point to think about whether your code would be better served by creating a relation to a
separate table, and managing the options for the checkboxes in that table. If not - if you want to simply build a group
of checkboxes directly - then you can save the values together in a single database field. Using a grouped set of
multiple checkboxes will mean that you won't be able to edit the data in the Backend. The Backend doesn't currently
allow for a grouped set of multiple checkboxes.

When you create your field in the extension_builder, use the field type “Text”. This creates a field in the database
which can store 65,000 individual characters. Don't forget to write the new type to the database, by means of the
Database Analyzer.

The form will then remain as in the former examples.::

 <f:form.checkbox property="colour" value="yellow" multiple="1" /> yellow<br />
 <f:form.checkbox property="colour" value="brown" multiple="1" /> brown<br />
 <f:form.checkbox property="colour" value="blue" multiple="1" /> blue<br />


Because you can't save an Array directly to the database, you'll have to convert the values which come from the form to
a string. For example, by using the `serialize()` function. The accompanying function `unserialize()` will convert the
values back to an Array when reading the values from the database. Each of these functions can be applied in the
appropriate “getter” and “setter” functions in your Model. ::

 /**
  * @var string
  */
 protected $colour;
 /**
  * @return array $colour
  */
 public function getColour() {
   return unserialize($this->colour);
 }
 /**
  * @param array $colour
  * @return void
  */
 public function setColour(array $colour) {
   $this->colour = serialize($colour);
 }



Add a constructor to the Model, too.::

 /**
  * initializes this object
  *
  * @param string $make
  * @param string $description
  * @param boolean $accident
  * @param array $colour
  */
 public function __construct($make = '', $description = '', $accident = false, array $colour = array()) {
   $this->setMake($make);
   $this->setDescription($description);
   $this->setAccident($accident);
   $this->setColour($colour);
 }


Your group will only be converted to a grouped set of multiple checkboxes through the use of this constructor. Take a
look at the generated HTML code.::


 <input type="checkbox" name="tx_sffluid_sffluid[newCar][colour][]" value="yellow" /><br />
 <input type="checkbox" name="tx_sffluid_sffluid[newCar][colour][]" value="brown" /><br />
 <input type="checkbox" name="tx_sffluid_sffluid[newCar][colour][]" value="blue" /><br />


You can see, by the empty square brackets, that the `colour` field is a grouped set of multiple checkboxes. This also
allows users to edit existing data with no problem at all.