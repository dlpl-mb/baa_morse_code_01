
## Geheimzeichen: Das Morse-Alphabet I
**Hallo, ich bin Robi01 und werde dich beim Programmieren mit BBC micro:bit begleiten.**

<img width="20%" src="https://github.com/dlpl-mb/baa_morse_code_01/blob/master/images/robi_klein.png?raw=1">


Wir werden uns nun einen Geheimsprache ansehen - das ** Morse-Alphabet **. Es diente jahrzehntelang zum Übertragen von Nachrichten und wurde inzwischen in vielen Bereichen von technisch aufwendigen Verfahren weiterentwickelt.
Inzwischen gibt es unzählige Codes, die sogar noch zusätzlich verschlüsselt werden, damit beispielswiese Geldüberweisungen oder auch militärische Informationen sicher übermittelt werden können.
Du wirst nun diese wichtige Morsealphabet genauer kennenlernen. Ein umfangreiche Information zum Morsecode erhältst du in [Wikipedia](https://de.wikipedia.org/wiki/Morsecode "(target|_blank)").

## Die Zeichen des Morsealphabets
Die Morsezeichen kann man optisch (Bildern) oder akustisch (Ton) oder auch über elektrische Leitungen übermitteln. Wichtig dabei ist, dass jeder Buchstabe, jede Ziffer genau einem Code entspricht.

<img width="100%" src="https://github.com/dlpl-mb/baa_morse_code_01/blob/master/images/morse-tab.png?raw=1">

* Wie du aus der Tabelle siehst haben Morsezeichen nur den **Punkte** und den **Striche**. Jeder Buchstabe hat einen bestimmte Kombination von Punkten und Strichen.
* Schreib dir in einer kleinen Tabelle die ersten Buchsstaben **A bis G** auf ein Blatt Papier heraus: **Buchstabe** und **Code**
* Statt einem Buchstaben werden also nur Punkt- und Strichcodes gesendet - was den großen Vorteil, dass man sogar ohne Leitungen etwa über Lichtsignale oder Soundsignale Daten übertragen kann.
* Damit das Gegenüber weiß, wann ein Buchstabe zu Ende ist und ein neuer beginnt, wird nach jedem Buchstaben ein kurze Pause gemacht. Längere Pause (etwa 1 Sekunde) nach jedem Wort.
* **Gleich eine Frage:** Welcher Buchstabe ist das? -.. oder dieser Buchstabe. 
* Versucht nun mit Klopfzeichen auf dem Tisch den Morsecode für ein A oder B oder C zu klopfen - dein Spielpartner sollte versuchen, den Buchstaben zu erraten.

## Programm 1: Codes anzeigen 

Du baust nun für dem BBC Micro:bit ein erstes Programm zum Zeigen der Morse-Codes für A bis G. 

**Die Aufgaben lautet:**

* `Taste A` des Micro:bit zeigt die Buchstaben A bis G (später nehmen wir alle anderen Buchstaben dazu.)
* `Taste B` zeigt den Morse-Code für diese Zeichen an 
* Später wirst du dein Programm so ausbauen, dass du Codes zu anderen Micro:bit übertragen und somit Anderen senden kann.
* Probiere das gleich mit dem Button "Dreieck" aus:
<img width="40%" src="https://github.com/dlpl-mb/baa_morse_code_01/blob/master/images/dreieck.png?raw=1">

```blocks
input.onButtonPressed(Button.A, () => { 
    basic.showString("A");
});

input.onButtonPressed(Button.B, () => { 
    basic.showString(".-");
});
```
* Schreib nun im Programmeditor (Button **Blöcke**) die kurzen Programme für die anderen Buchstaben B bis G.

## Programm 2: Alle sechs Buchstaben in ein Programm

Zugegeben: Das war ganz schön aufwändig, für jeden Buchstaben immer ein eigenes Programm zu schreiben.
Wir packen nun alles 7 Buchstaben in ein Programm:
* Wir müssen alle sieben Buchtaben in eine Liste hinein bringen
* Dazu gibt es einen besonderen Variablentyp **Array** oder **Liste** 
* Wähle unter ``|Fortgeschritten Arrays|`` und dort ``||array:setze Text_List ...||``
* Ändere den Variablen auf Buchstabenliste
* Vervollständige die Buchstaben von "A" bis "G"

### Speicherung der Buchstaben 

* Um auf ein Element dieser Liste zuzugreifen, muss du den **Index** (Reihungsnummer ) innerhalb der liste angeben.
* Beachte: Eine Liste beginnt in fast allen Programmiersprachen immer mit dem Element Nr. 0, dann 1 bis zum letzten element, das hat dann die Nummer 6 (unsere Liste von A bis G). Das ist sicher sehr gewöhnungsbedürftig - man sollte sich das möglichst schnell angewöhnen und anwenden. 

### Darstellung der Buchstaben 

* Wir benötigen eine Schleife von 0 bis 6
* Innerhalb der Schleife zeigen wir mit einer **Laufvariable** - wir nennen sie hier **index** auf jeweils ein Element.


## Fertiges Programm: Morse-Alphabet II
Du kannst nun am folgenden fertigen Programms noch experimentiert. 
* Verändere Variable und Zeiten
* Beim Experimentieren an fremden Programmen kannst du viel lernen 

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
anz_bst = liste_buchstaben.length - 1
```


#### Metadaten

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>


<!--stackedit_data:
eyJoaXN0b3J5IjpbNzYxOTAxOTM1LC00OTQ2NjMwNzUsLTczMj
ExMzkwOSwxNTkzMDkwOTg4LC0xNDc4MzI3NTU4XX0=
-->