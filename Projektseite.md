# Projektseite: Fischi aus Klå

## 1. Einführung
* Greenfoot ist eine auf Java basierte Programmiersprache, die gut für Einsteiger geeignet ist. Der Vorteil dieser Programmierumgebung besteht darin, dass grundlegende Methoden(methods) von Greenfoot vordefiniert sind und in alle Projekte importiert werden. Dies erspart einem Anfänger zum einen die mühsame Arbeit, grundlegende Methoden von Grund auf schreiben & verstehen zu müssen, des weiteren ist zum Beispiel eine "move()" - Methode, bei welcher der "Programierer" nur einen Parameter in der Klammer angeben muss, damit der entsprechende Actor sich um genannten Parameter bei Aktivierung der Methode vorwärtsbewegt, deutlich leichter zu verstehen, als der entsprechende "HardCode". Ein weiterer Vorteil für Anfänger besteht in der Objektorientierten Natur, mit der Greenfoot Programme aufgebaut sind. Dank dieser lassen sich Programme, auch für den Laien, deutlich übersichtlicher und einfacher gestalten.
* Fischi aus Klå ist ein Spiel, bei dem der Spieler den Protagonisten "Fischi" steuert. Das Ziel besteht dabei darin, zu versuchen, die anderen Fische zu besiegen und größer zu werden, ohne dabei von anderen Fischen gefressen zu werden. Das Zunehmen an Masse kann der Spieler dabei auf unterschiedlichen Wegen erreichen. Zum einen kann er kleinere, zufällig erscheinende Fische essen, zum anderen besteht die Möglichkeit, sich, bis zu einer gewissen Grenze, ab der der Fischi "genug" davon hat, sich von Seegras ernähren. Der Spieler hat gewonnen, wenn es keine Fressfeinde mehr gibt, die ihm gefährlich werden könnten. 

[Spiel herunterladen](https://www.file-upload.net/download-13787660/FischivonKl1.0.zip.html)

## 2. Code

### Tastenbelegung
#### Grundsteuerung
Mit den Kontrolltasten "rechts" und "links" kann der Spieler Fischi steuern. Dabei dreht sich Fischi nach links, solange die linke Pfeiltaste gedrückt ist und nach rechts, solange die rechte Pfeiltaste gedrückt ist. drückt der Spieler die obere Pfeiltaste, bewegt er sich nach vorne, drückt er die untere Pfeiltaste, bewegt er sich rückwärts.

Im Code ist diese Grundsteuerung für den Fischi wie folgt umgesetzt:

![Bildschirmfoto 2019-11-15 um 20 06 02](https://user-images.githubusercontent.com/54102146/68968692-834c2e80-07e3-11ea-95f9-447ad9627314.png)

Die "act" Methode ist in Greenfoot die Methode, die in Schleife dauerhaft läuft, wenn entweder "run" oder "act" im Launcher angeklickt wird. "public" heißt, dass alle Klassen auf diese Methode zugreifen können, dann folgt der Rückgabetyp, in diesem Fall "void", der "nichts" bedeutet, da diese Methode keinen "Wert" zurückgeben soll.
Um zu überprüfen, ob der Spieler eine der Steuerungstasten nutzt, laufen in der act-Methode dauerhaft "if-Schleifen", die überprüfen, ob die entsprechende Taste gedrückt ist. Ist das der Fall, gibt die if-Schleife einen "turn" oder "move"-Befehl aus. Die "turn" und "move" Methoden, sowie die boolean- variable "Greenfoot.isKeyDown("KEY")", welche entweder true oder falls ausgibt, sind von Greenfoot importiert und mussten somit von uns nicht definiert werden. In die turn methode kann eine Zahl eingegeben werden, um welche sich Fischi in Grad dreht, in die move Methode, wie eingangs beschrieben, die Distanz, um die Fischi sich bewegen soll. Statt "harten" Werten, haben wurde für die move-Methode die "speed" variable genutzt, welche vorher als private variable mit dem Startwert "4" definiert wurde. <a name="h2"> Dies hat den Vorteil, dass diese Variable später verändert werden kann, um die Geschwindigkeit des Spielers zu ändern, ohne dabei direkt im Code des Spielers Änderungen vorzunehmen. Das gleiche Prinzip wurde für die "turn"-Methode angewandt, wo die variable "Beweglichkeit" eingeführt wurde:
  
![Bildschirmfoto 2019-11-15 um 20 57 22](https://user-images.githubusercontent.com/54102146/68971766-90205080-07ea-11ea-8d80-5380d22db6c8.png)

Für die flüssige Bewegung war es außerdem wichtig, dass Fischi nicht in der Wand "stecken" bleibt. Bei einer Kollision mit dem Rand der Welt wird deshalb eine 180° Drehung vollzogen. Im Code ist das mit der Boolean-Methode "isAtEdge" in Kombination mit einer weiteren if-Schleife umgesetzt:

![Bildschirmfoto 2019-11-15 um 20 19 00](https://user-images.githubusercontent.com/54102146/68969437-43864680-07e5-11ea-874d-79138c3c7f58.png)

Die isAtEdge boolean-"Abfrage" ist dabei von Greenfoot importiert. Wird die if-Schleife "abgerufen", weil Fischi sich an der Wand der Stage befindet, wird die turn-methode "aktiviert" und Fischi vollführt eine 180° Drehung.

#### erweiterte Steuerungsmöglichkeiten
##### Flash
Fischi ist außerdem in der Lage, nach dem Abklingen eines "cooldowns" eine schnelle Bewegung nach vorne zu vollführen (Im Folgenden "Flash"). Flash wird durch das Drücken der Leertaste ("Space") abgerufen.
Im Code haben wir "Flash" als neue Methode wie folgt definiert:

![Bildschirmfoto 2019-11-15 um 20 31 14](https://user-images.githubusercontent.com/54102146/68970173-f905c980-07e6-11ea-9e45-3a2dd85f428e.png)

Wie im Bild zu sehen ist, bewegt Fischi sich mit der Move Methode um 100 Einheiten nach vorne und der Cooldown wird auf 1000 gesetzt. Cooldown ist dabei eine vorher definierte Variable, die als "int" eine ganze Zahl sein muss.

![Bildschirmfoto 2019-11-15 um 20 31 34](https://user-images.githubusercontent.com/54102146/68970178-fb682380-07e6-11ea-9610-70cfc203a29c.png)

Die Flash-Methode wird, wie die anderen Bewegungs-methoden durch eine if-Schleife in der act Methode von Fischi aktiviert:
<a name="linklink">

![Bildschirmfoto 2019-11-15 um 20 36 26](https://user-images.githubusercontent.com/54102146/68970500-b09adb80-07e7-11ea-9aad-0d737eccc250.png)

In diesem Fall wurde eine "doppelte" if-Schleife verwendet. die von uns definierte Flash-Methode wird abgerufen, wenn die cooldown-Variable den Wert "0" hat. außerdem muss die "Space" Taste gedrückt sein(Greenfoot.isKeyDown("Space").
Neu ist hier außerdem die ""else"-Schleife, welche dann eintritt, wenn der Cooldown nicht null ist. Die if (cooldown==0)-Abfrage also nicht abgerufen wird/ negativ ist. In der else-Schleife wird mit "-=" der Wert "1" von der cooldown-Variable abgezogen. Diese Schleife wird für jeden Lauf der "act" methode durchgeführt, bis der cooldown wieder einen Wert von 0 hat und der Spieler wieder "Flash" nutzen könnte, wodurch der Kreislauf von vorne gestartet würde. 
Eine weitere Besonderheit des "cooldowns" besteht außerdem darin, dass dieser dem Spieler in der Welt angezeigt wird. 
Dies wurde wie folgt realisiert:

![Bildschirmfoto 2019-11-15 um 20 46 08](https://user-images.githubusercontent.com/54102146/68971066-fc9a5000-07e8-11ea-9620-ba5d1425c24e.png)

this.getWorld() ruft die Welt ab, in der der Text angezeigt werden soll. "showText" ist die Methode, die die Welt ausführen soll, "cooldown für Flash" wird bei den hinten als "int" angegebenen Koordinaten angezeigt, "this.cooldown" ist der eigentlich wichtige Teil, weil dieser den aktellen Wert der Variable ausgibt und anzeigt.

##### boost
Die letzte Steuerungserweiterung/veränderung ist der boost. Der boost ist eine kleine Rakete. Sammelt Fischi diese ein, erhält er für kurze Zeit einen Boost in Geschwindigkeit und seitlicher Mobilität/Mumentum.

![Bildschirmfoto 2019-11-15 um 20 58 50](https://user-images.githubusercontent.com/54102146/68971870-c78efd00-07ea-11ea-8154-8ff486b62325.png)

Die obere if Schleife wird aktiviert, wenn "Boostleft", eine vorher eingeführte Variable = 0 ist. Durch diese if-Schleife werden die Werte für "speed" und "Beweglichkeit" auf ihre Startwerte zurpckgesetzt.
In der unteren "if"-Schleife werden die Beweglichkeit und die Geschwindigkeit erhöht, indem die entsprechenden Variablen auf einen höheren Wert gesetzt werden. Diese Schleife wird aber nur abgerufen, wenn "boostleft" größer ist, als 0. <a name="h1"></a>
Dass boostleft auf einen Wert > 0 gesetzt wird wird in der act Methode von Fischi umgesetzt:

![Bildschirmfoto 2019-11-15 um 21 03 56](https://user-images.githubusercontent.com/54102146/68972181-77fd0100-07eb-11ea-87c7-01cf733cab79.png)

Dieser Code befindet sich in der Act-Methode von Fischi. Berührt Fischi einen Actor der "X" Klasse, bei welchen es sich um die beschriebene Rakete handelt, wird die if-Schleife aktiviert. Die boolean- Abfrage "isTouching" ist dabei von Greenfoot vorgegeben, die RemoveTouching-Methode ebenfalls. Wird also die besagte "if-Schleife" abgerufen, wird der aktuell berührte actor der "X"-Raketenklasse entfernt und die variable "boostleft" auf 100 gesetzt. Dies aktiviert die [hier](#h1) beschriebene if-Schleife, wodurch Fischi beschleunigt wird und eine größere Agilität erhält. Damit der Boost() nicht ewig anhält, folgt dem "if" statement, welches überprüft, ob eine Rakete berührt wird, ein "else" Statement, das die boostleft Variabe für jeden "act-cycle" um 1 verringert, bis boostleft schließlich wieder den Wert "0" hat. Außerdem aktiviert diese "else" bedingung die "boost" funkiton, damit diese die werte auf den [hier beschriebenen Standardwert](#h2) zurücksetzt.  

Um das einsammeln der für den Boost verantwortlichen Raketen zu erschwären, teleportieren diese sich zu zufälligen Orten auf dem Spielfeld: 

![Bildschirmfoto 2019-11-15 um 21 16 18](https://user-images.githubusercontent.com/54102146/68972923-39684600-07ed-11ea-8c82-8dae318555d4.png)

Die zufällige Teleportation wurde dabei ähnlich wie die Abfrage nach vorhandenem Boost mit Variablen umgesetzt. Zuerst wurde eine Variable "Teleportiercooldown" für die RaketenKlasse "X" eingeführt:

![Bildschirmfoto 2019-11-15 um 21 17 49](https://user-images.githubusercontent.com/54102146/68972996-67e62100-07ed-11ea-8f4e-1d077632ced3.png)

Die Variable für den Teleportiercooldown beträgt zu Beginn 600 act-Zyklen. In der act-Methode der Rakete(n)-Klasse gibt eine if-Schleife den Befehl, die Position um eine zufällige Zahl zu verändern, welche sich innerhalb der Parameter x(0-1200) und y(0-600) befindet, welche die Grenzen der Karte definieren. Diese if-Schleife wird abgerufen, wenn der Wert der "teleportiercooldown"-Variable 0 beträgt. 
Ist dies nicht der Fall, so greift die "else"-Schleife, welche bei jedem act-cycle, in dem teleportiercooldown nicht 0 beträgt, diesen um 1 reduziert.
Diese schleife reduziert den wert also solange, bis eine teleportation stattfindet. In der oberen If-schleife wird dann der Wert wieder erhöht, bis er wieder abgebaut wurde usw.
Die benutzen Methoden setLocation(int, int) und Greenfoot.getRandomNumber(int) sind von Greenfoot importierte Methoden, die nicht definiert werden mussten.

Die Rakete hat außerdem einen dreizeiler Code, welcher ihr Bild auf die gewünschte Größe skaliert:

![Bildschirmfoto 2019-11-15 um 21 23 53](https://user-images.githubusercontent.com/54102146/68973314-40dc1f00-07ee-11ea-9e2a-1a04bac2c3f4.png)

Die erste Zeile definiert "image" als GreenFootimage und ruft dabei das aktuelle Bild des Actors ab, welches vorher, beim Erstellen der Rakete, festgelegt wurde. 
Scale(int, int) is ein Greenfoot Befehl, welcher 2 Werte für int erwartet und das vorher definierte Bild auf diese Werte skaliert. Mit image.getWidth wird die aktuelle Breite von definiertem "image" abgerufen. Da das Ursprungsbild für den Zweck der Rakete zu groß ist, wird von diesem Wert 60 abgezogen. Das Gleiche passiert mit der Höhe (getHeight, -30).
In der 3. Zeile wird dann das neu skalierte Bild als Bild für die Raketenklasse "X" gesetzt.
setImage ist ein Greenfoot Befehl, der das folgende (in diesem Fall unser vorher definiertes "image") als neues Bild für den Actor festlegt.

#### Grundfunktionen 
##### SeeGras
kollidiert Fischi mit SeeGras, dann wird eine if-Schleife aktiviert, welche eine weitere Reihe if-Schleifen auslöst. Wenn die vorher definierte Variable seeGraseaten unter 10 liegt, wird das berührte SeeGras entfernt und "1" zu seegraseaten hinzugefügt. Ist seegraseaten=10, wird wieder das Seegras entfernt, aber zusätzlich die setScale [Methode](#method_setScale) abgerufen, welche den Wert getScale + 1 bekommt. Außerdem wird wieder "1" zu seegraseaten hinzugefügt.
Die 3. Schleife entfernt dann nur noch das Seegras, wenn mehr als 10 SeeGras gegessen wurden. 
Zusammengefasst zählt diese Kombination an if-Schleifen also die "gegessenen" Seegräsern. Wurden 10 Seegräser "gegessen", wird die Größe des Fischis erhöht, danach hat das Essen von Seegräsern keinen Effekt mehr. 

![Bildschirmfoto 2019-11-15 um 21 58 48](https://user-images.githubusercontent.com/54102146/68975294-29536500-07f3-11ea-93b0-617ad713ea23.png)

##### Fische
Fischi (meinFisch) ist eine "subclass" von Fische, was bedeutet, dass Fischi alle Befehle von dieser Klasse "erbt". ["BöserFisch"](#böserFisch), die Klasse für die Gegner unseres Fischis, ist ebenfalls eine subclass von "Fische", was nützlich ist, weil Befehle, wie ["setScale" und "getScale"](#method_setScale) so nicht für beide Klassen einzeln definiert werden müssen und beim Größenvergleich abgerufen werden können. 

"Fische" enthält unter anderem die Methode **setScale** <a name="method_setScale"> 
  Der Zweck dieser Methode besteht darin, die Größe des Fisches, der sie ausführt mit einem Parameter (double) zu skalieren. Für die Nutzung solcher Parameter und auch z.B. für das multiplizieren mit diesem, mussten von Java Befehle/"Tools" importiert werden:
  
  ![Bildschirmfoto 2019-11-15 um 22 19 16](https://user-images.githubusercontent.com/54102146/68976474-1d1cd700-07f6-11ea-959a-84c092799c46.png)

![Bildschirmfoto 2019-11-15 um 22 20 55](https://user-images.githubusercontent.com/54102146/68976522-3887e200-07f6-11ea-85b0-9f37901508a1.png)
 
 setScale beginnt, indem die definierte Variable "scale"
 
 ![Bildschirmfoto 2019-11-15 um 22 22 27](https://user-images.githubusercontent.com/54102146/68976605-7127bb80-07f6-11ea-8d8c-933c7aa2ff57.png)
 
 zum aktuellen "skalierungswert" von "this", also dem Fisch, welcher die methode ausführt, gesetzt wird.
 Danach wird mit `GreenfootImage wachsenderFisch = new GreenfootImage (selbst) ;` der Wert der Variable selbst, welcher das Bild unseres Fisches ist, als neues Bild für "wachsenderFisch" definiert.
 "wachsenderFisch" wird dann mit der bekannten "scale"-Methode und den Parametern "breite" und "höhe" skaliert. Ein Faktor 0.05 sorgt für den richtigen Maßstab. "Breite" und "Höhe" sind wieder vorabgesetzte Variablen:
 
 ![Bildschirmfoto 2019-11-15 um 22 30 25](https://user-images.githubusercontent.com/54102146/68977028-910baf00-07f7-11ea-86f1-02c93093f248.png)
 
 Diese Variablen geben die mit dem GreenfootBefehl `getHeight`/`getWidth` ermittelten Parameter für Breite/ Höhe an. Der in der Methode abgefragte Wert für "Scale" sorgt in der Multiplikation mit "Maßstab" 0.05 und "Breite"/"Höhe" für eine skalierung.
 Final wird das wie gewünscht skalierte "wachsenderFisch" als Bild des actors gesetzt, der die methode ausführt.
 
 die Methode `getScale`fragt den aktuellen Wert für die Variable "scale" ab.
 Diese kann sich verändern, wenn der Fisch wächst [(siehe "setScale")](#method_setScale). Im Code ist dies so umgesetzt:
 
 ![Bildschirmfoto 2019-11-15 um 22 36 22](https://user-images.githubusercontent.com/54102146/68977359-62420880-07f8-11ea-8996-a984e99f82ab.png)
 
 Die Methode ist recht simpel gehalten. Wird sie abgerufen, gibt sie mit `return scale` den aktuellen Wert der "double" Variable "scale" aus.
 
 ![Bildschirmfoto 2019-11-15 um 22 38 17](https://user-images.githubusercontent.com/54102146/68977488-a7663a80-07f8-11ea-81dd-945cb5a052a8.png)

``` 
public Fische(double scale) {
  setScale(scale) ;
  }
 ```
 ...definiert für alle actor der Klasse "Fische", dass diese eine variable "scale" bei der erstellung haben/brauchen, mit der der Fisch bei der erstellung mit dem setScale befehl erstmals skaliert wird.
 
 ##### BöserFisch
moveRandomly ist die Methode, welche für BöserFisch, dem Gegner unseres Fischis, die zufällige Bewegungsrichtung festlegt.

![Bildschirmfoto 2019-11-15 um 22 48 01](https://user-images.githubusercontent.com/54102146/68978024-037d8e80-07fa-11ea-823b-2a5901a3c6ac.png)

Fischi bewegt sich jedes mal, wenn die moveRandomly-Methode abgerufen wird um (2) nach vorne.
Zusätzlich wird eine if-Schleife ausgelöst, welche, wenn eine zufällig aus 1000 gewählte Zahl kleiner ist, als 10, eine weitere if/else Schleife aktiviert wird: Diese lässt sich den bösen Fisch mit einer 50/50 Chance entweder um eine zufällige Zahl von (0-70) nach rechts oder links drehen. 

In der "act"-Methode von BöserFisch wird die definierte "moveRandomly" Methode abgerufen.
Außerdem läuft eine if-Schleife mit dem von [hier](#linklink)










