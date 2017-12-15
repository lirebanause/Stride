# Stride

Ich werde einfach die zehn Tutorials abschließen, um einen Überblick über Stride zu bekommen. Anschließend werde ich, vorausgesetzt, dass ich dann noch Zeit habe, das ein oder andere Szenario aus dem Buch versuchen, zu programmieren.

### Das Zehn-Schritt-Tutorial

Ich werde mich zur Abwechslung mal genau an die Aufgaben halten und gründlich vorgehen. Also:

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

##### 2.

Ich habe nun eine Move-Methode eingesetzt. Folglich bewegt sich der Actor geradeaus.

##### 3.

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

#### 7. Keyboard Control

Das war tatsächlich nicht so einfach, jedoch nicht aufgrund der Komplexität des Texts, sondern aufgrund von Kleinigkeiten und aufgrund der verblüffenden Einfachheit des Programms. Nachdem ich mit Code,org gearbeitet hatte, habe ich nun nicht erwartet, einfach 
KeyDown "left" mit einer turn-Methode verlinken zu können, und dann klappt es super.
Jedoch musste mich Nele auch mehr oder weniger mit dem Kopf darauf stoßen.

![KeyboardControl](https://github.com/lirebanause/Stride/blob/master/images/KeyControlling.PNG)

#### 8. Tomaten sammeln

Nun geht es daran, den Greep die Tomaten tatsächlich aufheben zu lassen.
Man soll, wie in der Aufgabe beschrieben, das Bild des Actors ändern, verbunden mit einer if-clause. Ich arbeite noch daran, mit einer Variable dafür zu sorgen, dass es nicht bei nur einer Tomate auf seinem Rücken bleibt. Ein Ziel von drei Tomaten tops sollte am besten passen.

![TomatoPickUp](https://github.com/lirebanause/Stride/blob/master/images/TomatoPickUp.png)


#### 9. Tomaten zählen

Nun soll in _"Fields"_ eine Variable zum zählen der Tomaten eingefügt werden. Das habe ich allerdings schon getan. Was genau die jedoch tut, bzw. was sie bringt, weiß ich noch nicht sicher. Ich vermute, dass es dazu da ist, den Bildwechsel des Actors zu kontrollieren, also bei einer aufgehobnenen Tomate das Bild des Greeps mit einer Tomate und bei der zweiten den Greep mit zwei Tomaten einzusetzen, usw. . Ich habe den Wert der Variable jedoch von 0 auf 1 geändert. So weit kann ich jedoch keine Änderung im Programm feststellen.

![CountingVariable](https://github.com/lirebanause/Stride/blob/master/images/Counting%20Variable.PNG)

Es ist nicht, jedenfalls nicht nur die _"Fields"_-Methode nötig. Mir ist nun klar, was tatsächlich von mir verlangt wird und wie ich besagtes umsetzen kann:

![CountingVariable 2](https://github.com/lirebanause/Stride/blob/master/images/Counting%20Variable%202.PNG)

Wenn man nun nach 3 eingesammelten Tomaten den Actor anklickt und inspiziert, kann man die Anzahl der eingesammelten Tomaten
(also z.B. 3) sehen.


#### 10.

Das Bild des Actors soll nun entsprechend der Anzahl der aufgesammelten Tomaten verändert werden. Die Anzahl der gesammelten Tomaten wird definiert durch _private int tomatoes_ . Diese Funktion in eine if-clause einzubauen, was glaube ich, der Weg ist, kriege ich bis jetzt noch nicht hin.

Die Anzahl der aufgesammelten Tomaten als Bedingung in einer _if-clause_ ist durch _"=="_ festgelegt. So kann ich die Anzahl der Tomaten mit einer Zahl **gleichsetzen**.

![SetImageControls](https://github.com/lirebanause/Stride/blob/master/images/SetImageControls.png)

Wie man sehen kann, habe ich jeweils eine neue _if-clause_ für die beiden Bilder "greep-with-food" und "greep-with-more-food" erstellt und für ersteres den Wert _1_ und für drei aufgesammelten Tomaten den Wert _3_ eingesetzt. Folgendes ist das Resultat:

![Greep with more Food](https://github.com/lirebanause/Stride/blob/master/images/Greep%20with%20more%20food.png)

Damit ist die Lernaktivität #1 abgeschlossen.






