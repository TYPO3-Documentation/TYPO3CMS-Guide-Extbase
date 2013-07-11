.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM. ÄÖÜäöüß

.. include:: ../Includes.txt

Dependency Injection
====================

Sehr häufig kommt es vor, dass Objekte von anderen Objekten abhängig sind. So sind
z.B. Objekte, die für Inhaltselemente zuständig sind abhängig von Seitenobjekten.
Also immer wenn wir ein Inhaltsobjekt instanziieren, muss auch das abhängige
Seitenobjekt instanziiert werden. Innerhalb des abhängigen Objektes, in unserem Fall
das Seitenobjekt, sieht man immer wieder einen Konstruktor, der das Objekt
initialisiert. Nicht selten wurden in solchen Konstruktoren weitere abhängige Objekte
eingebunden. Solch ein Objekt könnte zum Beispiel ein Seitenbaumobjekte oder eine Art
Rootlineobjekt sein.

Egal wie Ihr diese abhängigen Objekte nun einbindet, sei es mit new oder
t3lib_div::makeInstance(), spätestens beim Testen Eurer Software werdet Ihr auf
Probleme stoßen. Wollt Ihr innerhalb des Seitenobjektes eine Methode testen, dann
seit Ihr schon bei der Instanziierung diesen Objektes dazu gezwungen auch ein
Seitenbaumobjekt und ein Rootlineobjekt einzubinden, weil diese fest im Konstruktor
verankert sind.

Dieses Problem lässt sich mit Hilfe von Dependency Injections lösen. Innerhalb von
Extbase wurden sämtliche Konstruktore entfernt bzw. überarbeitet und die Einbindung
von abhängigen Klassen wurde in eigene kleine Methoden ausgelagert. Ab jetzt konnte
man das aktuelle Objekt instanziieren OHNE eine Abhängigkeit zu anderen Objekten
herstellen zu müssen.

In Bezug auf phpUnit gibt es sogar noch einen weiteren Vorteil: Ihr könnt nun ein
völlig fremdes Objekt als abhängiges Objekt für Euer Seitenbaumobjekt einbinden. Hier
noch ein besseres Beispiel: Falls Euer abhängiges Objekt ein Datenbankobjekt ist,
könntet Ihr nun phpUnit anweisen z.B. ein Datenbankobjekt einzubinden, dass sich die
Daten aus einer RAM-Tabelle zieht und auch dort wieder zurückschreiben kann. Auf
diese Weise würdet Ihr nicht in die Versuchung kommen beim Testen Eures Programmes
mit den Echtdaten in Kontakt zu kommen.