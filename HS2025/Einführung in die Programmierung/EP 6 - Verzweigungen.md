#HS2025 #EP 

```java
int x = 15;
double y = 0;
y = 2.5
x = (int)(x * y); //Cast verhindert Compilerfehler
y = x + y + 0.5;
```

## Standarddarstellung als String

- Für primitive Typen und Strings wie erwartet. 
- Verkettung mit der Standarddarstellung des anderen Werts
	- "Olympia " + 2024 ergibt "Olympia 2024"
- 2 + 3 + " Zehen" ergibt "5 Zehen"
- "Nummer " + 3 + 2 ergibt "Nummer 32

## Interaktive Programme (Eingabe)

- Konsole
	- Standard-Eingabe `System.in`
	- Standard-Ausgabe
- Scanner: Syntax
	- Scanner aus Bibliothek `java.util` importieren
		- `import java.util.Scanner`
	- `Scanner`-Objekt konstruieren mit Angabe der Eingabequelle
		- `Scanner name = new Scanner(system.in);`

| Method          | Description                                 |
| --------------- | ------------------------------------------- |
| `nextInt();`    | reads an `int` from the user and returns it |
| `nextDouble();` | ...                                         |
| `next();`       | ...                                         |
| `nextLine();`   | ...                                         |

## Zufallszahlen (random numbers)

- (Pseudo-)Zufallszahlengenerator `Random`
	- `Random` aus Bibliothek `java.util` importieren
		- `import java.util.Random;`
	- `Random`-Objekt konstruieren
		- `Random name = new Random();`
	- Verschiedene Methoden für unterschiedliche Modi

| Method         | Description                                                                                                          |
| -------------- | -------------------------------------------------------------------------------------------------------------------- |
| `nextInt()`    | returns a "random integer"                                                                                           |
| `nextInt(n)`   | returns a "random integer" in the range \[0, n)<br>in other words: returns a number from {0 , ... , n-1} at "random" |
| `nextDouble()` | returns a "random real number" in the range \[0.0, 1.0)                                                              |

**Häufige Szenarien**
- Zufällige ganze Zahl aus \[1, n]
	- `1 + rand.nextInt(n);`
- Zufällige ganze Zahl aus \[min, max]
	- `min + rand.nextInt(max - min + 1);`
- Zufällige reelle Zahl aus \[min, max)
	- `min + rand.nextDouble() * (max - min)`
- Zufälliges Objekt aus einer Menge von n Objekten
	- Beliebige Nummerierung der Objekte mit \[1, n] oder \[0, n-1]
## Verzweigungen

### If-Anweisung

Führe eine Gruppe A von Anweisungen nur dann aus, wenn eine Bedingung `test` wahr ist.

### If-else-Anweisung

Führe entweder eine Gruppe A von Anweisungen oder eine Gruppe B aus, abhängig von Bedingung `test`. 

### Vergleiche

| ==  | gleich         |
| --- | -------------- |
| !=  | ungleich       |
| <   | kleiner als    |
| \>  | grösser als    |
| <=  | kleiner gleich |
| \>= | grösser gleich |


### Logische Operatoren

| &&   | und   |
| ---- | ----- |
| \|\| | oder  |
| !    | nicht |


