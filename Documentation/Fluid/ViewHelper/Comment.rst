.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:comment
=========

Alles was sich innerhalb des f:comment ViewHelpers befindet, wird schlichtweg entfernt. Evtl. enthaltene ViewHelper
werden nicht ausgeführt.
Dieser ViewHelper ist gerade beim Debuggen von Webseiten sinnvoll. So könnt Ihr damit z.B. f:for-Schleifen temporär
ausblenden, um die Fehlersuche auf das Wesentliche zu beschränken.

Eigenschaften
-------------

Dieser ViewHelper besitzt keine Eigenschaften

Beispiel
--------

::

 <f:comment>
   <p>This text will not be displayed</p>
   <p>My name is: {address.firstName}</p>
 </f:comment>
 <p>{address.firstName} lives in city xyz</p>
 <![CDATA[<p>This text was made by {address.firstName} and will be displayed but not processed.</p>]]>

**Ausgabe**

::

 <p>Stefan lives in city xyz</p>
 <p>This text was made by {address.firstName} and will be displayed but not processed.</p>

.. tip::

   Die letzte Zeile ist etwas Besonderes. Denn mit Hilfe dieser CDATA-Notation, könnt Ihr die Verarbeitung der
   Platzhalter unterbrechen. Der Text wird zwar angezeigt, aber der Platzhalter {address.firstName} wird nicht
   ersetzt. Dies hat gerade dann den Vorteil, wenn Ihr in Eurem Template JavaScript verwendet.