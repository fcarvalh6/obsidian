#FS2026 #PP 

Present here:
- Chapters 1 to 3 of Goetz

### Chapter 1 - Introduction
*"Threads are the easiest way to tap the computing power of multiprocessor systems"*
- Threads are also called **lightweight processes**
- On most modern OS's, they are the basic units of scheduling
- Threads are even helpful in single-processor systems. Say one thread is waiting for I/O, which is generally slow. Another thread access the processor while the other thread waits. 
- Things to be mindful of:
	- One thread can modify a variable another thread is using. This is undesirable and unpredictable. 
	- The order in which operations are performed across threads is unpredictable and not deterministic. 
	- Threads can be confused by having data change unexpectedly.
	- Threads can be stuck in a state where they cannot make any progress, this is a **liveness failure** (e.g. livelock, deadlock and starvation).
- However, we can "solve" most of these problems by coordinating multi-threaded execution using the tools provided to us by Java! This is usually called **synchronization** and it is how we coordinate the execution of multiple threads.
- What's important to keep in mind is that **initializing** and **context switching**, among others, represent a thread overhead which can sometimes impact the final execution time negatively.
- In the end, we want to write more productive programs by making use of parallel execution, and we use **synchronization** to ensure correctness. 

### Chapter 2 - Thread Safety
- Our programs will make use of objects. More specifically, our threads will make use of objects in parallel. 
- We **don't** want the use of our objects/classes to cause errors because of parallelism, so we must ensure they are **thread safe**. 
- If an object is accessed by multiple threads, it **must** be thread-safe.
- It is a lot easier to design a class as thread-safe from the start than to modify an existing thread-unsafe class.
- If many threads are accessing a mutable state variable and they are not synchronized, there is something wrong. You can fix it by:
	- not sharing the state variable across threads
	- making it immutable
	- synchronizing the access
- Moreover, the classical object-oriented techniques will help build thread-safe classes:
	- encapsulation
	- immutability
	- clear specification of invariants

#### What is Thread Safety?
A class is thread-safe when it behaves correctly no matter the scheduling and interleaving execution of those threads. This safety does not depend at all on the calling program.

#### Atomicity
- Say you have a "hit-counter". Two threads want to register a new hit at the same time. They both read $n$ hits, add one, and write $n+1$. In reality, the proper value would be $n+2$. This happens because the increment operation is not **atomic**. 
- Two operations are atomic in relation to each other if one always is executed completely before the other. 
- If we (somehow...) made the increment operation atomic in relation to itself, then the example above would work properly, because the second increment operation would only execute after the first one is done completely. 
- One option to unsure atomicity is using a type in `java.util.concurrent.atomic` such as `AtomicLong`.
- Another, more flexible option, is using **locks**. 

#### Intrinsic Locks
- Intrinsic locks will ensure that, at any time, only one thread has access to the code block it guards.
- In Java, they can be implemented by using `synchronized blocks`. 

```java title:"synchronized example"
synchronized (lock) {
	// Access to modify shared state guarded by lock
}
```

- Intrinsic locks are reentrant, meaning if a thread tries accessing a lock it already holds, the requests succeeds. 
- Every shared, mutable variable should be guarded by exactly one lock. 
- Common locking convention: 
	- encapsulate all mutable states within an object
	- synchronize all accesses using the object's intrinsic lock

### Chapter 3 - Sharing Objects
- Objects are (often) shared between multiple threads. This poses risks such as those mentioned previously, but also a more subtle one: **memory visibility**.
- Basically, there is nothing that guarantees another thread will read a value modified by another thread in due time or at all. Moreover, there is nothing that guarantees operations will be performed in order. 

#### Stale Data
- Because of the above mentioned properties, a thread can read an old value that was already modified, this is **stale data.**
- Usually, stale data is bad, but not too bad, because it is still data which was placed there by another thread, it's not just some random value. 
- However, there are cases where the value read is a random value, such as with 64-bit operations. Reading/writing a `long` or `double` (not declared `volatile`) can be interpreted by the JVM as two 32-bit operations, so our stale value is now two values chopped and stitched together. 
- This makes locks even more powerful, since they can also be used to ensure all threads receive the freshest, up-to-date values. 

#### Volatile Variables
- By declaring a mutable value as `volatile`, the compiler/JVM know to not mess around and mix operations related to this variable with other memory operations. 
- However, locks are still stronger and more flexible:
	- volatile variables can guarantee visibility, but not atomicity. Locking can guarantee both. For example, the semantics of volatile cannot make an increment operation atomic. 
	- Code that relies on volatile variables for visibility is usually not as clear or resilient as code using locks. 
- There are still good uses for volatile variables, such as ensuring the visibility of object states or indicating an important lifecycle event (initialization, shutdown) has occurred. 

#### Publication and Escape
- **Publishing** an object means making it available to code outside of its current scope.
- If an object was published when it should not have been, it has **escaped**. For example, say you stored a reference to the object in a public static field, it already escaped...
- If we are publishing an object, we cannot let the reference escape during construction, since this would allow other threads to access an object which isn't necessarily fully constructed. Starting a thread during construction also does exactly that. 

#### Thread Confinement
- If all this sharing business sounds too complicated, there's an alternative: not sharing. This means every object is confined to a single thread. 
- One can ensure object confinement through a couple methods, such as using the `ThreadLocal` class. However, the use of these variables have downsides akin to those of global variables. 

#### Immutability
- If an object has a state which cannot be changed, there is no opportunity for threads causing issues, so they are all automatically thread-safe. 
- An object is immutable if:
	- its state cannot be modified after construction
	- all its fields are `final`
	- it is properly constructed (no escaping during construction)
- Final fields can't be modified and they are also useful to ensure initialization safety. 
- Even if an object is mutable, it is still a good practice to make it as immutable as possible (by, for example, declaring fields as final whenever possible).

#### Safe Publication
- A properly constructed object can be published safely by:
	- Initializing reference from static initializer
	- Storing reference in a volatile field or `AtomicReference`
	- Storing reference in a final field of a properly constructed object
	- Storing reference in a field properly guarded by a lock
- When available, the first option is usually the easiest.

#### Mutable Objects
- Publication requirements depend on object mutability: 
	- Immutable objects can be published by any mechanism
	- Effectively immutable objects must be safely published
	- Mutable objects must be safely published and thread-safe/guarded by lock
