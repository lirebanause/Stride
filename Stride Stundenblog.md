
# Stride Stundenblog

Ich werde einfach die zehn Tutorials abschließen, um einen Überblick über Stride zu bekommen. Anschließend werde ich, vorausgesetzt, dass ich dann noch Zeit habe, das ein oder andere Szenario aus dem Buch versuchen, zu programmieren.

_Doppelstunden sind zu einer Stunde zusammengefasst!_

## Inhaltsverzeichnis

[Erste Stunde](#IVZ1) 

[Zweite Stunde](#IVZ2)

[Dritte Stunde](#IVZ3) 

[Vierte Stunde](#IVZ4)

[Fünfte Stunde](#IVZ5)

[Sechste Stunde](#IVZ6)

[Siebte Stunde](#IVZ7)

[Achte Stunde](#IVZ8)

[Neunte Stunde](#IVZ9)

[Zehnte Stunde](#IVZ10)

[Elfte Stunde](#IVZ11)

[Zwölfte Stunde](#IVZ12)

[13. Stunde](#IVZ13)

[14. Stunde](#IVZ14)

[15. Stunde](#IVZ15)

[16. Stunde](#IVZ16)

[17. Stunde](#IVZ17)



### Erste Stunde<a name="IVZ1"></a>

#### Der Greep

Der Greep wird in der ersten Reihe an Tutorials als Actor fungieren. An ihm werden sich die Aufgaben orientieren.

#### 1. Tutorial

##### 1. 

Der Actor bewegt sich in einer Endlosschleife vorwärts und variiert in den Winkeln, mit denen er, wenn er auf eine Wand trifft, wieder von dieser Wand "abprallt". Da der Actor jedoch an jeder Wand mit jeweils einem selben Winkel abprallt, liegt es nahe, dass der Code vier explizite Winkel enthält, welche in festem Ablauf mit den moveForward_Funktionen gekoppelt sind. Also:

    move(distance)
    turn(A degrees)
    move(distance)
    turn(B degrees)
    move(distance)
    turn(C degrees)
    move(distance)
    turn(D degrees)
    
Und dann wieder von vorne. Ob der Actor automatisch dreht, wenn er auf eine Wand stößt, oder ob die Distances genau abgestimmt sind, weiß ich nicht. Oder natürlich, ich habe komplett unrecht und der Code ist sehr viel komplexer.

![Meet the Greeps](https://github.com/lirebanause/Stride/blob/master/images/Actor%2BMap.PNG)

Habe gerade erfahren, dass der ganze Code noch von Nele und Marit ist, und, dass die eigentliche Aufgabe ist, den Code selbst zu schreiben, und nicht den bestehenden zu analysieren...

Ohne Code passiert dementsprechend natürlich nichts.

### Zweite Stunde<a name="IVZ2"></a>

##### 2.

Ich habe nun eine Move-Methode eingesetzt. Folglich bewegt sich der Actor geradeaus.

##### 3.<a name="test"></a>

Der Actor bewegt sich nun nicht mehr, sondern dreht sich um sich selbst. Welch ein Wunder.

##### 4.

Der Actor bewegt sich im Kreis. Folglich werden der Move-Befehl und der Turn-Befehl nacheinander in einer Schleife abgespielt.

##### 5.

Nun soll der Actor an der Worldborder umderehen. Dementsprechend habe ich eine if-clause benutzt: if_isAtEdge() .
In die if-clause habe ich turn(180) eingetragen. So dreht er sich direkt herum und geht bis zur anderen Border und tut dort das selbe.

##### 6.

Da die nächste Aufgabe darin besteht, Tomaten aufzuheben, muss ich meine Umsetzung der letzten Aufgabe umändern, weil er sonst keine Tomaten berührt. Also habe ich die if-clause geändert: if_isAtEdge() und eingetragen: 
  turn(10)
  move(5)
  turn(15)
  move(5)
  turn(10)
  
So soll erstens das Drehen an der Wand ein wenig mehr smooth werden und zweitens der Ausfallswinkel so sein, dass willkürlich Tomatenberührt werden. Durch den veränderten Winkel verändern sich die Routen des Actors nach jeder Berührung der Border.

###### Nun zur eigentlichen Aufgabe:

Ich habe erneut eine if-clause verwendet: if_isTouching(Tomato.class) und diese Funktion removeTouching(Tomato.class) eingesetzt.
So werden die Tomaten entfernt, wenn sie berührt werden. Das war die Aufgabe. Wie ich es jedoch schaffen soll, dass der Actor die Tomaten mitnimmt, was wahrscheinlich noch eine Aufgabe sein wird, weiß ich noch nicht.

### Dritte Stunde<a name="IVZ3"></a>

#### 7. Keyboard Control

Das war tatsächlich nicht so einfach, jedoch nicht aufgrund der Komplexität des Texts, sondern aufgrund von Kleinigkeiten und aufgrund der verblüffenden Einfachheit des Programms. Nachdem ich mit Code,org gearbeitet hatte, habe ich nun nicht erwartet, einfach 
KeyDown "left" mit einer turn-Methode verlinken zu können, und dann klappt es super.
Jedoch musste mich Nele auch mehr oder weniger mit dem Kopf darauf stoßen.

![KeyboardControl](https://github.com/lirebanause/Stride/blob/master/images/KeyControlling.PNG)

#### 8. Tomaten sammeln

Nun geht es daran, den Greep die Tomaten tatsächlich aufheben zu lassen.
Man soll, wie in der Aufgabe beschrieben, das Bild des Actors ändern, verbunden mit einer if-clause. Ich arbeite noch daran, mit einer Variable dafür zu sorgen, dass es nicht bei nur einer Tomate auf seinem Rücken bleibt. Ein Ziel von drei Tomaten tops sollte am besten passen.

![TomatoPickUp](https://github.com/lirebanause/Stride/blob/master/images/TomatoPickUp.png)

### Vierte Stunde<a name="IVZ4"></a>

#### 9. Tomaten zählen

Nun soll in _"Fields"_ eine Variable zum zählen der Tomaten eingefügt werden. Das habe ich allerdings schon getan. Was genau die jedoch tut, bzw. was sie bringt, weiß ich noch nicht sicher. Ich vermute, dass es dazu da ist, den Bildwechsel des Actors zu kontrollieren, also bei einer aufgehobnenen Tomate das Bild des Greeps mit einer Tomate und bei der zweiten den Greep mit zwei Tomaten einzusetzen, usw. . Ich habe den Wert der Variable jedoch von 0 auf 1 geändert. So weit kann ich jedoch keine Änderung im Programm feststellen.

![CountingVariable](https://github.com/lirebanause/Stride/blob/master/images/Counting%20Variable.PNG)

Es ist nicht, jedenfalls nicht nur die _"Fields"_-Methode nötig. Mir ist nun klar, was tatsächlich von mir verlangt wird und wie ich besagtes umsetzen kann:

![CountingVariable 2](https://github.com/lirebanause/Stride/blob/master/images/Counting%20Variable%202.PNG)

Wenn man nun nach 3 eingesammelten Tomaten den Actor anklickt und inspiziert, kann man die Anzahl der eingesammelten Tomaten
(also z.B. 3) sehen.

### Fünfte Stunde<a name="IVZ5"></a>

#### 10.

Das Bild des Actors soll nun entsprechend der Anzahl der aufgesammelten Tomaten verändert werden. Die Anzahl der gesammelten Tomaten wird definiert durch _private int tomatoes_ . Diese Funktion in eine if-clause einzubauen, was glaube ich, der Weg ist, kriege ich bis jetzt noch nicht hin.

Die Anzahl der aufgesammelten Tomaten als Bedingung in einer _if-clause_ ist durch _"=="_ festgelegt. So kann ich die Anzahl der Tomaten mit einer Zahl **gleichsetzen**.

![SetImageControls](https://github.com/lirebanause/Stride/blob/master/images/SetImageControls.png)

Wie man sehen kann, habe ich jeweils eine neue _if-clause_ für die beiden Bilder "greep-with-food" und "greep-with-more-food" erstellt und für ersteres den Wert _1_ und für drei aufgesammelten Tomaten den Wert _3_ eingesetzt. Folgendes ist das Resultat:

![Greep with more Food](https://github.com/lirebanause/Stride/blob/master/images/Greep%20with%20more%20food.png)

Damit ist die Lernaktivität #1 abgeschlossen.

### Sechste Stunde<a name="IVZ6"></a>

### Lernaktivität 2 (FatCat 1.0)

#### 1. Der Cheat Sheet 

Als erstes wird der Cheat Sheet eingeführt, etwas spät für meine Begriffe, weil ich ihn die ganze Greep-Aktivität hindurch benutzt habe.
Er war jedoch auch bei mir von Anfang an geöffnet, was anscheinend gar nicht hätte sein sollen. So ist diese Aufgabe jedoch größtenteils obsolet.

Meine Beobachtungen sind, dass sich der Cheat Sheet in verschiedenen Umgebungen/ Zeilen verändert. Demnach sind also nicht alle Commands in allen Frames anwendbar.

#### Neuen Inhalt einfügen und wieder löschen

Leere Zeilen, Methoden etc. sind mit der Esc.-Taste wieder zu löschen. Zeilen mit Text können jedoch nicht mit selbiger gelöscht werden. Es muss entweder der Text entfernt oder die Zeile an sich mit der Backspace-Taste gelöscht werden.
Des Weiteren kann eine Zeile durch Rechtsklick und folgend Delete gelöscht werden.

#### Quelltext vorübergehend deaktivieren

Verschiedene Zeilen können markiert und durch Rechtsklick und folgend "Disable" deaktiviert werden und auf selbem Wege, jedoch auf "Enable" wieder aktiviert werden.

### Siebte Stunde<a name="IVZ7"></a>

#### Welche Methoden stehen zur Verfügung ?

Wenn man die Maus auf _inherited from Actor_ bewegt, dann zeigen sich allgemeine Funktionen wie z.B. _move_ oder _turn_. Das sind also Commands, die jede Art von Actor, nicht nur die FatCat, beherrscht.

_Inherited from Cat_ jedoch enthält spezifische Befehle für die FatCat, wie z.B. _dance_ oder _isHungry_.

Es gibt also einen Speicher, wenn man es so nennen möchte, indem die grundlegenen Befehle selbst programmiert sind. Es wird also dem Befehl _move_ die tatsächliche Bewegung des Actors als Bedeutung gegeben. Diese grundlegenen Befehle werden automatisch in jedes neue Szenario eingefügt, sodass der Actor mit diesen Commands gesteuert werden kann, so scheint es.

Der Pfeilkopf nach _extends Cat_ enthält, was die _Inherited from Cat_-Commands angeht, so wie es aussieht, weitesgehend das gleiche.
_Inherited from Actor_ jedoch scheint sehr viel umfangreicher.
Während _Inherited from Cat_ an beiden Stellen die gleiche Anzahl an Commands beinhaltet, sind bei _extends Cat_ mit 25 Commands damit zehn mehr als in der ersten Auflistung (mit Links_Click auf den Actor).

### Achte Stunde<a name="IVZ8"></a>

##### Bird's eye

Wenn man auf **Bird's eye** clickt, fasst sich der Quelltext zu seinen Funktionen zusammen. Wenn man nun auf das guckt, was dabei herauskommt, ähnelt das Resultat sehr _Inherited from Cat_. Eine _walk_-Funktion existiert jedoch noch neben _walk left_ und _walk right_, im Gegensatz zur _Inherited from Cat_-Auflistung.


#### Automatische Quelltextergänzung

Wenn man innerhalb einer Methode Ctrl+Space drückt, dann erscheint ein Fenster mit Methoden, welche verwendet werden können.
Wenn ich nun _I_ drücke, wird das Ergebnis gefiltert. Alles, was mit I anfängt, wird angezeigt.

Dies war die letzte Aufgabe (außer: eine Methode auswählen und wieder entfernen) dieser Lernaktivität.

### Neunte Stunde

### Lernaktivität 3 (FatCat 2.0)

Die Klasse _MyCat_ ist eine Art DNA der FatCat. In ihr sind alle Aktionen, die die Katze durchführen kann, vorprogrammiert, sodass relativ komplexe Aktionen wie Tanzen unter einem einfachen Command _dance_ zusammengefasst sind.

![Cat code](https://github.com/lirebanause/Stride/blob/master/images/Unbenannt.PNG)

Durch ein einfaches Command _"eat"_ ist die Katze unbefristet ein Stück Pizza:

![FatCat eating](https://github.com/lirebanause/Stride/blob/master/images/FatCat%20eating.PNG)

### Zehnte Stunde<a name="IVZ10"></a>

Wenn man an diese Methode die Methode _sleep_ dran hängt, tanzt und schläft die Katze anschließend in einem Loop. 

_Überlege dir eine eigene Routine für die Katze!_

Die Katze liebt es zu tanzen, vor allem, weil das Lied, zu dem sie tanzt, einem eigentlich keine Wahl lässt. Sie tanzt also. Von einer solchen körperlichen Ertüchtigung wird man sowohl hungrig als auch müde.

![FatCat Routine](https://github.com/lirebanause/Stride/blob/master/images/FatCat%20Routine.PNG)

Die Katze tanzt, isst etwas, geht dann schlafen und frühstückt zuletzt, bevor sie wieder Lust auf Tanzen bekommt. So beginnt der Loop von vorn.

_if-Befehle:_

_Lass die Katze schlafen, falls sie müde ist._

Ich erstelle eine _if-method_: _if_ isSleepy_ --> sleep
Jedoch schläft die Katze nicht, weil sie nicht müde ist und nicht müde wird. Wie ich das ändere, weiß ich noch nicht. 

### Elfte Stunde<a name="IVZ11"></a>

Nach einem bitter nötigen Blick in den Code von _Cat_ habe ich verstanden, dass _FatCats_ Handeln tatsächlich Konsequenzen hat. Wenn die Katze tanzt, wird sie müde. Das ist die Lösung.

Ich habe nun versucht, den Großteil des Alltags der Katze mit _if-funktionen_ zu bestimmen. Wenn sie gelangweilt ist, tanzt sie, wenn sie müde ist, schläft sie und wenn sie hungrig ist, isst sie. Mein Problem ist, dass dieser ganze Ablauf nur einmal statt findet. Das Programm ist wie eine Kettenreaktion. Die Katze ist von Anfang an gelangweilt, wodurch diese ganze Kette ausgelöst wird.

### Zwölfte Stunde<a name="IVZ12"></a>

Nach diesem Gespräch mit Ihnen ist mir nun klar, warum (unter anderem natürlich - meine allumfassende Inkompetenz war auch nicht hilfreich) ich mich durchgehend so schwer getan habe. Dass ich eine Methode nicht nur definieren, sondern auch nochmal ausführen muss. Dieses Prinzip ist mir nicht unbekannt, trotzdem hatte ich es mental einfach nicht von Code.org/Gamelab auf Stride übertragen.
Das war so dumm, dass es mir fast peinlich ist...

### 13. Stunde<a name="IVZ13"></a>

##### Aufgabe Neun

Ich habe der Katze verlangte Routine gegeben, sodass sie nun entsprechend ihrer Umwelt und ihrer aktuellen Einstellung agiert.

![Aufgabe Neun Routine](https://github.com/lirebanause/Stride/blob/master/images/Aufgabe%20Neun%20Routine.PNG)

##### Aufgabe Zehn

![Aufgabe Zehn](https://github.com/lirebanause/Stride/blob/master/images/Aufgabe%20Zehn.PNG)

Dieser Act-Methode nach schläft die Katze solange, wie sie allein ist. Bekommt sie Gesellschaft, rufen beide Katzen abwechselnd Hooray.
Wenn man beide Katzen inspiziert, seiht man, dass natürlich beide verschiedene Namen haben: MyCat und MyCat2.
Wie man jedoch in der Methode zwischen den beiden differenziert, sodass bestimmte Funktionen nur für eine der beiden gelten.


### Little Crab

##### 1. Aufgabe

Der Strand ist leer. Der Quelltext der Welt sieht wie folgt aus:

![little crab 1](https://github.com/lirebanause/Stride/blob/master/images/little%20crab%201.PNG)

Wenn ich, wie die Aufgabe es sagt, eine Krabbe in die Welt setze, dann sieht der Quelltext so aus:

![little crab](https://github.com/lirebanause/Stride/blob/master/images/little%20crab%202.PNG)

Man sieht, dass der zweite Teil durch die Krabbe in den Quelltext eingefügt wurde.
In der zweiten Zeile des neune Teils des Quelltextes sieht man die aktuelle Position der Krabbe, angegeben in x - und y-Koordinaten.

##### 2. Aufgabe 

Ich gebe der Krabbe die drei Methoden für _move, turn und isAtEdge_. Wie erwartet bewegt die Krabbe sich und dreht sich um 17*, wenn sie an den Rand der Welt gerät.

### 14. Stunde<a name="IVZ14"></a>

### Kleines Zwischenprojekt

Ich möchte mich für ein paar Informatikstunden von den Aufgaben lösen und selbst ein kleines Fangspiel programmieren, weil ich mich sicherer mit dem Programm fühle.
Das Spiel selbst ist nicht außerordentlich kompliziert. Man selsbt steuert die Krabbe, muss Würmer fressen und darf nicht von Hummern gefangen werden, denn sonst ist das Spiel beendet.

![Fangspiel](https://github.com/lirebanause/Stride/blob/master/images/Fangspiel.PNG)

So sieht momentan der Code der Krabbe aus:

![CrabCode](https://github.com/lirebanause/Stride/blob/master/images/CrabCode.PNG)

Und so der Code der Hummer:

![LobsterCode](https://github.com/lirebanause/Stride/blob/master/images/LobsterCode.PNG)

Das Ändern des Aussehens der Krabbe zu ändern erweist sich als schwerer als gedacht, weil das Ändern der Bilder _crab.png_ und _crab2.png_ nur ein Mal vollzogen wird, während es natürlich eigentlich im Loop ablaufen sollte. Ich habe einen while-loop ausprobiert und auf die condition "isKeyDown" ausgerichtet.

### 15. Stunde

Der Versuch meiner letzten Stunde hat natürlich nicht funktioniert. Tatsächlich hat nichts funktioniert, was ich ausprobiert habe.
Den Würmern habe ich noch ein Extra verpasst. Statt einfach aufgefresssen zu werden, erscheint ein neuer Wurm an einer willlürlichen Stelle in der Welt, jedes Mal, wenn ein Wurm gefressen wird. So wird das Spiel am Laufen gehalten. Ich werde wahrscheinlich noch einen Counter für aufgefressene Würmer einsetzen, ohne ein Limit jedoch. Man soll einfach wissen, wie weit man es geschafft.

### 16. Stunde 

Ich versuche immer noch, die Crab optisch laufen lassen. Als ich erneut nach 20 Minuten aufgeben musste, habe ich deprimiert noch Feinheiten an der Steuerung der Crab und am Movement der Lobsters verändert, um das Gameplay aufzuwerten.

### 17. Stunde

Schließlich habe ich im Internet eine letzte Chance gefunden. Eine if-else-Methode. Während ich diese am Verstehen und Übernehmen war, kamen Sie. Sie haben dann, wie Sie sich sicher noch erinnern, ein entsprechendes Gegenstück aus dem Buch vorgelegt. Dieses habe ich in den Code der Crab eingefügt. Das Resultat:


