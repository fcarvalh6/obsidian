#HS2025 #EP 

% - 02.10.2025

```java title:ForLoop
for (int i = 1; i <= 5; i = i + 1) {
	System.out.println(i); // 1 2 3 4 5
}
```

```java title:NestedLoops
for (int i = 1; i <= 5; i = i + 1) {
	for (int j = 1; j <= 10; j = j + 1) {
	...
	}
}
```

## Typen von Schleifen

- **Bestimmte Schleife** (*definite loop*) oder **Zählschleife** (*counting loop*)
	- Anzahl Iterationen ist vor Beginn der Ausführung der Schleife bekannt
- **Unbestimmte Schleife** (*indefinite loop*)
	- Anzahl Iterationen nicht vor Beginn klar

```java title:WhileLoop
int num = 1;
while (num * num <= 2000) {
	System.out.println(num + " ");
	num = num * 2;
}
```

```java title:NichtTrivialerTeiler
int n = 91;
int factor = 2;
while (n % factor != 0) {
	factor = factor + 1;
}
System.out.println("first divisor is " + factor);
```

## Methoden II

```java title:Parameter 
public static void main (String[] args) {
	echoPIN(123456);
	echoPIN(40 + 2);
}

public static void echoPIN (int pin) {
	System.out.println("Die Geheimnummer ist " + pin);
}
```

## Wertübergabe (*value semantics*)

- Primitive Parametertypen (int, boolean, ...)
	- Ausdruck wird evaluiert und Ergebnis in Parameter-Variable **kopiert**
	- Aufgerufene Methode erhält nur **Kopie** des Werts

