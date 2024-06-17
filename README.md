# FizzBuzz Spiel

## Spielbeschreibung

Das Spiel „FizzBuzz“ stellt dem Spieler eine Zahl zwischen 1 und 999 vor. Die Aufgabe des Spielers besteht darin, zu entscheiden, ob die präsentierte Zahl durch 3 (Fizz), durch 5 (Buzz) oder durch 3 und 5 (FizzBuzz) teilbar ist. Für jede richtige Antwort erhält der Spieler Punkte. Bei falscher Antwort gibt es keine Punkte.  
Falls die Zahl weder durch 3, noch durch 5 oder durch beide teilbar ist, muss der Spieler die Zahl als normale Nummer angeben.  
Das Ziel ist, so viele Punkte wie möglich zu sammeln, indem man die Teilbarkeit der Zahlen richtig erkennt.

## Spielanleitung

1. Generiere eine neue Zahl mit der „space“-Taste oder mit dem Button „New Number“.
2. Entscheide, ob die Zahl durch 3, durch 5 oder durch 3 und 5 teilbar ist.
3. Gib das Ergebnis mit den Buttons „Fizz“ (durch 3), „Buzz“ (durch 5) oder „FizzBuzz“ (durch 3 und 5) an.
4. Falls die Zahl weder durch 3 noch durch 5 teilbar ist, gib die Zahl als normale Nummer an.
5. Um die im Spiel erlangten Punkte zurückzusetzen, betätige den Button „Reset Points“.

### So funktioniert das Spiel im Überblick:
1. Eine Zahl zwischen 1 und 999 wird präsentiert.
2. Der Spieler entscheidet, ob die Zahl:
    - durch 3 (Fizz),
    - durch 5 (Buzz) oder
    - durch 3 und 5 (FizzBuzz) teilbar ist.
3. Ist die Antwort korrekt, gibt es Punkte.
4. Ist die Zahl durch keine dieser Zahlen teilbar, gibt der Spieler sie als normale Nummer an.
5. Falsche Antworten bringen keine Punkte.

Viel Spaß beim Spielen und Punkte sammeln!

```mermaid
classDiagram
    class FBS_Script {
        // Attribute
        + Text rannumtxt
        + Text gamepoints
        + Text infotext
        + Button fizzbtn
        + Button buzzbtn
        + Button fizzbuzzbtn
        + Button normnumbtn
        + Button newnumbtn
        + Button resetButton
        + Image backround
        + AudioSource correct
        + AudioSource incorrect
        + int randnum
        + int points
        + int fizz = 3
        + int buzz = 5
        + string[] antworten

        // Methoden
        + void Start()
        + void Update()
        + void IncorrectAnswer()
        + void CorrectAnswer()
        + void ResetPoints()
        + void RandomNumber()
        + void CheckFizzBuzz()
        + void CheckFizz()
        + void CheckBuzz()
        + void CheckNormalNumber()
    }

    FBS_Script : rannumtxt
    FBS_Script : gamepoints
    FBS_Script : infotext
    FBS_Script : fizzbtn
    FBS_Script : buzzbtn
    FBS_Script : fizzbuzzbtn
    FBS_Script : normnumbtn
    FBS_Script : newnumbtn
    FBS_Script : resetButton
    FBS_Script : backround
    FBS_Script : correct
    FBS_Script : incorrect
    FBS_Script : randnum
    FBS_Script : points
    FBS_Script : fizz
    FBS_Script : buzz
    FBS_Script : antworten
    FBS_Script : Start() void
    FBS_Script : Update() void
    FBS_Script : IncorrectAnswer() void
    FBS_Script : CorrectAnswer() void
    FBS_Script : ResetPoints() void
    FBS_Script : RandomNumber() void
    FBS_Script : CheckFizzBuzz() void
    FBS_Script : CheckFizz() void
    FBS_Script : CheckBuzz() void
    FBS_Script : CheckNormalNumber() void
