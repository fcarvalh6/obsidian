#HS2025 #EP 

## NullPointerException

Auf null können keine Operationen ausgeführt werden. 

Vermeiden durch `if(data != null && data.length() > 0)`

## Unerreichbare Objekte

Wenn keine Referenzvariable mehr auf ein Objekt zeigt, dann ist das Objekt unerreichbar. Es wird irgendwann vom Java-Laufzeitsystem entfernt werden ("garbage collection")

## Array-Methoden

### Replace 

`replace(what, array, with)`

```java
public static void replace(int what, int[] array, int with){
	for(int i = 0; i < array.length; i++){
		if(array[i] == what){
			array[i] = with;
		}
	}
}
```

### All True

```java
public static boolean allTrue(boolean[] a){
	for(int i = 0; i < a.length; i++){
		if(!a[i]) return false;
	}
	return true;
}
```

### Concatenation

```java
public static int[] concat(int[] first, int[] second){
	int[] result = new int[first.length + second.length];
	for(int i = 0; i < first.length; i++){
		result[i] = first[i];
	}
	for(int i = 0; i < second.length; i++){
		result[first.length+i] = second[i];
	}
	return result;
}
```

## Was Arrays nicht können

- arithmetische Operatoren
- relationalen Operatoren
- vergrössern/verkleinern
- `println`
- `==`
- `arrA.equals(arrB)`

### Mehrdimensionale Arrays

Ein Array von Arrays des gleichen Typs, nützlich für Tabellen und Matrizen.

```java
type[][] name; //Deklaration ohne Erstellung

type[][] name = new type[nRows][nColumns]; //Dek. mit Initialisierung

System.out.println(Arrays.deepToString(name))

for(int row = 0; row < name.length; row++){
	for(int column = 0; column < name[row].length; column++){
		//block
	}
}
```

## Rekursion

Methode ruft sich selbst auf.

```java title:Fakultät
public static int factorial(int n){
	if (n <= 1) {
		return 1;
	}else return n * factorial(n-1);
}
```

```java title:Count

```