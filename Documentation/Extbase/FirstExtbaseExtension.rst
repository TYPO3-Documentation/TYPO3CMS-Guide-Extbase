.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: Includes.txt

Creating an Extbase extension
=================================

Your first extension - step by step
-----------------------------------

First of all, you'll need to put aside your knowledge of piBase programming to understand that programming
in Extbase doesn't begin with code, but in discussions with the client. As a programmer, you need to be clear 
on the client's requirements. The more clarity you achieve at the concept stage, the better you can plan - 
and planning is the alpha and omega of programming for Extbase.

In the following process, you'll create a product overview. On the first page, a list of products, containing links 
to individual detail view pages. Because the number of products can vary a great deal, we'll make a page navigation 
to allow the website visitor to browse through the product catalogue.

.. tip::

   To ensure that the extension can easily be translated from an English base, and in order to avoid issues with 
   special characters, we'll create all of the database column names in English.

Install the Extension Builder
-----------------------------

In order to create a new extension for Extbase, install the Extension Builder (extension_builder) extension using 
the Extension Manager. Once this extension has been activated, a new menu entry *Extension Builder* will appear 
in the backend menu. Click on the new menu entry and you'll be presented with the start page of the *Extension 
Builder*, which explains the first few basic points. At the top of this page, you can switch between the *Introduction* 
and the *Domain Modelling* pages, using the pull-down menu.

Information about your extension
--------------------------------

Having switched to the *Domain Modelling* screen, you'll see a form on the left of the screen, which you can fill 
out with the information about the extension you want to create. To the right is a large, checkered area, which 
we'll explain in a moment.

For the extension we're working on here, add the following information to the form.

- Name: Product Overview

- Key: productoverview

- Description: This extension shows a paginated product overview including a simple single view

- Persons: [Add your own personal information.]

- Frontend plugin:

  * Name: Products

  * Key: products

You'll find the plugin name later in the select box, when you're adding it as page content. The plugin key will be 
combined with the extension key by Extbase, in order to create a unique identifier: productoverview_products.

Create the domain model
-----------------------

You can collapse the extension configuration form using the small arrow (top right of the form) if you like. This 
will reduce the visible area to the checkered section of the page. Drag the small box *New Model Object* and drop it 
anywhere on the checkered background: this will create a new domain model for you to complete. (This is the basis 
of the data you'll be creating, which will contain information about the products you'll create later.)

Click on the text “click to edit” and give the domain model its name: Product. Open the *Domain object settings* section 
and activate the checkbox *Is aggregate root?*. The optional description can be completed too.

Close *Domain object settings* and open *Default actions*, then choose *list* and *show*. These are the different views 
you'll need for outputting the product information in the frontend of the website.

Add 2 new *properties* of type *String*: title and price.

So that the products can be categorised, you'll need to create a new relationship, which will connect the product with its 
categories. Beneath the option *Relations*, add a new entry with the name “categories”. Because the relationship may 
enable multiple categories for each products, choose the option “1:n”.

Create a new domain model by dragging and dropping *New Model Object* again, and call it “Category”. Optionally add 
a description, but don't activate the option *Is aggregate root?* this time. We won't need any “actions” for this 
domain object.

Add a new property of type *String* to the new domain model, named “category”.

You can now drag a line from the category property of the model *Product* to the model *Category*

.. figure:: Images/Domainmodelling.jpg
   :alt: Domainmodelling
   :width: 700

Activate the extension
----------------------

Go to the Extension Manager and activate the extension *productoverview*. Activating the extension will add the necessary 
fields to the database.

Add the plugin to a page
------------------------

Add a new content element of type “General plugin” to a TYPO3 page, and select the option *Product* from the pulldown. If all is well, 
you'll see an empty table with the table headers *title* and *price* in the frontend.

Add a data record
-----------------

In the TYPO3 backend, create a new page of type *folder*. You can create new *Product* records in this folder. So that 
they appear in the frontend, you'll need to tell the plugin where your records are stored. Edit the plugin (content element) and 
switch to the Plugin tab: there you'll find a *record storage page* field, where you can select the new page (of type *folder*) 
you've created. Your product entries will now appear in the frontend.

Have fun with your first Extbase extension!
