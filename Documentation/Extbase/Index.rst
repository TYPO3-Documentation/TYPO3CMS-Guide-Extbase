.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM. ÄÖÜäöüß

.. include:: Includes.txt

Extbase Guide
=============

What is Extbase?
----------------

Extbase is a framework for TYPO3 extension development. It was introduced with
TYPO3 4.3 in 2009 and is well on the way to entirely replacing the classic way 
of writing TYPO3 extension (pibase). Most important it is a gateway from TYPO3 
CMS to version TYPO3 NEOS as it is a backport of TYPO3 FLOW technology.

Should I use Extbase?
---------------------

If you develop an extension for TYPO3 you should most definitely use Extbase.
The days of piBased extensions are numbered. Extbase gives you the benefit of a
modern, clear and highly structured means of PHP development with a hidden bonus:
if you know Extbase, getting into FLOW3 will be much, much easier. Another bonus: 
porting Extbase extensions to TYPO3 NEOS will be a walk in the park, whereas
porting a piBased extension to TYPO3 NEOS will be incredibly laborious. (If it's even 
possible at all.)

How do I get started with Extbase?
----------------------------------

* Check out the Extbase documentation section.
* Inspect the code of Extbase-based extensions in the The TYPO3 extension repository (TER).

Want to contribute?
-------------------

Do you want to help make Extbase, TYPO3, and the world an even better
place? We would love to welcome you to the team if you want to contribute
in a substantial way.

**Inhaltsverzeichnis**

.. toctree::
   :maxdepth: 1
   :titlesonly:
   :glob:

   FirstExtbaseExtension
   ExtendExtbaseExtension
   Step1Introduction/Index
   Step2SystemCheck/Index
   Step3Documentation/Index
