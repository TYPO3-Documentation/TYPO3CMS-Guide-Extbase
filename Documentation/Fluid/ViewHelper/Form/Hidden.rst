.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

f:form.hidden
=============

Mit diesem ViewHelper erstellst Du ein verstecktes Feld. Das ist schonmal nützlich, um Datensatz-UIDs abzulegen,
die der Webseitenbesucher nicht zu sehen braucht, aber für Dich wichtig sind, wenn es darum geht, die eingegebenen
Daten einem Datensatz zuzuordnen, um ihn z.B. zu speichern.

Eigenschaften
-------------

.. include:: ../../UniversalTagAttributes.txt

.. include:: ../../UniversalFormFieldAttributes.txt

Beispiel
--------

::

 <f:form.hidden name="myExtName[ttAddressUid]" value="15" />

oder

::

.<f:form.hidden property="ttAddressUid" value="15" />
