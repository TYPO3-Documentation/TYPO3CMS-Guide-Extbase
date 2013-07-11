.. ÄÖÜäöüß 

PHP
===

Auch wenn TYPO3 4.5 noch mit PHP 5.2.* klar kommt, so sollten Sie bei der
Entwicklung von Extbase-Extensions mindestens eine PHP-Version größer 5.3.2
einsetzen.

Seit TYPO3 6.0 gibt es den Support von Namespacing. Da es mit früheren PHP-Versionen
zu Problemen beim Namespacing kommen kann empfehlen wir Ihnen eine PHP-Version größer
5.3.8 zu installieren.

Während TYPO3 4.5 sich noch mit einem memory_limit von 64MB begnügt, sollten es bei
neueren TYPO3-Versionen schon besser 128MB sein.

Falls Sie mit Hilfe von xdebug unterwegs sind, dann kann es Ihnen passieren, dass Sie
ab einer bestimmten Anzahl von verschachtelten Partials folgender Fehler auftaucht::

  Maximum function nesting level of '100' reached, aborting!

Editieren Sie in diesem Fall Ihre php.ini und erhöhen Sie den Wert für die
Verschachtelungen. Die 500 ist ein Vorschlag. Falls es nicht ausreicht, dann setzen
Sie den Wert noch höher (1000)::

  xdebug.max_nesting_level = 500