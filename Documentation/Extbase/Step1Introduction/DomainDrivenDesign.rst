.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.  ÄÖÜäöüß

.. include:: ../Includes.txt

Domain Driven Design
====================

Ohne Struktur kann der Quellcode einer Software echt wüst aussehen. Wir haben
Extensions gesehen die insgesamt 3 PDF-Generatoren beinhaltet haben. Wusste der
Programmierer nicht mehr, dass er einen PDF-Generator implementiert hatte? Oder
musste der PDF-Generator in einem Teilbereich etwas anderes arbeiten/interagieren?
Wir wissen es nicht. Aber wenn dieser Programmierer irgendwann einmal wieder an
seinem PDF-Generator arbeitet und einen Fehler behebt, wird er diesen dann auch für
die beiden anderen PDF-Generatoren entfernen?

Viele Programmierer haben schon sehr früh erkannt, dass es zwingend nötig ist
Quellcode zu strukturieren bzw. die Teilbereiche einer Software wie z.B. die
PDF-Generierung, die Anbindung an eine Datenbanktabelle, das Schreiben von
Logdateien oder dem Versand einer E-Mail in eigene Objekt den sogenannten
Domainmodellen zu kapseln.

Dieses Prinzip der Planung und Programmierung nennt man Domain Driven Design. Dies
hat den Vorteil, dass sich der Programmierer immer auf ein spezielles Problem
konzentrieren kann. Programmiert er gerade an dem PDF-Generator, dann werden ihm
keine Teilbereiche aus der Logging-Domain oder aus der Datenbankanbindung in die
Quere kommen. Auch Extbase selbst arbeitet nach diesem Prinzip. So brauchen Sie sich
als Programmierer keine Gedanken darüber zu machen, wie Sie an die benötigten Daten
für eine Ausgabe kommen. Mit Hilfe von Validatoren innerhalb des Domainmodels können
Sie das Model anweisen sich selbst zu überprüfen. Wird das Model wo auch immer im
Quellcode z.B. ungültig wird es nicht weiter verarbeitet bzw. wird nicht in der
Datenbank abgespeichert.

Domain Driven Design sollte schon während dem Gespräch mit dem Kunden angewendet
werden. Erst dadurch können die jeweiligen Problemfälle, die der Kunde durch Ihr
Programm gelöst haben will, visuell dargestellt werden. Alle Eigenschaften und
Methoden werden mit dem Kunden besprochen und es wird eine einheitliche Sprache
zwischen Ihnen und dem Kunden erstellt (Ubiquitous Language). Entscheiden Sie sich
also bei der Debitorennummer für das Kürzel dNr, dann ist das IMMER die
Debitorennummer und wenn der Kunde auf einmal mit debNr oder dNummer ankommt, dann
ist dies für das aktuelle Projekt eine völlig neue Eigenschaft. Beim Bilden dieser
gemeinsamen Sprache sollten Sie sich auf die englische Sprache einigen, da viele
Fremdsprachen mit ihren Umlauten häufig zu Problemen führen.