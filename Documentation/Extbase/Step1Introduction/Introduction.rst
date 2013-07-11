.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM. ÄÖÜäöüß

.. include:: ../Includes.txt

Einführung
==========

Da die TYPO3-Programmierung auf Basis der piBase immer undurchsichtiger wird und
keine klare Struktur bei der Programmierung zu erkennen ist, haben sich die
TYPO3-Entwickler auf die Suche gemacht und überlegt welches System sie in Zukunft für
TYPO3 einsetzen können. Die Entwickler haben sich viele Frameworks angeschaut, aber
überall Defizite gefunden und entschieden ein eigenes Framework aufzubauen und so ist
FLOW3 entstanden.

Dieses FLOW3 wird bzw. ist schon die Basis des neuen TYPO3 5, welches derzeit unter
dem Namen Phoenix durch die TYPO3-Gemeinde wandert. Da FLOW3 eine völlig neue Basis
und auch völlig anders aufgebaut ist, kann FLOW3 nicht von jetzt auf gleich den
derzeitigen TYPO3 4.3 Core ersetzten. Damit aber schon heute Extensions auf Basis des
neuen Systems programmiert werden können, hat man Teile des FLOW3-Systems als
Sysextension. So entstanden die Extensions extbase und fluid. Auf extbase basierende
Extensions laufen auf TYPO3-Versionen ab 4.3 und können später mit nur wenig
Änderungen auf das TYPO3 5 System portiert werden.