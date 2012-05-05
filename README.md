# Workshop 04. Mai 2012

## Inhalt

Der zweite Workshoptermin wird sich auch noch den Grundlagen widmen: »Dinge« und Speicher, Stack und Heap, Klassen und Instanzen (Objekte)

### Folien zum Vortrag

Die Vortragsfolien stehen als [PDF](https://github.com/downloads/kit-cpp-workshop/workshop-ss12-02/slides.pdf) zum Download bereit. Außerdem liegt der LaTeX-Quellcode zu den Folien im Ordner `slides`.

###Screencast

Eine (vorläufige) Aufzeichnung des Vortrags steht zum [Download](http://ubuntuone.com/3jd4VvjcWsOzSFA3O5zMz0) bereit. Durch die Verwendung eines anderen Mikrofons ist der Klang besser, dafür sind Fragen/Anmerkungen der Zuhörer (fast) nicht zu verstehen. Die Endfassung des Vortrags wird daher mit Untertiteln versehen.

## Aufgaben

Sendet, nachdem ihr alle Aufgaben abgearbeitet habt, einen Pull-Request an das Workshop-Repository. Stellt sicher, dass ihr vorher alle eure Änderungen in euren Fork übertragen habt. Nennt euren Workshop-Betreuer im Text des Pull-Requests, einer der Betreuer (bevorzugt der genannte) wird dann eure Lösungen durchsehen, kommentieren und nach Abschluss des Reviews den Pull-Request als abgelehnt markieren.


### Aufgabe 1: Fibonacci-LUT

Eine LUT ist eine Lookup-Tabelle ( [siehe wikipedia](https://de.wikipedia.org/wiki/Lookup-Tabelle) ).
Diese speichert Daten (_hier: Fibonacci-Zahlen_) deart, dass auf diese Schnell mittels eines Schlüssels (_hier: die Nummer `n` der Fibonacci-Zahl_) zugegriffen werden kann.

Schreibe eine Fibonnaci-LUT als Klasse. Die Objekte der Klasse sollen mit einem Parameter erzeugt werden, der die größte Nummer der Fibonnaci-Zahlen festlegt.
Mittels einer Methode soll aus einem Objekt auf eine Fibonnaci-Zahl der LUT zugegriffen werden können.


Spoiler:
Verwende ein Array auf dem Heap und verwalte es im ctor und dtor.

Anmerkungen:
Die Fibonacci-Zahlen werden recht schnell größer als die größte Zahl,
die man in einem Integer speichern kann. Wenn ihr merkwürdige negative
Zahlen in euerer Liste habt, dann liegt das daran.
Bonuspunkte gibt's, wenn die Zahlen erst dann berechnet werden, wenn
das auch wirklich nötig ist (Hinweis: Überlege Dir, wie Du speichern
kannst, dass eine bestimmte Zahl noch nicht berechnet wurde).


### Aufgabe 2: Ringpuffer

Ein Ringpuffer ist eine Datenstruktur, in der endlich viele Daten gespeichert werden können. Wird versucht, mehr Daten hineinzuschreiben, so werden alte Daten überschrieben.
Siehe [wikipedia](https://de.wikipedia.org/wiki/Ringpuffer#Ringpuffer)

Schreibe eine Ringpuffer-Klasse, dessen Instanzen `double`s speichern können. Ein neues Datum (ein neuer `double`) soll hinzugefügt werden können (`push`), die vorhandenen Elemente in entgegengesetzter Reihenfolge zum Einfügen gelöscht (`pop`). 
`pop` soll immer das älteste Element, welches noch nicht zurückgegeben
wurde, zurückgeben (wenn man also zweimal `pop` macht, sollte man das
zweitälteste bekommen etc.).
`push` soll einen bool zurückgeben: true falls ein Element erfolgreich
eingefügt wurde, und false falls das Einfügen fehlgeschlagen ist, zum
Beispiel weil der Buffer voll ist. Es sollen also keine Elemente
überschrieben werden, auf die noch nicht mit `pop` zugegriffen wurde.
Man soll mittels einer Methode jedes Element des Ringpuffers auslesen können (ob du überprüfst, ob dieses Element noch nicht beschrieben wurde, bleibt dir überlassen).

Spoiler:
Es kann sich anbieten, die Fibonacci-LUT als Grundgerüst zu verwenden. Dann benötigst du (je nach Implementierung) nur noch zwei zusätzlichen Pointer (und natürlich andere Methoden/Funktionen).