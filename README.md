# Das Morse-Alphabet

## Geheimzeichen: Das Morse-Alphabet I

**Hallo, ich bin Robi01 und werde dich beim Programmieren mit BBC micro:bit begleiten.**

Wenn du neu bist im Bereich Micro:bit, dann empfehle ich dir das [Schulbuch zum Micro:bit](https://microbit.eeducation.at/wiki/Hauptseite "(target|_blank)")
zum Einarbeiten in diesen fabelhaften Kleincomputer. Dieses Projekt benötigt bereits ein wenig Grundwissen in BBC micro:bit. Zum Arbeiten an diesem Projekte ist es wichtig, dass ihr im Team zu zweit arbeitet.

<center>
<img width="20%" src="https://github.com/dlpl-mb/baa_morse_code_01/blob/master/images/robi_klein.png?raw=1" />
</center>

Wir werden uns eine Geheimsprache ansehen - das **Morse-Alphabet**. Es diente jahrzehntelang zum Übertragen von Nachrichten - heute ist es in einigen Bereichen noch verwendet.
Inzwischen gibt es unzählige Kodiersysteme, die sogar noch zusätzlich verschlüsselt können, damit beispielswiese Geldüberweisungen oder auch militärische Informationen sicher übermittelt werden können.
Du wirst nun diese wichtige Morsealphabet genauer kennenlernen. Ein umfangreiche Information zum Morsecode erhältst du in [Wikipedia](https://de.wikipedia.org/wiki/Morsecode "(target|_blank)").

## Die Zeichen des Morsealphabets

Die Morsezeichen oder Morsecodes kann man optisch (in Bildern) oder akustisch (mit Ton) oder auch über elektrische Leitungen übermitteln. Wichtig dabei ist, dass jeder Buchstabe, jede Ziffer genau einem Code aus **Punkt und Strich** entspricht. Hier ist eine Tabelle des Morsealphabets.

<img width="100%" src="https://github.com/dlpl-mb/baa_morse_code_01/blob/master/images/morse-tab.png?raw=1"/>

* Wie du aus der Tabelle ersehen kannst, haben Morsezeichen nur den **Punkt** und den **Strich** zum Darstellung zur Verfügung. Jeder Buchstabe besteht aus einer bestimmte Kombination aus **Punkten und Strichen**.
* Schreib dir auf einem Blatt Papier die ersten Buchsstaben **A bis G** heraus: **Buchstabe** und **Code** - aus Überblicksgründen verwenden wir in den ersten Übungen vorerst einmal nur wenige Buchstaben.
* Statt einem Buchstaben werden also nur **Punkt- und Strichcodes** gesendet - was den großen Vorteil hat, dass man sogar ohne elektrische Leitungen etwa über Lichtsignale oder Soundsignale Daten übertragen kann.
* Damit das Gegenüber weiß, wann der eine Buchstabe zu Ende ist und ein neuer beginnt, wird nach jedem Buchstaben ein kurze Pause gemacht (ca. 1/2 Sekunde). Längere Pausen (etwa 1 Sekunde) zeigen an, dass ein Wort zu Ende ist.
* **Nun gleich eine Übungsfrage:** Welchen Buchstaben stellt dieses Zeichenkombination dar? `-..` oder diese `..-.`  
* Versucht nun mit Klopfzeichen auf dem Tisch den Morsecode für ein `A` oder `B` oder `C` zu klopfen - dein Spielpartner sollte versuchen, den Buchstaben zu erraten.

## Programm 1: Die Morsecodes auf dem icro:bit anzeigen

Du baust nun für dem BBC Micro:bit ein erstes Programm zum Zeigen der Morse-Codes für `A` bis `G`.

**Die Aufgaben lautet:**

* `Taste A` des Micro:bit zeigt vorerst einmal den Buchstabe A (später nehmen wir alle anderen Buchstaben dazu.)
* `Taste B` zeigt den Morse-Code für dieses Zeichen an
* Später wirst du dein Programm so ausbauen, dass du Codes zu anderen Micro:bits senden kannst.

```blocks
input.onButtonPressed(Button.A, () => { 
    basic.showString("A");
});

input.onButtonPressed(Button.B, () => { 
    basic.showString(".-");
});
```

* Schreib nun jeder im Programmeditor (mit **grafischen Blöcke**) die kurzen Programme für die anderen Buchstaben B bis G. Du musst dieses Demoprogramm für jeden Buchstaben umschreiben.

[Programmcode 1](https://makecode.microbit.org/#pub:_dwP8X4TpY7oz){:target="_blank"}

## Programm 2: Alle sechs Buchstaben in einem Programm anzeigen

Es ist recht aufwändig, für jeden Buchstaben immer ein eigenes Programm zu schreiben.
**Wir packen nun alles 7 Buchstaben in ein Programm:**

* Wir müssen also alle sieben Buchstaben in eine Liste bringen
* Dazu gibt es einen besonderen Variablentyp **Array** oder **Liste**
* Wähle unter ``|Fortgeschritten Arrays|`` und dort ``||array:setze Text_List ...||``
* Lege dort 2 Text-Listen an: `liste buchstaben` und  `liste_morsecodes` (siehe unten)
* Vervollständige die Eintragungen von "A" bis "G"

### Zugriff auf die Buchstaben einer Liste

* Um auf ein Element dieser Liste zuzugreifen, muss du in eckigen Klammern immer den **Index** (Reihungsnummer ) innerhalb der Liste angeben - zB: liste_morsecodes[0] ist das erste Element
* **Beachte:** Eine Liste beginnt in allen Programmiersprachen immer mit dem **Element Nr. 0**, dann kommt 1 bis zum letzten Element (6), das hat hier in diesem Beispiel die Nummer 6 (unsere Liste von A bis G)
* Die höchste Nummer ist immer **Anzahl der Elemente - 1**
* Das ist sicher sehr gewöhnungsbedürftig - man sollte sich das möglichst schnell angewöhnen und anwenden.
* Wie du unten im Beispiel ersehen kannst, werden die Indizes von 0 bis ... immer automatisch verteilt und du brauchst die Elemente nur der Reihe nach mit Beistrichen getrennt angeben. Handelt es sich um Texte, so sind diese in Anführungszeichen einzuschließen.

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

### Darstellung der Buchstaben

* Wir benötigen eine Schleife von 0 bis 6
* Innerhalb der Schleife zeigen wir mit einer **Laufvariable** - wir nennen sie hier **index** auf jeweils ein Element.

Du kannst nun am folgenden fertigen Programms noch experimentiert.

* Verändere Variable und deren Inhalte
 [Programmcode 2](https://makecode.microbit.org/#pub:_MPxAW5dkwgKF){:target="_blank"}

```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index <= anz_bst; index++) {
        basic.showString("" + (liste_buchstaben[index]))
        basic.pause(500)
    }
})
input.onButtonPressed(Button.B, function () {
    for (let index2 = 0; index2 <= anz_bst; index2++) {
        basic.showString("" + (liste_buchstaben[index2]))
        basic.showString("" + (liste_morsecodes[index2]))
        basic.pause(2000)
        basic.clearScreen()
    }
})
let anz_bst = 0
let liste_morsecodes: string[] = []
let liste_buchstaben: string[] = []
basic.showIcon(IconNames.Yes)

anz_bst = liste_buchstaben.length - 1
```

Experimentiere mit diesem Programm.

### Dies war das schwierige Kapitel der Arrays - das ist immer ein Profikapitel für Programmierer und Programmierinnen.

Du hast nun bereits Arrays (Listen) kennen gelernt - übt mit eurem Lehrer / eurer Lehrerin Arrays noch an anderen Sachverhalten. Diese Art von Variablen sind eine der wichtigsten im Bereiche der Programmierung.

In der zweiten Lektion wirst du schon tiefer in das Programmieren einsteigen und das bisher gelernte anwenden.

## [Lektion 2 - Morsecode](https://dlpl-mb.github.io/baa_morse_code_02)

<style>.page-header {font-size:1rem;height:0vh;padding-top:1.5rem}</style>
<script src="https://makecode.com/gh-pages-embed.js"></script>
<script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
