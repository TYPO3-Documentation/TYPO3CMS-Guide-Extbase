.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

f:image
=======

Die Arbeit, die man sich normalerweise umständlich in einer Extension oder im TS machen musste gibt es nun fertig
als ViewHelper und die Bilder werden nicht einfach nur verkleinert dargestellt. Nein! Sie werden mit Hilfe von PHP-GD
und/oder imagemagick auf die hier angegebene Größe verkleinert.

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
   :Description: Pfad zu der Datei. Hier kann auch mit EXT: gearbeitet werden, da es sich hier um ein IMG_RESOURCE handelt
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    width
   :Datatype:    String
   :Description: Breite des Bildes. Hier kann z.B. mit einem angehangenen "c" gesagt werden, dass das Bild, falls die Proportionen nicht genau passen geschnitten wird. Z.B. 200c
   :Standard:    NULL
   :Mandatory:   Ja

 - :Property:    height
   :Datatype:    String
   :Description: Höhe des Bildes. Hier kann z.B. mit einem angehangenen "c" gesagt werden, dass das Bild, falls die Proportionen nicht genau passen geschnitten wird. Z.B. 100c
   :Standard:    NULL
   :Mandatory:   Ja

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

Beispiel in Originalgröße
-------------------------

::

 <f:image src="fileadmin/bilder/landschaft.jpg" alt="landschaft" />

Beispiel: Beibehaltung der Proportionen
---------------------------------------

::

 <f:image src="fileadmin/bilder/landschaft.jpg" alt="landschaft" width="50" />

Beispiel: Geschnittenes Bild
----------------------------

::

 <f:image src="fileadmin/bilder/landschaft.jpg" alt="landschaft" width="100c" height="100c" />

Die kürzere Seite wird auf 100 Pixel gesetzt und bei der längeren Seite wird nach 100 Pixeln einfach abgeschnitten.