.. include:: ../Includes.txt

===========
Fluid Guide
===========

Introduction
============

What is Fluid?
----------------

Fluid is a PHP template engine, developed independently of TYPO3. It was introduced
back in 2009 with TYPO3 4.3, along with Extbase.

The biggest difference to most other template engines is the valid xml syntax.
Therefore there is no new Syntax to understand.

The engine is available at https://github.com/TYPO3/Fluid and can be used in PHP
projects without TYPO3.

Should I use Fluid?
---------------------

Fluid is the de-facto standard for any HTML based output in TYPO3. It's used by
Extbase extensions by default and is available in TypoScript via
:ref:`t3tsref:cobj-fluidtemplate`.

It is used by the system extension ext:fluid_styled_content, as well, to provide
output of default content elements.

There is even a standalone version of Fluid available,
:php:`TYPO3\CMS\Fluid\View\StandaloneView`, that provides all the means to use Fluid
in a command controller or :php:`AbstractPlugin`.

How to get started with Fluid
-----------------------------

* Check out the Fluid documentation https://github.com/TYPO3/Fluid
* Check out the Fluid documentation section in this guide.
* Inspect the existing Fluid templates, e.g. provided by TYPO3's system extension
  ext:fluid_styled_content https://github.com/TYPO3-CMS/fluid_styled_content .

Concepts
--------

TYPO3 itself requires the Fluid template engine. As this engine does not know
anything about TYPO3, the engine is extended by TYPO3 within the system extension
ext:fluid. This extension provides further ViewHelpers for TYPO3 specifics like link building.

Fluid itself provides a basic **syntax**, which is explained at
https://github.com/TYPO3/Fluid/blob/master/doc/FLUID_SYNTAX.md .
This syntax can be extended, see
https://github.com/TYPO3/Fluid/blob/master/doc/FLUID_EXPRESSIONS.md .

Also Fluid has different levels of **templates**. There is always a *Template*, which can
contain different *Sections*. Also the *Template* can inherit a *Layout*.
For easier re-use *Partials* can be created and rendered within *Layouts* and *Templates*.
For further information on the structure and usage of Fluid check out
https://github.com/TYPO3/Fluid/blob/master/doc/FLUID_STRUCTURE.md .

In TYPO3's extensions the default lookup paths are:

Templates
   Resources/Private/Templates
Layouts
   Resources/Private/Layouts
Partials
   Resources/Private/Partials

But these can be configured through TypoScript via
:ref:`t3tsref:cobj-fluidtemplate-properties-templaterootpaths`,
:ref:`t3tsref:cobj-fluidtemplate-properties-layoutrootpaths` and
:ref:`t3tsref:cobj-fluidtemplate-properties-partialrootpaths`.

To further extend Fluid, there are **ViewHelpers**. These are custom HTML-Tags which
contain PHP Logic.
To understand what they are and how to use them, check out
https://github.com/TYPO3/Fluid/blob/master/doc/FLUID_VIEWHELPERS.md .
If you want to write your own ViewHelpers take a look at
https://github.com/TYPO3/Fluid/blob/master/doc/FLUID_CREATING_VIEWHELPERS.md .

Main Contents
=============

.. toctree::
   :hidden:

   ViewHelper/Index
   UniversalTagAttributes
   UniversalFormFieldAttributes
   ThingsToKnow/Index
   BestPractice/Index
