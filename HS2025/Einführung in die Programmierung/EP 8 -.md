#HS2025 #EP 

## Namensräume (*scopes*)

Teil des Programms, in dem ein Name/Symbol sichtbar ist
- von der Deklaration bis zum ende des aktuellen Blocks (durch { } begrenzt)

## Methodenüberladung
- Signatur einer Methode: Name und Liste der Parametertypen
	- Mehrere Methoden mit der gleichen Signatur sind nicht erlaubt
	- Mehrere Methoden mit dem gleichen Name sind erlaubt, sofern die Signaturen nicht gleich sind.

```java title:Signaturen
public static String foo(int a, double b){
	return "int double";
}
public static String foo(double a, int b){
	return "double int";
}
foo(1, 1.0); //returns "int double"
foo(1.0, 1); //returns "double int"
foo(1.0, 1.0); //ERROR: no matching method
foo(1, 1); //ERROR: both methods match (ambiguous)
```

## Inkrement und Dekrement

```java title:PostInkrement
int x = 2;
int y = x++;
System.out.println(x);//prints 3
System.out.println(y);//prints 2
```

```java title:PräInkrement
++var;
```

## Benutzergesteuerte Schleifen

```java title:Taschenrechner
Scanner console = new Scanner(System.in)
int sum = 0
int number;

do{
	System.out.print("Enter a number (0 to quit)");
	number = console.nextInt();
	sum = sum + number;
}while(number != 0);

System.out.println("The total is " + sum);
```