# Projektseite: Fischi aus Klå

## 1. Einführung
* Greenfoot ist eine auf Java basierte Programmiersprache, die gut für Einsteiger geeignet ist. Der Vorteil dieser Programmierumgebung besteht darin, dass grundlegende Methoden(methods) von Greenfoot vordefiniert sind und in alle Projekte importiert werden. Dies erspart einem Anfänger zum einen die mühsame Arbeit, grundlegende Methoden von Grund auf schreiben & verstehen zu müssen, des weiteren ist zum Beispiel eine "move()" - Methode, bei welcher der "Programierer" nur einen Parameter in der Klammer angeben muss, damit der entsprechende Actor sich um genannten Parameter bei Aktivierung der Methode vorwärtsbewegt, deutlich leichter zu verstehen, als der entsprechende "HardCode". Ein weiterer Vorteil für Anfänger besteht in der Objektorientierten Natur, mit der Greenfoot Programme aufgebaut sind. Dank dieser lassen sich Programme, auch für den Laien, deutlich übersichtlicher und einfacher gestalten.
* Fischi aus Klå ist ein Spiel, bei dem der Spieler den Protagonisten "Fischi" steuert. Das Ziel besteht dabei darin, zu versuchen, die anderen Fische zu besiegen und größer zu werden, ohne dabei von anderen Fischen gefressen zu werden. Das Zunehmen an Masse kann der Spieler dabei auf unterschiedlichen Wegen erreichen. Zum einen kann er kleinere, zufällig erscheinende Fische essen, zum anderen besteht die Möglichkeit, sich, bis zu einer gewissen Grenze, ab der der Fischi "genug" davon hat, sich von Seegras ernähren. Der Spieler hat gewonnen, wenn es keine Fressfeinde mehr gibt, die ihm gefährlich werden könnten. 

[Spiel herunterladen](https://www.file-upload.net/download-13787660/FischivonKl1.0.zip.html)

## 2. Code
2.1 Grundbefehle
#### Tastenbelegung
##### Grundsteuerung
Mit den Kontrolltasten "rechts" und "links" kann der Spieler Fischi steuern. Dabei dreht sich Fischi nach links, solange die linke Pfeiltaste gedrückt ist und nach rechts, solange die rechte Pfeiltaste gedrückt ist. drückt der Spieler die obere Pfeiltaste, bewegt er sich nach vorne, drückt er die untere Pfeiltaste, bewegt er sich rückwärts.

Im Code ist diese Grundsteuerung für den Fischi wie folgt umgesetzt:
![Bildschirmfoto 2019-11-15 um 20 06 02](https://user-images.githubusercontent.com/54102146/68968692-834c2e80-07e3-11ea-95f9-447ad9627314.png)
Die "act" Methode ist in Greenfoot die Methode, die in Schleife dauerhaft läuft, wenn entweder "run" oder "act" im Launcher angeklickt wird. "public" heißt, dass alle Klassen auf diese Methode zugreifen können, dann folgt der Rückgabetyp, in diesem Fall "void", der "nichts" bedeutet, da diese Methode keinen "Wert" zurückgeben soll.
Um zu überprüfen, ob der Spieler eine der Steuerungstasten nutzt, laufen in der act-Methode dauerhaft "if-Schleifen", die überprüfen, ob die entsprechende Taste gedrückt ist. Ist das der Fall, gibt die if-Schleife einen "turn" oder "move"-Befehl aus. Die "turn" und "move" Methoden, sowie die boolean- variable "Greenfoot.isKeyDown("KEY")", welche entweder true oder falls ausgibt, sind von Greenfoot importiert und mussten somit von uns nicht definiert werden. In die turn methode kann eine Zahl eingegeben werden, um welche sich Fischi in Grad dreht, in die move Methode, wie eingangs beschrieben, die Distanz, um die Fischi sich bewegen soll.

Für die flüssige Bewegung war es außerdem wichtig, dass Fischi nicht in der Wand "stecken" bleibt. Bei einer Kollision mit dem Rand der Welt wird deshalb eine 180° Drehung vollzogen. Im Code ist das mit der Boolean-Methode "isAtEdge" in Kombination mit einer weiteren if-Schleife umgesetzt:
![Bildschirmfoto 2019-11-15 um 20 19 00](https://user-images.githubusercontent.com/54102146/68969437-43864680-07e5-11ea-874d-79138c3c7f58.png)
Die isAtEdge boolean-"Abfrage" ist dabei von Greenfoot importiert. Wird die if-Schleife "abgerufen", weil Fischi sich an der Wand der Stage befindet, wird die turn-methode "aktiviert" und Fischi vollführt eine 180° Drehung.
