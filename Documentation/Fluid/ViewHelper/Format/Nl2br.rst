.. include:: ../../../Includes.txt

f:format.nl2br
==============

Dieser ViewHelper besitzt keine Parameter. Den umzuwandelnden Inhalt bezieht er sich aus dem Text zwischen den Tags.
Sinnvoll wird dieser ViewHelper beim Anzeigen von Inhalten aus TEXTAREA-Tags. Denn hier wurden die Zeilenumbrüche mit
ENTER (CHR(10)) realisiert. HTML sind diese Umbrüche aber völlig egal und würde den Text einfach hintereinander weg
anzeigen. Um das zu verhindern könnt Ihr diesen ViewHelper verwender. Er konvertiert alle CHR(10)-Zeilenumbrüche in
<br />-Tags und so werden Zeilenumbrüche auch im Browser wieder richtig dargestellt.

Properties
----------

Dieser ViewHelper besitzt keine Eigenschaften

Beispiel
--------

::

 <f:format.nl2br>Text
 mit
 Zeilenumbrüchen</f:format.nl2br>

ergibt

::

 Text<br />mit<br />Zeilenumbrüchen