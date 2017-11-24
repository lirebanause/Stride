# Stride

Das hier wird also ein Neuanfang. Ich werde einfach die zehn Tutorials abschließen, um einen Überblick über Stride zu bekommen. Anschließend werde ich, vorausgesetzt, dass ich dann noch Zeit habe, das ein oder andere Szenario aus dem Buch versuchen, zu programmieren.

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

Habe gerade erfahren, dass der ganze Code noch von Nele und Marit ist, und, dass die eigentliche Aufgabe ist, den Code selbst zu schreiben und nicht den bestehenden zu analysieren...

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
So werden die Tomaten entfernt, wenn sie berührt werden. Das war die Aufgabe. Wie ich es jedoch schaffen soll, dass der Actor die Tomaten mitnimmt, was wahrscheinlich noch eine aufgabe sein wird, weiß ich noch nicht.



