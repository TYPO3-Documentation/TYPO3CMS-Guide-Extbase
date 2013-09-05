.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

.. _f-format-cdata:

f:format.cdata
==============

Dieser ViewHelper ummantelt einen Text oder eine Variable mit CDATA. Das wird gerade dann interessant,
wenn Ihr z.B. eine RSS-Ausgabe mit Hilfe von Extbase und Fluid programmiert. Da solche Ausgaben auf XML basieren, ist
es wichtig HTML-Tags innerhalb dieser XML-Ausgabe zu maskieren.

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    value
   :Datatype:    String
   :Description: Der Text, der mit CDATA ummantelt werden soll
   :Standard:    NULL
   :Mandatory:   Nein

Beispiel mit Text:
------------------

::

 <f:format.cdata>Text, der ummantelt werden soll</f:format.cdata>

wird zu

::

 <![CDATA[Text, der ummantelt werden soll]]>

Beispiel mit Variablen:
-----------------------

Als Beispiel übergeben wir etwas untypisch HTML und Text vom Controller aus::

 $this->view->assign('variable', '<strong>Stefan</strong>');

Im Fluidtemplate wickeln wir die Variable in CDATA ein::

 <f:format.cdata>{variable}, die ummantelt werden soll</f:format.cdata>

Als Ergebnis erhaltet ihr::

 <![CDATA[<strong>Stefan</strong>, die ummantelt werden soll]]>

.. important::

   Wie Ihr im Ergebnis sehen könnt, wird die Variable 1zu1 ausgegeben. Der Inhalt wird nicht durch htmlspecialchars
   geschleust oder sonst in irgendeiner Form maskiert. Bitte beachtet diese Vorgehensweise gerade in Hinblick auf
   XSS-Attacken.