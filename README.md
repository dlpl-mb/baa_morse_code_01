# Das Morse-Alphabetx
## Geheimzeichen: Das Morse-Alphabet I
**Hallo, ich bin Robi01 und werde dich beim Programmieren mit BBC micro:bit begleiten.**

Wenn du neu bist im Bereich Micro:bit, dann empfehle ich dir das [Schulbuch zum Micro:bit](https://microbit.eeducation.at/wiki/Hauptseite "(target|_blank)") zum Einarbeiten in diesen fabelhaften Kleincomputer. Diese Lektion benötigt bereits ein wenig Grundwissen in BBC micro:bit. Wichtig ist auch, dass ihr immer im Team zu zweit arbeitet.

<img width="20%" src="https://github.com/dlpl-mb/baa_morse_code_01/blob/master/images/robi_klein.png?raw=1">


Wir werden uns eine Geheimsprache ansehen - das ** Morse-Alphabet **. Es diente jahrzehntelang zum Übertragen von Nachrichten und wurde inzwischen in vielen Bereichen zu technisch aufwendigen Verfahren weiterentwickelt.
Inzwischen gibt es unzählige Kodiersysteme, die sogar noch zusätzlich verschlüsselt werden, damit beispielswiese Geldüberweisungen oder auch militärische Informationen sicher übermittelt werden können.
Du wirst nun diese wichtige Morsealphabet genauer kennenlernen. Ein umfangreiche Information zum Morsecode erhältst du in [Wikipedia](https://de.wikipedia.org/wiki/Morsecode "(target|_blank)").

## Die Zeichen des Morsealphabets
Die Morsezeichen kann man optisch (Bildern) oder akustisch (Ton) oder auch über elektrische Leitungen übermitteln. Wichtig dabei ist, dass jeder Buchstabe, jede Ziffer genau einem Code aus **Punkt und Strich** entspricht.

<img width="100%" src="https://github.com/dlpl-mb/baa_morse_code_01/blob/master/images/morse-tab.png?raw=1">

* Wie du aus der Tabelle ersehen kannst, haben Morsezeichen nur den **Punkt** und den **Strich** zum Kodieren. Jeder Buchstabe besteht aus einer bestimmte Kombination aus Punkten und Strichen.
* Schreib dir in einer kleinen Tabelle die ersten Buchsstaben **A bis G** auf ein Blatt Papier heraus: **Buchstabe** und **Code** - aus Überblicksgründen verwenden wir in den ersten Übungen vorerst einmal nur wenige Buchstaben.
* Statt einem Buchstaben werden also nur Punkt- und Strichcodes gesendet - was den großen Vorteil, dass man sogar ohne Leitungen etwa über Lichtsignale oder Soundsignale Daten übertragen kann.
* Damit das Gegenüber weiß, wann ein Buchstabe zu Ende ist und ein neuer beginnt, wird nach jedem Buchstaben ein kurze Pause gemacht. Längere Pause (etwa 1 Sekunde) dann nach jedem Wort.
* **Nun gleich eine Frage:** Welcher Buchstabe ist das? `-..` oder dieser Buchstabe `..-.`  
* Versucht nun mit Klopfzeichen auf dem Tisch den Morsecode für ein `A` oder `B` oder `C` zu klopfen - dein Spielpartner sollte versuchen, den Buchstaben zu erraten.

## Programm 1: Codes anzeigen 

Du baust nun für dem BBC Micro:bit ein erstes Programm zum Zeigen der Morse-Codes für `A` bis `G`. 

**Die Aufgaben lautet:**

* `Taste A` des Micro:bit zeigt die Buchstaben A bis G (später nehmen wir alle anderen Buchstaben dazu.)
* `Taste B` zeigt den Morse-Code für diese Zeichen an 
* Später wirst du dein Programm so ausbauen, dass du Codes zu anderen Micro:bit übertragen und somit Anderen senden kannst.

```blocks
input.onButtonPressed(Button.A, () => { 
    basic.showString("A");
});

input.onButtonPressed(Button.B, () => { 
    basic.showString(".-");
});
```
* Schreib nun im Programmeditor (mit grafischen **Blöcke**) die kurzen Programme für die anderen Buchstaben B bis G. Du musst das Demoprogramm für jeden Buchstaben umschreiben.

[Programmcode 1](https://makecode.microbit.org/#pub:_dwP8X4TpY7oz "(target|_blank)")

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

Du kannst nun am folgenden fertigen Programms noch experimentiert. 
* Verändere Variable und Zeiten
* Beim Experimentieren an fremden Programmen kannst du viel lernen 

[Programmcode 2](https://makecode.microbit.org/#pub:_MPxAW5dkwgKF "(target|_blank)")

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
# Danke für eure Mitarbeit
Du hast nun bereits Arrays (Listen) kennen gelernt - übt mit eurem Lehrer/eurer/Lehrerin Arrays noch an anderen Sachverhalten. Diese Art von Variablen sind eine der wichtigsten im Bereiche der Programmierung.

In der zweiten Lektion wirst du nun schon tiefer in das Programmieren einsteigen.

#### Technische Metadaten
<style>.page-header {font-size:1rem;height:0vh;padding-top:1.5rem}</style>
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2NTYyMjQzNjMsMTk2Njk5MzYxLC0xND
czNzUyNTAzLC0xMzI4MzAwNzYxLDkzOTk3NDE2MywxMzUzMTM2
NTY5LDg0MDY5MDI1OCwtMTU1Mzk4MDI3MiwyMTMzNDI0MzQsLT
E1NTM5ODAyNzIsNjE5NjYyMDY0LDM1Mzk2Mjg3OSwtMTM1ODc2
NjQwNywtNDk0NjYzMDc1LC03MzIxMTM5MDksMTU5MzA5MDk4OC
wtMTQ3ODMyNzU1OF19
-->