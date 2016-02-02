.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM. ÄÖÜäöüß

.. include:: ../Includes.txt

Architecture
============

This reference describes all of the features which Extbase contains innately.

System parts
------------

The Extbase framework is formed of the following parts:

The *TYPO3 Extbase Bootstrap* takes care of the configuration and initialisation of the complete Extbase framework.
The *object manager* creates, caches and connects objects.
The *configuration framework* reads and interleaves the various configurations.

The *Resource module* contains functions for publishing, caching, securing and retrieving resources.
The *HTTP component* is a standards-compliant implementation of a number of RFCs around HTTP, Cookies, content negotiation and more.
The *MVC framework* takes care of requests and responses and provides you with a powerful, easy-to use Model-View-Controller implementation.
The *Cache framework* provides different kinds of caches with can be combined with a selection of cache backends.
The *Error module* handles errors and exceptions and provides utility classes for this purpose.
The *Log module* provides simple but powerful means to log any kind of event or signal into different types of backends.
The *Signal Slot module* implements the event-driven concept of signals and slots through AOP aspects.
The *Validation module* provides a validation and filtering framework with built-in rules as well as support for custom validation of any object.
The *Property module* implements the concept of property editors and is used for setting and retrieving object properties.
The *Reflection API* complements PHP's built-in reflection support by advanced annotation handling and a cached reflection service.
The *Persistence module* allows you to transparently persist your objects following principles of Domain Driven Design.
The *Security framework* enforces security policies and provides an API for managing those.
The *Session framework* takes care of session handling and storing session information in different backends
The *I18n service* manages languages and other regional settings and makes them accessible to other packages and TYPO3 Flow sub packages.
The *Utility module* is a library of useful general-purpose functions for file handling, algorithms, environment abstraction and more.

If you are overwhelmed by the amount of information in this reference, just keep in mind that you don't need to know 
all of it to write your own TYPO3 Flow packages. You can always come back and look up a specific topic once you need to 
know about it - that's what references are for.

Even if you don't need to know everything, we recommend that you get familiar with the concepts of each module and read 
the whole manual. This way you make sure that you don't miss any of the great features TYPO3 Flow provides, and you'll 
feel inspired to produce clean and easy-maintainable code.