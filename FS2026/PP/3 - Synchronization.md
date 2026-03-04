#FS2026 #PP 

- Say we have two threads who add/subtract $1$ to a shared variable for $n$ ticks. Both threads are fighting over the same variable, so a stale value could be read, a correct value could be overwritten, etc. This is a **data race**.
- Terminology:
	- **Data race (low-level race condition):** bad behavior caused by insufficiently synchronized access to a shared memory location.
	- **Bad interleaving (high-level race condition):** bad behavior caused by "unlucky" execution order between multiple threads.
	- **Critical section:** part of a program only one thread should execute at a time
- Again, we must **synchronize** the interaction between parallel threads, this stops them from "stepping on each other's toes".
- **Synchronized blocks** ensure mutual exclusion
- **Synchronized methods** encapsulate all method contents in a synchronized block
- Every object has an **implicit lock**, but we can also declare locks explicitly so that a class can have, for example, two counters which are not mutually exclusively increased between themselves.
- We present a **producer/consumer** program where a buffer is filled with tasks by producers and consumers take the tasks to perform them. Here, it is important that threads wait whenever the buffer is empty and spring into action when a new task is added. 

First, let's try solving this using a simple while loop. 

```java title:v1
// Consumer thread
public void run() {
	while (true) {
		while (buffer.isEmpty()); // Spin until item available
		performLongRunningComputation(buffer.remove());
	}
}

// Producer thread
public void run() {
	// . . .
	while (true) {
		prime = computeNextPrime(prime);
		buffer.add(prime);
	}
}
```

This does not work since the buffer could be emptied between the waiting loop and the call to the computation method, leading to an error. Let's try using synchronized blocks.

```java title:v2
// Consumer thread
public void run() {
	long prime;
	while (true) {
		synchronize (buffer){
			while (buffer.isEmpty()); // Spin until item available
			prime = buffer.remove();
		}
		performLongRunningComputation(prime);
	}
}

// Producer thread
public void run() {
	// . . .
	while (true) {
		prime = computeNextPrime(prime);
		synchronize (buffer) {
			buffer.add(prime);
		}
	}
}
```

This also does not work because whenever the consumer enters the synchronized block to wait for the buffer to be filled, all producers are locked out because they also use the buffer lock, this is a **deadlock**. We would like to tell threads to wait until they are notified by the producer that buffer is not empty anymore. Thankfully, there are java methods for this functionality!

```java title:v3
// Consumer thread
public void run() {
	long prime;
	while (true) {
		synchronize (buffer){
			while (buffer.isEmpty())
				buffer.wait(); // goes to sleep AND gives up lock
			prime = buffer.remove();
		}
		performLongRunningComputation(prime);
	}
}

// Producer thread
public void run() {
	// . . .
	while (true) {
		prime = computeNextPrime(prime);
		synchronize (buffer) {
			buffer.add(prime);
			buffer.notifyAll(); // wakes up threads waiting for lock
		}
	}
}
```

This works as intended, because when the consumer thread is sent to sleep, it gives up the lock and allows a producer to access the buffer. After something is added, all threads are woken up.  

Methods:
- `wait()` releases lock and sends thread to an internal waiting queue
- `notify()` wakes up the highest-priority thread closest to the front of the queue
- `notifyAll()` wakes up all waiting threads (they will now compete for the lock)