.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM. ÄÖÜäöüß

.. include:: ../Includes.txt

Der Controller
==============

Der *Controller* steht zwischen den *Modellen* und dem *View* (MVC-Prinzip). Über die Informationen darüber,
wie die *Modelle* mit ein ander verschachtelt sind, kann eine Datenbankabfrage generiert werden,
die die benötigten Daten an den *Controller* ausliefern kann. Der *Controller* schiebt diese Daten dann
1zu1 oder in leicht veränderter Form an den *View* (Fluid) weiter, der sich dann um die eigentliche Ausgabe kümmert.
Seine Hauptaufgabe besteht also nur darin, den Datenfluss zwischen *Modellen* und *View* zu koordinieren.

Der ActionController
--------------------

In dem *ActionController* befinden sich eine oder mehrere Methoden die mit "action" beginnen. Je nach Konfiguration
in der ext_localconf.php oder auch Uri-Parameter wird eine andere *Action* ausgeführt,
die die Inhaltsausgabe verändert. So kann es z.B. eine *Action* geben, die für eine Listenansicht
während eine andere *Action* für die Detailansicht zuständig ist. Es gibt aber auch *Actions*,
die nur für das Erstellen oder auch Bearbeiten und Löschen von Datensätzen zuständig sind.

Der Weg bis zum Aufruf einer Action
-----------------------------------

Welche *Action* aufgerufen wird, entscheiden die Informationen im $request-Objekt,
das über den Dispatcher an den *ActionController* übergeben wurde::

 $controller->processRequest($request, $response);

Jeder *Request* will verarbeitet werden. Denn nur wenn ein *Request* verarbeitet wurde,
geht es im Dispatcher weiter. Der folgende Codeschnipsel zeigt eine Endlosschleife,
die solange wiederholt wird, bis das $request-Objekt als "verarbeitet" markiert wurde. Im Normalfall reicht
ein Durchlauf und das $request-Objekt wird innerhalb der *processRequest* Methode als "verarbeitet" markiert. Aber es
gibt bestimmte Situationen, die diese Information wieder auf "unverarbeitet" setzen. Sowas passiert z.B. wenn
Ihr von einer *Action* zu einer anderen *Action* weiterleitet. Einige *Actions* erwarten ganz bestimmte Parameter,
die zwingend gesetzt sein oder einem ganz bestimmten Datentyp entsprechen müssen. Ist dies nicht der Fall,
spring Extbase wieder zurück zur vorherigen *Action* und führt sie erneut aus. Sollte eine Weiterleitung bestehen,
wird die fehlerhafte *Action* von gerade erneut aufgerufen. Es ist eine Endlosschleife entstanden. Um solche
Fälle zu verhindern dürfen pro Webseitenaufruf und Extension nur 99 Weiterleitungen durchgeführt werden. Ist dieser
Wert erreicht, wird die weitere Ausführung des Scriptes verhindert und eine Fehlermeldung präsentiert::

 while (!$request->isDispatched()) {
   if ($dispatchLoopCount++ > 99) throw new Tx_Extbase_MVC_Exception_InfiniteLoop('Could not ultimately dispatch the request after '  . $dispatchLoopCount . ' iterations. Most probably, a @dontvalidate annotation is missing on re-displaying a form with validation errors.', 1217839467);
   $controller = $this->resolveController($request);
   try {
     $controller->processRequest($request, $response);
   } catch (Tx_Extbase_MVC_Exception_StopAction $ignoredException) {
   }
 }

UriBuilder
::::::::::

Der *UriBuilder* bietet Euch die Möglichkeit an Links zu erzeugen. Sämtliche Einstellungen,
die Ihr in TypoScript hinterlegt habt, werden beim Erstellen von Links berücksichtig. So auch die Konfiguration der
Extension RealUrl, falls installiert.

Der *ActionController* benötigt den *UriBuilder* zum Verlinken auf eine andere *Action*,
die über eine veränderte Uri geladen werden soll: $this->redirect();

Die Action
::::::::::

In der ext_localconf.php werden alle erlaubten *Actions* registriert und nur mit ihrem Namen angesprochen. Zum
Beispiel: list, detail, update, edit, delete. Auch in der Uri werden die *Actions* mit diesem Namen versehen.
Innerhalb des *ActionControllers* werden jedoch Methodennamen in lowerCamelCase-Schreibweise erwartet,
denen ein "Action" angehangen wurde:

Die *Action* "list" muss demnach in den Methodennamen: "listAction" umgewandelt werden::

 $actionMethodName = $this->request->getControllerActionName() . 'Action';

initializeActionMethodArguments
:::::::::::::::::::::::::::::::

Diese Methode liest die Parameter der aufzurufenden *Action* Methode aus und stellt diese als Argumente für die
Action zur Verfügung. Hier ein Beispiel anhand der showAction::

 /**
  * action show
  *
  * @param Tx_Productoverview_Domain_Model_Product $product
  * @return void
  */
 public function showAction(Tx_Productoverview_Domain_Model_Product $product) {
   $this->view->assign('product', $product);
 }

Noch bevor diese Methode aufgerufen wird liest *initializeActionMethodArguments* mit Hilfe der *ReflectionServices*
alle Methodenparameter aus. In diesem Fall $product. Dieser Parameter wird analysiert und unter anderem wird heraus
gefunden, um was für einen Datentyp es sich bei diesem Parameter handelt. Zum Beispiel: String, Integer,
Array aber auf Objekttypen wie "DateTime" werden in diesem Prozess erkannt.

Dieser Parameter wird mit seinen Datentypinformationen in einem Sammelobjekt *Tx_Extbase_MVC_Controller_Arguments*
abgespeichert und steht innerhalb des Controllers als **$this->arguments** zur Verfügung.

.. note::

 Die enthaltenen *Arguments* beinhalten bis hierhin noch keine Werte! Es sind nur Parametername und Datentyp
 gespeichert.

initializeActionMethodValidators
::::::::::::::::::::::::::::::::

Für jeden Parameter innerhalb einer *Action* Methode habt Ihr die Möglichkeit sogenannte *Validators* zu aktivieren.
Auf diese Weise könnt Ihr Extbase anweisen, den Parameter x dahingehend zu testen, ob es sich um einen Parameter vom
Datentyp y handelt. Ist das nicht der Fall wird die Action nicht ausgeführt. Im Folgenden eine Beispiel *Action* mit
einem gesetzten *Validator*::

 /**
  * action show
  *
  * @param Tx_Productoverview_Domain_Model_Product $product
  * @param String $autoMarke
  * @validate $autoMarke String, StringLength(minimum=3,maximum=20)
  * @return void
  */
 public function showAction(Tx_Productoverview_Domain_Model_Product $product, $autoMarke) {
   $this->view->assign('product', $product);
 }

Mit Hilfe der PHPDoc-Annotation "@validate" wurde Extbase nun mitgeteilt, dass der Parameter $autoMarke geprüft
werden soll, ob es sich dabei um einen String handelt und dieser String zwischen 3 und 20 Zeichen lang ist.

Alle definierten Validatoren werden hier an dieser Stelle noch nicht ausgeführt,
sondern nur die Information, dass dieser Parameter gegen diesen Validator geprüft werden soll, den gefundenen
Argumenten in **$this->arguments** hinzugefügt.

initializeAction
::::::::::::::::

Diese *Action* gehört Euch. Alles was Ihr hier rein schreibt, wird VOR dem Aufrufen irgendeiner *Action* ausgeführt.

initializeXXXAction
:::::::::::::::::::

Auch diese *Action* gehört Euch. Als Platzhalter für XXX könnt Ihr eine *Action* angeben. Eine Beispiel Methode
könnte so aussehen: *initializeDetailAction*.

Der Inhalt diese Methode wird nur dann ausgeführt, wenn die angegebene *Action* geladen werden soll.

mapRequestArgumentsToControllerArguments
::::::::::::::::::::::::::::::::::::::::

Egal ob alter oder neuer PropertyMapper. Hier in dieser Methode erhalten die ausgelesenen Action Methodenparameter
die Werte aus dem $request-Objekt::

 foreach ($this->arguments as $argument) {
   $argumentName = $argument->getName();
   if ($this->request->hasArgument($argumentName)) {
     $argument->setValue($this->request->getArgument($argumentName));
   } elseif ($argument->isRequired()) {
     throw new Tx_Extbase_MVC_Controller_Exception_RequiredArgumentMissingException('Required argument "' . $argumentName  . '" is not set.', 1298012500);
   }
 }

Innerhalb von *setValue* geschieht eine ganze Menge Magic. Schaut Euch nochmal diese *Action* hier an::

 /**
  * action show
  *
  * @param Tx_Productoverview_Domain_Model_Product $product
  * @return void
  */
 public function showAction(Tx_Productoverview_Domain_Model_Product $product) {
   $this->view->assign('product', $product);
 }

Egal was Ihr per Formular oder per Uri übergebt: Ihr könnt keine Objekte übertragen! Um trotzdem eine Möglichkeit zu
schaffen, werden entweder die Eigenschaften des Objektes als Array oder,
falls das Objekt schon existiert und eine eindeutige UID aufweisen kann, die UID als Integerwert übertragen. Die
Methode *setValue* geht nun her und prüft, welcher Datentyp vom Formular oder Uri ankommt und in welchen Datentyp der
Wert konvertiert werden muss.

**Datentyp: Integer**

Wenn eine Zahl für den Parameter $product übergeben wird, wird in der Datenbank nach einem Eintrag mit dieser UID
gesucht und die Spalten mit Hilfe des *DataMappers* auf die Eigenschaften des angegebenen Datentyps
(Tx_Productoverview_Domain_Model_Product) übertragen.

**Datentyp: Array**

Beim Anlegen eines neuen Produktes gibt es noch keine UID. Es kommen also alle Eigenschaften als Array an. Auch hier
wird wieder der *DataMapper* aktiv und portiert alle Arrayeinträge auf die Eigenschaften des benötigten Objektes.

Egal, was für ein Datentyp übergeben wurde, der *PropertyMapper* wird versuchen diese Datentypen in den vorgegebenen
Datentyp zu konvertieren. Das hat den Vorteil, dass Ihr als Programmierer ein fertig eingerichtetes Objekt innerhalb
Eurer *Action* zur Verfügung stehen habt.

resolveView
:::::::::::

Für jede *Action* kann ein eigener *View* definiert werden. Dazu müsst Ihr einen *View* mit einem Klassennamen im
folgenden Format erstellen::

 Tx_@extension_View_@controller_@action@format

Ein Klassenname könnte zum Beispiel so aussehen: Tx_Productoverview_View_Product_ShowHtml

Wenn eine solche Klasse jedoch nicht angelegt wurde, dann wird der Standard *View*: *Tx_Fluid_View_TemplateView*
geladen. Kurz: Keine Klasse anzugeben ist das Standardverhalten und läd somit völlig automatisch Fluidtemplates als
Templateengine.

callActionMethod
::::::::::::::::

In dieser letzten Methode wird überprüft, ob die Validatoren (siehe weiter oben) Fehler verursacht haben. Wenn ja,
dann wird ein ErrorHandling ausgeführt, dass die verursachten Fehler auf der Webseite darstellen. Wurden keine Fehler
gefunden wird die *Action* Methode aufgerufen. Wenn die Methode einen Wert zurück gibt,
wird dieser Wert 1zu1 auf der Webseite ausgegeben. Wird kein Wert mit return zurückgeliefert,
dann wird völlig automatisch **$this->view->render** aufgerufen also die Fluid Templates gestartet und geparst. Es
wird dann das Ergebnis aus den Templates an den Dispatcher zurück gegeben.