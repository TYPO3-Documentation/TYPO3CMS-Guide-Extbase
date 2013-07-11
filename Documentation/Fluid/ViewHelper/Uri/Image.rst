.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:uri.image
===========

Eigenschaften
-------------

.. t3-field-list-table::
 :header-rows: 1

 - :Property,20:    Eigenschaft
   :Datatype,20:    Datentyp
   :Description,40: Beschreibung
   :Standard,10:    Standard
   :Mandatory,10:   Mandatory

 - :Property:    src
   :Datatype:    String
   :Description: Pfad und Dateiname zum Bild. Der Pfad muss vom Webroot aus angegeben werden. Konstanten wie EXT:
                 können verwendet werden.
   :Standard:
   :Mandatory:   Ja

 - :Property:    width
   :Datatype:    String
   :Description: Breite des Bildes. Neben einem numerischen Wert können hier auch Angaben mit "c" oder "m" verwendet
                 werden, um das Bild entsprechend zu skalieren.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    height
   :Datatype:    String
   :Description: Höhe des Bildes. Neben einem numerischen Wert können hier auch Angaben mit "c" oder "m" verwendet
                 werden, um das Bild entsprechend zu skalieren.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    minWidth
   :Datatype:    Integer
   :Description: Minimale Breite des Bildes. Falls das Bild kleiner ist, wird es automatisch auf diese Breite
                 vergrößert. Hinweis: Falls Ihr im Installtool [GFX][im_noScaleUp] aktiviert habt,
                 wird das Bild nicht vergrößert.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    minHeight
   :Datatype:    Integer
   :Description: Minimale Höhe des Bildes. Falls das Bild kleiner ist, wird es automatisch auf diese Höhe
                 vergrößert. Hinweis: Falls Ihr im Installtool [GFX][im_noScaleUp] aktiviert habt,
                 wird das Bild nicht vergrößert.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    maxWidth
   :Datatype:    Integer
   :Description: Maximale Breite des Bildes. Falls das Bild größer ist, wird es automatisch auf diese Breite
                 verkleinert.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    maxHeight
   :Datatype:    Integer
   :Description: Maximale Höhe des Bildes. Falls das Bild größer ist, wird es automatisch auf diese Breite
                 verkleinert.
   :Standard:    NULL
   :Mandatory:   Nein

 - :Property:    treatIdAsReference
   :Datatype:    Boolean
   :Description: Wenn TRUE, dann wird die Angabe bei src als sys_file_reference interpretiert. Wenn FALSE als sys_file
                 oder Dateipfad
   :Standard:    FALSE
   :Mandatory:   Nein

