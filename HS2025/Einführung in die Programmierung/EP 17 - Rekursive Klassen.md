#HS2025 #EP 

## Rekursive Java-Klassen

Klasse besitzt Attribut vom gleichen Typ.

```java
class ListNode {
	int value;
	ListNode next;
}
```

```java
public class LinkedList {
	private ListNode front;
	
	public LinkedList() {
		front = null;
	} 
}
```


## Verschachtelte Klassen

```java
public class OuterClass {
	...
	private class InnerClass {
		...
	}
}
```

- Innere Klasse (nur) innerhalb der äusseren Klassen sichtbar
- %

## Methoden

```java
int size() {
	int counter = 0;
	ListNode current = front;
	
	while(current != null) {
		counter++;
		current = current.next;
	}
	return counter;
}
```

```java
public int get(int index) {
	ListNode current = front;
	while(){
	%
	}
}
```

