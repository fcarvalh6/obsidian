#HS2025 #EP 

## Allgemeine Programmstruktur

Jedes (ausführbare) Java-Programm besteht aus
1. Einer Datei mit Namen "*ProgrammName.java*"
2. die eine Klasse namens "*ProgrammName*" hat
3. die eine Methode namens "*main*" enthält
	- die eine Reihe von Anweisungen enthält
	- die automatisch ausgeführt wird

## Methoden

Warum?
- Methoden strukturieren die Anweisungen
- Methoden erlauben es, Wiederholungen zu vermeiden
- Jede Methode stellt eine neue, spezialisierte Anweisung dar

"Rezept"
1. Gesamtaufgabe in Teilaufgaben zerlegen
2. Teilaufgaben in separaten Methoden lösen
3. Teillösungen zu Gesamtlösung Zusammensetzen

```java title:Rakete
public class AsciiRocketv2 {
	//Gesamtlösung
	public static void main(string[] args){
		printHat();
		printLine();
		printBlock();
		printLine();
		printBlock();
		printLine();
		printHat();
	}
	
	public static void printLine(){
		System.out.println("+------+");
	}
	
	public static void printHat() {
		System.out.println("   /\\");
		System.out.println("  /  \\");
		System.out.println(" /    \\");
	}
	
	public static void printBlock() {
		System.out.println("|  NA  |");
		System.out.println("|  SA  |");
	}
}
```