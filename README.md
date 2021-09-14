# Das Morse-Alphabet

... IN ARBEIT ...

## Geheimzeichen: Das Morse-Alphabet I

**Hallo, ich bin Robi-x01 und werde dich beim Programmieren mit BBC micro:bit begleiten.**

Wenn du neu bist im Bereich Micro:bit, dann empfehle ich dir das [Schulbuch zum Micro:bit](https://microbit.eeducation.at/wiki/Hauptseite "(target|_blank)")
zum Einarbeiten in diesen fabelhaften Kleincomputer. Dieses Projekt benötigt bereits ein wenig Grundwissen in BBC micro:bit. Zum Arbeiten an diesem Projekt ist es wichtig, dass ihr im Team zu zweit arbeitet.

<center>
<img width="20%" src="https://github.com/dlpl-mb/baa_morse_code_01/blob/master/images/robi_klein.png?raw=1" />
</center>

Wir werden uns eine Geheimsprache ansehen - das **Morse-Alphabet**. Es diente jahrzehntelang zum Übertragen von Nachrichten - heute wird es in einigen wenigen Bereichen noch verwendet.
Inzwischen gibt es unzählige Codiersysteme, die zusätzlich zum Übertragen auch noch verschlüsselt können, damit beispielswiese Geldüberweisungen oder auch militärische Informationen sicher übermittelt werden können.
Du wirst nun das Morsealphabet genauer kennenlernen. Eine umfangreiche Information zum Morsecode erhältst du in [Wikipedia](https://de.wikipedia.org/wiki/Morsecode "(target|_blank)").

## Die Zeichen des Morsealphabets

Die Morsezeichen oder Morsecodes kann man optisch (in Bildern) oder akustisch (mit Ton) oder auch über elektrische Leitungen als kurze und lange Signale übermitteln. Wichtig dabei ist, dass jeder Buchstabe, jede Ziffer genau einem Code aus **Punkten und Strichen** entspricht. Hier ist eine Tabelle des Morsealphabets.

<img width="100%" src="https://github.com/dlpl-mb/baa_morse_code_01/blob/master/images/morse-tab.png?raw=1"/>

* Wie du aus der Tabelle ersehen kannst, haben Morsezeichen nur den **Punkt** und den **Strich** zur Darstellung zur Verfügung. Jeder Buchstabe besteht aus einer Kombination von **Punkten und Strichen**.
* Schreib dir auf einem Blatt Papier die ersten Buchsstaben **A bis G** heraus: **Buchstabe** und **Code** - aus Überblicksgründen verwenden wir in den ersten Übungen vorerst nur einmal wenige Buchstaben.
* Damit beim Senden der Empfänger weiß, wann der eine Buchstabe zu Ende ist und ein neuer beginnt, wird nach jedem Buchstaben eine kurze Pause eingebaut (ca. 1/2 Sekunde). Längere Pausen (etwa 1 Sekunde) zeigen an, dass ein Wort zu Ende ist.
* **Dazu gleich eine Übungsfrage:** Welchen Buchstaben stellt dieses Zeichenkombination dar? `-..` oder diese `..-.`  
* Versucht nun mit Klopfzeichen auf dem Tisch den Morsecode für ein **A** oder **B** oder **C**` zu klopfen - dein Spielpartner sollte versuchen, den Buchstaben zu erraten. Wechselt die Rollen und versucht einen guten Klopf-Rhythmus zu finden.

## Der Morsecode-Tester

* Drücke ``|Taste A|`` für die Aufgabe
* Suche den angezeigten Buchstaben in der Morsetabelle
* Drücke ``|Taste B|`` für die Lösung
* Führe 10 Versuche durch
* wei gut bist du im Raten des Morsecodes
* <div style="position:relative;height:0;padding-bottom:81.97%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---run?id=_YF16Xa8C9ecP" allowfullscreen="allowfullscreen" sandbox="allow-popups allow-forms allow-scripts allow-same-origin" frameborder="0"></iframe></div>

* Wenn du wissen willst, wie der Programmcode aussieht, dann öffne diesen Link
* [Programmcode 1b - Morsecode-Test`](https://makecode.microbit.org/#pub:_YF16Xa8C9ecP){:target="_blank"}

* *** ENDE *** ENDE *** ENDE

## Programm 1: Die Morsecodes auf dem Micro:bit anzeigen

Du baust nun für dem BBC Micro:bit ein erstes Programm zum Zeigen der Morse-Codes für **A bis G**.

**Eine Aufgabe:**

* ``|Taste A|`` des Micro:bit zeigt vorerst einmal den Buchstabe A (später nehmen wir weitere Buchstaben dazu.)
* ``|Taste B|`` zeigt den Morse-Code für dieses Zeichen an
* Später wirst du dein Programm so ausbauen, dass Codes an anderen Micro:bits gesendet werden können.

```blocks
input.onButtonPressed(Button.A, () => { 
    basic.showString("A");
});

input.onButtonPressed(Button.B, () => { 
    basic.showString(".-");
});
```

* Schreibt nun im (Grafik-)Programmeditor die jeweiligen Programme für die anderen Buchstaben **B bis G**. Du musst das Programm bei jedem Buchstaben umschreiben (ganz schön umständlich!)

* [Programmcode 1 - ``|Taste A|`` und ``|B|``](https://makecode.microbit.org/#pub:_dwP8X4TpY7oz){:target="_blank"}

<hr>

<img width="20%" src="https://github.com/dlpl-mb/baa_morse_code_01/blob/master/images/robi_klein.png?raw=1" />

**!!! Nun wird es deutlich schwieriger !!!**

## Programm 2: Alle sechs Buchstaben in einem Programm anzeigen

Es ist recht aufwändig, für jeden Buchstaben immer ein eigenes Programm zu schreiben.
**Wir packen nun alle 7 Buchstaben in ein Programm:**

* Wir werden dazu alle sieben Buchstaben in eine Liste bringen
* Dazu gibt es einen besonderen Variablentyp **Array** oder **Liste**
* Wähle unter ``|array:Arrays|`` und dort ``|array:setze Text_List ...|``
* Lege dort 2 Text-Listen an: `liste buchstaben` und  `liste_morsecodes` (siehe unten)
* Vervollständige die Eintragungen von "A" bis "G"

```blocks
let liste_morsecodes: string[] = []
let liste_buchstaben: string[] = []

liste_buchstaben = [
"A",
"B",
"C",
"D",
"E",
"F",
"G"
]
liste_morsecodes = [
".-",
"-...",
"-.-.",
"-..",
".",
"..-.",
"--."
]
```

### Zugriff auf die Buchstaben einer Liste

* Um auf ein Element dieser Liste zuzugreifen, muss du in eckigen Klammern immer den **Index** (Reihungsnummer) innerhalb der Liste angeben - zB: liste_morsecodes[0] ist das erste Element, liste_morsecode[1] ist das zweite Element.
* **Beachte:** Eine Liste beginnt in allen Programmiersprachen immer mit dem **Element Nr. 0**, dann kommt 1 bis zum letzten Element (6), das hat hier in diesem Beispiel die Nummer 6 (unsere Liste von A bis G) (Zugegeben: das ist vorerst etwas unlogisch, bringt aber später beim Programmieren große Vorteile)
* Die höchste Nummer ist immer **Anzahl der Elemente - 1**
* Das ist sicher sehr gewöhnungsbedürftig - man sollte sich diese kleine Sonderlogik möglichst schnell eingewöhnen und anwenden
* Sobald man auf einzelne Elemente zugreifen will, ist dieses Indexzahl wichtig.

### Anzeigen der Buchstaben nach der Reihe von A bis G

* Wir benötigen für den Zugriff auf alle Elemente eine Schleife von 0 bis 6
* Innerhalb der Schleife "zeigen" wir mit einer **Laufvariable** (mit einem Index) auf das jeweilige Element.

### Ein kleiner Programmteil zum Experimentieren - öffne das Programm 1b bim Micro:bit

* Studiere diesen Programmteil und experimentiere mit der Schleife bei ``|Taste A|``  
* Verändere Variable und deren Inhalte und sieh dir dann die Schleife an.
* Überlege, was die neue Variable ``|anz_bst|`` für eine Funktion hat: 
  * Tipp: Wir könnten ja die Schleife von 0 bis 6 fix programmieren - was passiert aber, wenn wir später die Liste der Buchstaben ändern.

* [Programmcode 1b - Taste A](https://makecode.microbit.org/#pub:_61cEM1PaTRMR){:target="_blank"}

* Derzeit gibt die ``|Taste A|`` die Buchstaben aus
* Die ``|Taste B|`` bekommt nun auch eine Aufgabe, die Morsezeichen auszugeben
* Die Logik ist wieder sehr ähnlich der ``|Taste A|``
* Dazu hier der Programmcode 1c - experimentiere auch hier wieder mit dem Programmcode.
  
* [Programmcode 1c - Taste B](https://makecode.microbit.org/#pub:_XvJik0eaW78Y){:target="_blank"}

## Fertiger Programmteil "Einführung"

* Und nun haben wir bereits das fertige Programm diese Projektteils **Einführung**
* Eine kleine Ergänzung kommt zur ``|Taste B|`` noch dazu:
  * Man möchte auch den Buchstaben zum Morsecode sehen.

* [Programmcode 2: Fertiges Programm](https://makecode.microbit.org/#pub:_MPxAW5dkwgKF){:target="_blank"}

<img width="100%" src="https://github.com/dlpl-mb/baa_morse_code_01/blob/master/images/bild_prg1c.png?raw=1"/>

* Experimentiere mit diesem Programm.

### Dies war nun ein schwieriges Kapitel mit den Arrays (Listen) - das ist immer ein kleiner Prüfstein für uns Roboter.

<img width="20%" src="https://github.com/dlpl-mb/baa_morse_code_01/blob/master/images/robi_klein.png?raw=1" />

* Übt mit eurem Lehrer/eurer Lehrerin **Arrays** noch an anderen Sachverhalten. Diese Art von Variablen sind die **wichtigsten** im Bereich der Programmierung. Wer mit Array umgehen kann, der kann sehr viele Anwendungen verstehen oder programmieren. **Arrays** werden immer dann eingesetzt, wenn viele Variable nötig sind, man überlegt, wie man sie in eine Liste packen könnte.

* Im zweiten Projektteil wirst du das Gelernte anwenden und noch ausbauen. Dort gehts es dann um das **Senden der Nachrichten** - wir senden an einen zweiten Micro:bit.

## [Aufruf des zweiten Projektteils: Morsecodes versenden](https://dlpl-mb.github.io/baa_morse_code_02)

<style>.page-header {font-size:1rem;height:0vh;padding-top:1.5rem}</style>
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
