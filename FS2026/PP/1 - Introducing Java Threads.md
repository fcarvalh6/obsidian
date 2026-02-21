#FS2026 #PP 

### Thread Class
- Documentation: https://docs.oracle.com/javase/8/docs/api/java/lang/Thread.html
- Java has a public class called "Thread" in `java.lang` (usually, the functionality in `.lang` works without needing explicit imports)
- Threads have attributes regarding its priority. Threads with a higher number in these fields are executed in preference. 

### Creating a Thread
- Source: https://www.geeksforgeeks.org/java/java-threads/
- To create a thread, can either extend the `Thread` class or implement the `Runnable` interface 
- Both approaches have the same result, but if your thread already extends a class then you'd have to implement the interface, e.g. `class ComplexCalculation extends Calculation implements Runnable` 
- Overriding the `run` method allows you to define what your new thread class will do.

```java title:"Extending Thread Class"
	class TestExtends extends Thread {
		@Override
		public void run(){
			System.out.println("This thread is running...");
		}
	}
	
	public static void main (String[] args){
		TestExtends t = new TestExtends();
		// execute thread (more on this later)
	}
```

```java title:"Implementing Runnable Interface"
	class TestImplements implements Runnable {
		@Override
		public void run(){
			System.out.println("This thread is running...");
		}
	}
	
	public static void main (String[] args){
		TestImplements t = new TestImplements();
		// need to create a thread object by passing the interface
		Thread t = new Thread(r);
		// execute thread (more on this later)
	}
```

### Executing Threads
- Sources: 
	- https://www.geeksforgeeks.org/java/java-threads/
	- https://jonas-wetzel.notion.site/pprog26
- Calling the `.run` method directly would behave exactly like a normal method call
- Calling the `.start` method initiates a thread and calls `.run` in parallel
- Calling the `.join` method waits for the thread to "die" (used to wait until all threads are done)

```java title:"Simple Example"
	// creating threads
	TestExtends t1 = new TestExtends();
    TestExtends t2 = new TestExtends();
    
    // starting threads
    t1.start();
    t2.start();
	
	// waiting for threads to finish
	t1.join();
	t2.join();
```

For a more involved example which also demonstrates speedup see Jonas Wetzel's website. Describing that code is outside of the scope of this note. 