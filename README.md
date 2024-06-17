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
graph TD
    Start --> Init[Initialize Variables]
    Init --> WaitForInput[Wait for Input]

    WaitForInput -->|UpArrow/Button| CheckFizzBuzz
    WaitForInput -->|DownArrow/Button| CheckNorm
    WaitForInput -->|LeftArrow/Button| CheckFizz
    WaitForInput -->|RightArrow/Button| CheckBuzz
    WaitForInput -->|Space/Button| GenerateRandomNumber

    CheckFizzBuzz -->|Correct| CorrectAnswer
    CheckFizzBuzz -->|Incorrect| IncorrectAnswer

    CheckFizz -->|Correct| CorrectAnswer
    CheckFizz -->|Incorrect| IncorrectAnswer

    CheckBuzz -->|Correct| CorrectAnswer
    CheckBuzz -->|Incorrect| IncorrectAnswer

    CheckNorm -->|Correct| CorrectAnswer
    CheckNorm -->|Incorrect| IncorrectAnswer

    GenerateRandomNumber --> ResetBackground
    ResetBackground --> WaitForInput

    CorrectAnswer --> UpdatePoints
    IncorrectAnswer --> UpdateBackgroundRed

    UpdatePoints --> WaitForInput
    UpdateBackgroundRed --> WaitForInput

    subgraph Logic
        CheckFizzBuzz
        CheckFizz
        CheckBuzz
        CheckNorm
        GenerateRandomNumber
    end

    subgraph Responses
        CorrectAnswer
        IncorrectAnswer
    end

    subgraph States
        Init
        WaitForInput
        UpdatePoints
        UpdateBackgroundRed
        ResetBackground
    end
