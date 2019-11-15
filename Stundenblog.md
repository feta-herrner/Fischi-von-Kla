# Informatikprojekt 1: Stundenblog

### Übersicht
<details>
  <summary>August</summary>
  
##### [13.08.19](#1308)
##### [14.08.19](#1408)
##### [15.08.19](#1508)
##### [20.08.19](#2008)
##### [21.08.19](#2108)
##### [27.08.19](#2708)
##### [28.08.19](#2808)
##### [29.08.19](#2908)


</details>
<details>
  <summary>September</summary>

##### [11.09.19](#1109)
##### [12.09.19](#1209)
##### [24.09.19](#2409)
##### [25.09.19](#2509)
##### [26.09.19](#2609)


</details>
<details>
  <summary>Oktober</summary>
  
##### [01.10.19](#0110)  
##### [02.10.19](#0210)
##### [22.10.19](#2210)
##### [23.10.19](#2310)
##### [24.10.19](#2410)
##### [29.10.19](#2910)

</details>
<details>
  <summary>November</summary>
  
##### [05.11.19](#0511)
##### [06.11.19](#0611)
##### [07.11.19](#0711)
##### [12.11.19](#1211)
##### [14.11.19](#1411)
  
</details>  


#### 13.08.19 <a name="1308"></a> 
Heute hat Herr Buhl uns eine Einführung in den Informatikunterricht gegeben. Wir haben erfahren, welche Ziele und Aufgaben uns im kommenden Jahr erwarten. Danach hatten wir kurz Zeit, uns in Zweierteams zusammenzufinden und erste Ideen für Projekte aus seinem Leitfaden zu entnehmen. 

#### 14.08.19 <a name="1408"></a> 
Heute war unsere erste "richtige" Informatikstunde, die wir dafür genutzt haben, einen Github Account und ein repository für unser Informatikprojekt zu erstellen, in welchem wir die Dokumente für Stundenblog und Stundenprotokoll erstellt haben. Wir haben uns anschließend im Internet über die Programmiersprache markdown informiert, bei welcher es sich um eine vereinfachte Auszeichnungssprache handelt, welche auf Github verwendet wird. Mit unserem neuen Wissen aus dem Internet haben wir begonnen die ersten Stundenprotokolle zu verfassen, welche wir zuhause beendet haben.
Für die kommende Informatikstunde haben wir uns vorgenommen, die ersten Schritte in unserem Projekt zu machen und hatten auch schon eine Idee, wie das aussehen könnte.

#### 15.08.19 <a name="1508"></a> 
Heute haben wir die Stunde damit begonnen, uns im Internet über Arduino zu informieren. Mit unserer Idee einer automatischen Pflanzenwässerungsanlage für Lottas Aloe Vera im Hinterkopf, haben wir uns dann entschieden, uns zuerst einmal mit den "Basics" von Arduino vertraut zu machen. Wir haben von Herrn Buhl einen Arduino ausgeliehen und waren eine Weile damit beschäftigt, das Vorprojekt auseinanderzubauen. Danach haben wir nach Online Tutorials und Informationen für Arduino Basics gesucht und beschlossen, [diesem](https://learn.sparkfun.com/tutorials/what-is-an-arduino/all) Tutorial nachzugehen, in welchem Arduino grundlegend erklärt wird und wir am Ende in der Lage sein sollen, eine Glühbirne zum Leuchten zu bringen.
Zunächst wurden wir auf [diese](https://learn.sparkfun.com/tutorials/installing-arduino-ide) Seite weitergeleitet, auf welcher wir Treiber und Programmierumgebung für den Arduino herunterladen sollten. Diese haben wir installiert.
Für die nächste Stunde haben wir uns vorgenommen, da es zeitlich knapp wurde, das Tutorial durchzustarten.


#### 20.08.19 <a name="2008"></a> 
Heute sind wir unserem Vorsatz der letzten Stunde nachgegangen, uns mit Arduino vertraut zu machen. Nützlicherweise war im Anschluss an die [Installationsanleitung](https://learn.sparkfun.com/tutorials/installing-arduino-ide) auch ein Tutorial beigefügt, in welchem wir ein **Beipsielskript**

```
  void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  digitalWrite(LED_BUILTIN, HIGH);
  delay(1000); 
  digitalWrite(LED_BUILTIN, LOW);
  delay(1000); 
}
```
fanden, welches eine Glühbirne zum leuchten bringt. Wir haben gelernt, wie man dieses und andere Skripts auf den Arduino hochlädt und auch, in welchem Rythmus und unter welchen Umständen die Skripts ausgeführt werden.
<!--- hier lieber ein Bild? --->
Da wir nun wussten, wie man Skripts schreibt und hochlädt und das "Blink"-Beispielskript das Gleiche wie in unserem [Arduino-Tutorial](https://learn.sparkfun.com/tutorials/what-is-an-arduino) ist, haben wir beschlossen, nächste Stunde zu diesem zurückzukehren, weil die Zeit mal wieder etwas knapp wurde.
Im Tutorial wurde uns vor der Ersten Auseinandersetzung mit demselben etwas [Lesestoff](#Lesestoff) beigefügt und nahegelegt, um eine leichtere Zeit in der Programmierung zu haben. Da wir blutige Anfänger im physical computing sind hielten wir das für eine gute Idee und haben uns die verlinkten Artikel als Hausaufgabe aufgegeben.
BILD

<a href="google.com" target="_blank">Google</a>

#### 21.08.19 <a name="2108"></a> 
Leider haben wir uns gezwungen gesehen, das Projekt zu verwerfen, da es online schon hunderte von Tutorials (zum Beispiel [dieses](https://youtu.be/pYLfcOB5ars) für Arduino-Bewässerungsanlagen gibt und es daher sehr schwierig wäre etwas eigenes oder etwas neues zu entwickeln. Auch bezüglich verschiedener Sensorenkombinationen gab es schon alle Möglichkeiten als genaue Anleitung. Da wir physical computing eigentlich sehr interessant finden, haben wir damit angefangen ein neues Projekt zu finden.
  


#### 27.08.19 <a name="2708"></a> 
Als wir beim Brainstorming Tee getrunken haben, ist uns aufgefallen, dass wir fast immer vergessen, den Teebeutel zur richtigen Zeit aus dem Wasser zu ziehen. Weil wir etwas alltagstaugliches mit Arduino machen wollen, kam uns die Idee, einen automatischen Teebeutelentferner mit Zeitschaltung zu programmieren. Im Internet sind wir auf ein [ähnliches Projekt](https://www.kreativekiste.de/tee-wecker-arduino-projekt-servo) gestoßen, an dem wir uns orierntieren können. 


#### 28.08.19 <a name="2808"></a>  
Da Herr Buhl uns vorgeschlagen hat, das Projekt zu übernehmen und als Eigenleistung den Code selbst zu schreiben, haben wir uns erneut umentschieden und werden nun doch die Bewässerungsanlage bauen. Wundervoll, diese hundertfachen Planänderungen oder?
Wir beginnen damit, das Grundprinzip der Sensoren zu verstehen, wie man sie verbindet und programmiert. Nächste Stunde werden wir an dem Beispiel eines Temperatursensors beginnen.


#### 29.08.19 <a name="2908"></a>  
Wir haben den [Schaltkreis](https://learn.adafruit.com/thermistor/using-a-thermistor) erstellt und **Beispielcodes** im Internet gesucht.
```

 
void setup(void) {
  Serial.begin(9600);
}
 
void loop(void) {
  float reading;
 
  reading = analogRead(THERMISTORPIN);
 
  Serial.print("Analog reading "); 
  Serial.println(reading);
 
  // convert the value to resistance
  reading = (1023 / reading)  - 1;     // (1023/ADC - 1) 
  reading = SERIESRESISTOR / reading;  // 10K / (1023/ADC - 1)
  Serial.print("Thermistor resistance "); 
  Serial.println(reading);
 
  delay(1000);
}
```
Wir haben leider schnell gemerkt, dass wir relativ wenig Verständnis aufweisen konnten und Felix stellte, rückblickend auf sein letztes Projekt, fest, dass es optimaler Projekte für uns geben könnte und so kam es, dass wir Arduino aufgaben.


#### 11.09.19 <a name="1109"></a>
Da wir nun wieder ohne Projekt da standen haben wir zuerst ein Mal überlegt, was wir überhaupt wollen. Ziemlich schnell konnten wir uns darauf einigen, dass wir ein Computerspiel erstellen wollen.
Als nächstes stellten wir uns die Frage: Welches Programm ist für uns am besten geeignet?
Da Felix bereits letztes Jahr mit [Snap!](https://snap.berkeley.edu/) gearbeitet hat, schlossen wir dies aus, damit er keinen zu großen Wissensvorspung hat. Wir erstellten eine Liste anderer Möglichkeiten und entschieden uns am Ende zwischen [App Lab](https://code.org/educate/applab) und [Greenfoot](https://www.greenfoot.org/door) für letzteres, da es für Anfänger empfohlen wird und die Schule Bücher dazu bereit stellt.


#### 12.09.19 <a name="1209"></a>
Um uns einen ersten Überblick über die Funktionsweise von Greenfoot zu verschaffen, sind wir einige der Lernaktivitäten, die Herr Buhl im isurf-Ordner hochgeladen hat durchgegangen. Bei dem ersten haben wir gelernt, wie ein sogenannter "Actor" sich mithilfe der Pfeiltasten bewegen kann, andere "Actor Classes" eleminieren kann und sie danach sogar mit sich herum trägt. Das Beispiel hieß "Meet the Greeps".

<img width="550" alt="Bildschirmfoto 2019-11-14 um 15 53 09" src="https://user-images.githubusercontent.com/54102146/68875793-b1f2d800-0703-11ea-83ab-01c5a356eb52.png">




#### 24.09.19 <a name="2409"></a>
Auch heute widmeten wir uns wieder den Lernaktivitäten, das heutige Szenario hieß "Fat Cat".
Wir beschäftigten uns mit verschiedenen if-commands, das heißt, dass das Programm Zusammenhänge herstellt, zum Beispiel, dass die Katze frisst, wenn sie hungrig ist und im Anschluss tanzt. Hier haben wir verschiedene Handlungsketten erstellt. Zudem haben wir mehr über die Klassen und ihre Unterklassen gelernt und wie man dieses entweder abhängig oder unabhängig von einander codiert.


#### 25.09.19 <a name="2509"></a>
Bevor wir uns weitere Skills aneigneten, haben wir überlegt, was für ein Szenario wir selbst erstellen wollten. Da unsere vorherigen Projektideen, die Bewässerungsanlage und der automatischen Teebeutelentfernen, beide etwas mit Wasser zu tun hatten, beschlossen wir, dies fortzuführen und eine Unterwasserwelt zu erstellen. Wir wählten den [Hintergrund](https://pixers.de/aufkleber/unterwasser-hintergrund-sonnenlicht-auf-meeresboden-67199299) aus und passten ihn in Greenfoot an. In einer Unterwasserwelt muss es natürlich auch Fische geben, daher suchten wir auch danach im Internet, wurden aber vorerst nicht fündig.


#### 25.09.19 <a name="2509"></a>
Wir setzten unsere Suche fort und beschlossen ihn in Adobe Photoshop selbst zu kreieren. 

![Fisch1](https://user-images.githubusercontent.com/54102146/68875775-aacbca00-0703-11ea-818d-6f3e317f516c.png)

Da dies zwar recht zeitaufwendig war, aber unseres Erachtens nach lohnenwert, beschlossen wir, dies mit den anderen Fischen ebenfalls zu tun.


#### 25.09.19 <a name="2509"></a>
Weiter ging es heute mit dem 2. und 3. Fisch, die wir im Unterricht nicht vollständig erstellen konnten. Den Rest erledigten wir also pflichtbewusst zu Hause :).

![Fisch3](https://user-images.githubusercontent.com/54102146/68875864-cd5de300-0703-11ea-95cb-01077cb25028.png)
![Fisch2](https://user-images.githubusercontent.com/54102146/68875866-cd5de300-0703-11ea-8fb9-6c5752698fdb.png)




#### 26.09.19 <a name="2609"></a>
Weil wir uns nun an Photoshop gewöhnt hatten, konnten wir die Fische viel schneller fertig stellen und die verschiedenen Optiken in dieser Stunde fertigstellen. 

![Fisch5](https://user-images.githubusercontent.com/54102146/68875862-cd5de300-0703-11ea-89c1-a1a8521accdf.png)
![Fisch4](https://user-images.githubusercontent.com/54102146/68875863-cd5de300-0703-11ea-95ff-a3119e8cd75c.png)

Da die Fische auch vegetarische Nahrung brauchen, haben wir noch [Algen](https://de.pngtree.com/free-png-vectors/cartoon--seegras) im Internet herausgesucht. Da in dieser Version noch ein weißer Hintergrund zu sehen war, nutzten wir die "Ausschneidefunktion" von Photoshop mit folgendem Ergebnis: 

![Unknown](https://user-images.githubusercontent.com/54102146/68875861-cd5de300-0703-11ea-8f96-f988160d1a28.png)



#### 01.10.19 <a name="0110"></a>
Jetzt, wo wir die Optik fertiggestellt hatten, mussten wir uns erst mal darüber klar werden, welches Konzept unser Spiel verfolgen sollte.
Lotta hatte die Idee ein Spiel zu entwickeln, in dem man einen Fisch steuert, der überlebt, indem er andere, kleinere Fische frisst und dabei wächst. Er kann allerdings auch selbst von größeren Fischen gefressen werden, dann ist die Runde beendet. Die Steuerung soll über die Pfeiltasten am Computer ablaufen, wie wir es in der Lernaktivität 1 (siehe 12.09.19) gelernt haben. 
Die restlichen Methoden wollten wir uns in den nächsten Stunden mithilfe der Lernaktivitäten und des Greenfoot Buchs "Einführung in Java und Greenfoot" erschließen.


#### 02.10.19 <a name="0210"></a>
In dieser Stunde gab es leider technische Schwierigkeiten mit dem Computer. Das Log-in hat nicht funktioniert, weshalb wir nach einigen Versuchen an den PC von Herrn Buhl gegangen sind. Wie schon geplant, arbeiteten wir heute an den Lernaktivitäten. Bei "Little Crab" lernten wir zum Beispiel, wie man einen Actor zufällig auf dem Bildschirm bewegen lässt und, wie er an den Ecken seine Richtung ändert.
Für viel mehr hat die Zeit blöderweise nicht gereicht.


#### 22.10.19 <a name="2210"></a>
Die glorreiche Stunde der Kreation von etwas Wundervollen hat begonnen: Fischis erster Code wurde geschrieben!
Um ganz simpel anzufangen, haben wir Fischi erst ein Mal das Schwimmen beigebracht.

<img width="550" alt="Bildschirmfoto 2019-11-15 um 14 06 02" src="https://user-images.githubusercontent.com/54102146/68946137-867af680-07b2-11ea-8fc4-3bc567c6dd0a.png">

Die Geschwindigkeit definierten wir vorher.

<img width="550" alt="Bildschirmfoto 2019-11-15 um 14 05 00" src="https://user-images.githubusercontent.com/54102146/68946610-b5459c80-07b3-11ea-8f88-58da87f0607e.png">


#### 23.10.19 <a name="2310"></a>
Fehler zugeben ist sehr wichtig, wie Felix G. Herrmann einst sagte. Die heutige Unterrichtsstunde war definitiv nicht unsere produktivste, wir schafften es nur Fischi beizubringen, nicht zu weit weg zu schwimmen und am Rand umzudrehen, wie wir es in den Lernaktivitäten erschlossen hatten.

<img width="550" alt="Bildschirmfoto 2019-11-15 um 14 33 21" src="https://user-images.githubusercontent.com/54102146/68947117-fd18f380-07b4-11ea-83cb-319eea62bbaf.png">

Des weiteren suchten wir online nach passenden Codes für unser kleines Haustier.


#### 24.10.19 <a name="2410"></a>
Ob es Schicksal gibt oder nicht, ist eine schwere Frage. Was Felix und ich aber feststellen durften: Pechsträhnen gibt es durchaus (vielleicht sollte man es nicht Pechsträhne, sondern Dummheitssträhne nennen). Wir wollten unserem Fischi eine Boostmöglichkeit geben, bei der sich die Geschwindigkeit erhöht. Damit es kein dauerhaft nutzbarer Cheatcode ist, haben wir versucht einen Cooldown einzubringen, also eine Abklingzeit. Leider blieb das ein einseitiger Wunsch, den Fischi ignorierte, weil er manchmal noch etwas bockig war. Der Boost funtioniert zwar, die Abklingzeit aber nicht.

<img width="550" alt="Bildschirmfoto 2019-11-15 um 14 38 43" src="https://user-images.githubusercontent.com/54102146/68947824-b5936700-07b6-11ea-8d2c-c8c7a2687476.png">

Aus zeitlichen Gründen haben wir uns dann aber entschlossen, diese Baustelle zu einem anderen Zeitpunkt zu beenden und uns vorerst wichtigeren Dingen zu widmen.


#### 29.10.19 <a name="2910"></a>
Irgenwann werden auch die süßesten Kinder, wie Felix, erwachsen, aber um ihn geht es in dieser Stunde nicht. Viel besser noch: Fischi wächst! Felix hat viel Spinat gegessen und Fischi eben sein Seegras. Damit er dabei nicht verpixelt, lassen wir das Bild jedes mal neu setzen, anstatt es einfach größer zu ziehen.

<img width="550" alt="Bildschirmfoto 2019-11-15 um 14 53 08" src="https://user-images.githubusercontent.com/54102146/68948248-c4c6e480-07b7-11ea-8a70-34bb630e7e2e.png">


#### 05.11.19 <a name="0511"></a>
Wer liebt beim Computerspielen keine Special Items? (Lotta eigentlich, aber Felix konnte sich durchsetzen)
Eine weitere Möglichkeit Fischi schneller zu machen, war es, ihn mit der neuen Actor Class "X", einer kleinen Rakete, in Berührung kommen zu lassen. 

<img width="550" alt="Bildschirmfoto 2019-11-15 um 15 01 24" src="https://user-images.githubusercontent.com/54102146/68948791-effe0380-07b8-11ea-8138-0bca2b8fbae0.png">

<img width="550" alt="Bildschirmfoto 2019-11-15 um 15 01 42" src="https://user-images.githubusercontent.com/54102146/68948801-f4c2b780-07b8-11ea-8e4e-d7656dcd2096.png">




https://www.greenfoot.org/files/javadoc/index-all.html

(To-Do):
- [x] Checkliste
- [ ] Lesestoff Links
- [ ] Lesestoff bilder


#### Lesestoff/ Quellen <a name="Lesestoff"></a>
https://www.kreativekiste.de/servo-suessigkeiten-spender-arduino
