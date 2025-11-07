#HS2025 #EP 

```java 
public class Point {
	int x;
	int y;
}
```


| Methode                 | Beschreibung |
| ----------------------- | ------------ |
| getSlope()              |              |
| setLocation(x,y)        |              |
| translate(dx,dy)        |              |
| getDistance(p)          |              |
| getDistanceFromOrigin() |              |

```java
public class Point {
	int x;
	int y;
	
	double getSlope(){
		// assert x != 0
		return (double)(this.y)/(this.x)
	}
	
	void setLocation(int x,int y){
		this.x = x;
		this.y = y;
	}
	
	void translate(int dx,int dy){
		this.x += dx;
		this.y += dy;
	}
	
	double getDistance(Point p){
		double pow1 = Math.pow(p.x - this.x, 2);
		double pow2 = Math.pow(p.y - this.y, 2);
		return Math.sqrt(pow1 + pow2);
	}
	
	double getDistanceFromOrigin(){
		return getDistance(new Point());
	}
}
```

% - toString

## Konstruktoren

Ein **Konstruktor** initialisiert den Zustand eines neuen Objektes. 

```java title:Konstruktoren
public class Point {
	int x;
	int y;
	
	public Point(int x, int y){
		this.x = x;
		this.y = y;
	}
	
	public Point(Point other){
		this.x = other.x;
		this.y = other.y;
	}
	
	public Point(){
		this(0,0);
	}
}
```

Wenn kein eigener Konstruktor deklariert wird, stellt Java den Standard/Default-Konstruktor... %

## Datenkapselung

```java
public class Rational {
	int numerator;
	int denominator;
}
```

Nur konsistent, falls denominator != 0, eine solche Konsistenzbedingung heisst auch Objektinvariante.

Attribute können durch Zugriffsmodifikatoren in ihrer Sichtbarkeit eingeschränkt werden.

```java
public type attribute // für alle Klienten sichtbar

private type attribute // nur für Objekte derselben Klasse sichtbar
```

```java
public class Rational {
	private int num;
	private int den; 
	
	// constructor
	public Rational(int n, int d) {
		// assert d != 0
		num = n;
		den = d;
	}
	
	// getters
	public int getNumerator() {
		return num;
	}
	
	public int getDenominator() {
		return den;
	}
	
	// setters
	public void setNominator(int n) {
		num = n;
	}
	
	public void setDenominator(int d) {
		// assert d != 0
		den = d;
	}
}
```

Private Attribute einer Klasse sind für alle Objekte dieser Klasse sichtbar.

