# Projektseite: Fischi aus Klå

## 1. Einführung
* Greenfoot ist eine auf Java basierte Programmiersprache, die gut für Einsteiger geeignet ist. Der Vorteil dieser Programmierumgebung besteht darin, dass grundlegende Methoden(methods) von Greenfoot vordefiniert sind und in alle Projekte importiert werden. Dies erspart einem Anfänger zum einen die mühsame Arbeit, grundlegende Methoden von Grund auf schreiben & verstehen zu müssen, des weiteren ist zum Beispiel eine "move()" - Methode, bei welcher der "Programierer" nur einen Parameter in der Klammer angeben muss, damit der entsprechende Actor sich um genannten Parameter bei Aktivierung der Methode vorwärtsbewegt, deutlich leichter zu verstehen, als der entsprechende "HardCode". Ein weiterer Vorteil für Anfänger besteht in der Objektorientierten Natur, mit der Greenfoot Programme aufgebaut sind. Dank dieser lassen sich Programme, auch für den Laien, deutlich übersichtlicher und einfacher gestalten.
* Fischi aus Klå ist ein Spiel, bei dem der Spieler den Protagonisten "Fischi" steuert. Das Ziel besteht dabei darin, zu versuchen, die anderen Fische zu besiegen und größer zu werden, ohne dabei von anderen Fischen gefressen zu werden. Das Zunehmen an Masse kann der Spieler dabei auf unterschiedlichen Wegen erreichen. Zum einen kann er kleinere, zufällig erscheinende Fische essen, zum anderen besteht die Möglichkeit, sich, bis zu einer gewissen Grenze, ab der der Fischi "genug" davon hat, sich von Seegras ernähren. Der Spieler hat gewonnen, wenn es keine Fressfeinde mehr gibt, die ihm gefährlich werden könnten. 

[Spiel herunterladen](https://www.file-upload.net/download-13787660/FischivonKl1.0.zip.html)

## 2. Code

#### Tastenbelegung
##### Grundsteuerung
Mit den Kontrolltasten "rechts" und "links" kann der Spieler Fischi steuern. Dabei dreht sich Fischi nach links, solange die linke Pfeiltaste gedrückt ist und nach rechts, solange die rechte Pfeiltaste gedrückt ist. drückt der Spieler die obere Pfeiltaste, bewegt er sich nach vorne, drückt er die untere Pfeiltaste, bewegt er sich rückwärts.

Im Code ist diese Grundsteuerung für den Fischi wie folgt umgesetzt:
![Bildschirmfoto 2019-11-15 um 20 06 02](https://user-images.githubusercontent.com/54102146/68968692-834c2e80-07e3-11ea-95f9-447ad9627314.png)
Die "act" Methode ist in Greenfoot die Methode, die in Schleife dauerhaft läuft, wenn entweder "run" oder "act" im Launcher angeklickt wird. "public" heißt, dass alle Klassen auf diese Methode zugreifen können, dann folgt der Rückgabetyp, in diesem Fall "void", der "nichts" bedeutet, da diese Methode keinen "Wert" zurückgeben soll.
Um zu überprüfen, ob der Spieler eine der Steuerungstasten nutzt, laufen in der act-Methode dauerhaft "if-Schleifen", die überprüfen, ob die entsprechende Taste gedrückt ist. Ist das der Fall, gibt die if-Schleife einen "turn" oder "move"-Befehl aus. Die "turn" und "move" Methoden, sowie die boolean- variable "Greenfoot.isKeyDown("KEY")", welche entweder true oder falls ausgibt, sind von Greenfoot importiert und mussten somit von uns nicht definiert werden. In die turn methode kann eine Zahl eingegeben werden, um welche sich Fischi in Grad dreht, in die move Methode, wie eingangs beschrieben, die Distanz, um die Fischi sich bewegen soll. Statt "harten" Werten, haben wurde für die move-Methode die "speed" variable genutzt, welche vorher als private variable mit dem Startwert "4" definiert wurde. <a name="h2"> Dies hat den Vorteil, dass diese Variable später verändert werden kann, um die Geschwindigkeit des Spielers zu ändern, ohne dabei direkt im Code des Spielers Änderungen vorzunehmen. Das gleiche Prinzip wurde für die "turn"-Methode angewandt, wo die variable "Beweglichkeit" eingeführt wurde:
![Bildschirmfoto 2019-11-15 um 20 57 22](https://user-images.githubusercontent.com/54102146/68971766-90205080-07ea-11ea-8d80-5380d22db6c8.png)

Für die flüssige Bewegung war es außerdem wichtig, dass Fischi nicht in der Wand "stecken" bleibt. Bei einer Kollision mit dem Rand der Welt wird deshalb eine 180° Drehung vollzogen. Im Code ist das mit der Boolean-Methode "isAtEdge" in Kombination mit einer weiteren if-Schleife umgesetzt:
![Bildschirmfoto 2019-11-15 um 20 19 00](https://user-images.githubusercontent.com/54102146/68969437-43864680-07e5-11ea-874d-79138c3c7f58.png)
Die isAtEdge boolean-"Abfrage" ist dabei von Greenfoot importiert. Wird die if-Schleife "abgerufen", weil Fischi sich an der Wand der Stage befindet, wird die turn-methode "aktiviert" und Fischi vollführt eine 180° Drehung.

##### erweiterte Steuerungsmöglichkeiten
###### Flash
Fischi ist außerdem in der Lage, nach dem Abklingen eines "cooldowns" eine schnelle Bewegung nach vorne zu vollführen (Im Folgenden "Flash"). Flash wird durch das Drücken der Leertaste ("Space") abgerufen.
Im Code haben wir "Flash" als neue Methode wie folgt definiert:
![Bildschirmfoto 2019-11-15 um 20 31 14](https://user-images.githubusercontent.com/54102146/68970173-f905c980-07e6-11ea-9e45-3a2dd85f428e.png)
Wie im Bild zu sehen ist, bewegt Fischi sich mit der Move Methode um 100 Einheiten nach vorne und der Cooldown wird auf 1000 gesetzt. Cooldown ist dabei eine vorher definierte Variable, die als "int" eine ganze Zahl sein muss.
![Bildschirmfoto 2019-11-15 um 20 31 34](https://user-images.githubusercontent.com/54102146/68970178-fb682380-07e6-11ea-9610-70cfc203a29c.png)
Die Flash-Methode wird, wie die anderen Bewegungs-methoden durch eine if-Schleife in der act Methode von Fischi aktiviert:
![Bildschirmfoto 2019-11-15 um 20 36 26](https://user-images.githubusercontent.com/54102146/68970500-b09adb80-07e7-11ea-9aad-0d737eccc250.png)
In diesem Fall wurde eine "doppelte" if-Schleife verwendet. die von uns definierte Flash-Methode wird abgerufen, wenn die cooldown-Variable den Wert "0" hat. außerdem muss die "Space" Taste gedrückt sein(Greenfoot.isKeyDown("Space").
Neu ist hier außerdem die ""else"-Schleife, welche dann eintritt, wenn der Cooldown nicht null ist. Die if (cooldown==0)-Abfrage also nicht abgerufen wird/ negativ ist. In der else-Schleife wird mit "-=" der Wert "1" von der cooldown-Variable abgezogen. Diese Schleife wird für jeden Lauf der "act" methode durchgeführt, bis der cooldown wieder einen Wert von 0 hat und der Spieler wieder "Flash" nutzen könnte, wodurch der Kreislauf von vorne gestartet würde. 
Eine weitere Besonderheit des "cooldowns" besteht außerdem darin, dass dieser dem Spieler in der Welt angezeigt wird. 
Dies wurde wie folgt realisiert:
![Bildschirmfoto 2019-11-15 um 20 46 08](https://user-images.githubusercontent.com/54102146/68971066-fc9a5000-07e8-11ea-9620-ba5d1425c24e.png)
this.getWorld() ruft die Welt ab, in der der Text angezeigt werden soll. "showText" ist die Methode, die die Welt ausführen soll, "cooldown für Flash" wird bei den hinten als "int" angegebenen Koordinaten angezeigt, "this.cooldown" ist der eigentlich wichtige Teil, weil dieser den aktellen Wert der Variable ausgibt und anzeigt.

###### boost
Die letzte Steuerungserweiterung/veränderung ist der boost. Der boost ist eine kleine Rakete. Sammelt Fischi diese ein, erhält er für kurze Zeit einen Boost in Geschwindigkeit und seitlicher Mobilität/Mumentum.
![Bildschirmfoto 2019-11-15 um 20 58 50](https://user-images.githubusercontent.com/54102146/68971870-c78efd00-07ea-11ea-8154-8ff486b62325.png)
Die obere if Schleife wird aktiviert, wenn "Boostleft", eine vorher eingeführte Variable = 0 ist. Durch diese if-Schleife werden die Werte für "speed" und "Beweglichkeit" auf ihre Startwerte zurpckgesetzt.
In der unteren "if"-Schleife werden die Beweglichkeit und die Geschwindigkeit erhöht, indem die entsprechenden Variablen auf einen höheren Wert gesetzt werden. Diese Schleife wird aber nur abgerufen, wenn "boostleft" größer ist, als 0. <a name="h1"></a>
Dass boostleft auf einen Wert > 0 gesetzt wird wird in der act Methode von Fischi umgesetzt:

![Bildschirmfoto 2019-11-15 um 21 03 56](https://user-images.githubusercontent.com/54102146/68972181-77fd0100-07eb-11ea-87c7-01cf733cab79.png)
Dieser Code befindet sich in der Act-Methode von Fischi. Berührt Fischi einen Actor der "X" Klasse, bei welchen es sich um die beschriebene Rakete handelt, wird die if-Schleife aktiviert. Die boolean- Abfrage "isTouching" ist dabei von Greenfoot vorgegeben, die RemoveTouching-Methode ebenfalls. Wird also die besagte "if-Schleife" abgerufen, wird der aktuell berührte actor der "X"-Raketenklasse entfernt und die variable "boostleft" auf 100 gesetzt. Dies aktiviert die [hier](#h1) beschriebene if-Schleife, wodurch Fischi beschleunigt wird und eine größere Agilität erhält. Damit der Boost() nicht ewig anhält, folgt dem "if" statement, welches überprüft, ob eine Rakete berührt wird, ein "else" Statement, das die boostleft Variabe für jeden "act-cycle" um 1 verringert, bis boostleft schließlich wieder den Wert "0" hat. Außerdem aktiviert diese "else" bedingung die "boost" funkiton, damit diese die werte auf den [hier beschriebenen Standardwert](#h2) zurücksetzt (#h2) 

