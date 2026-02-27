#FS2026 #PP 

### Parallelism vs Concurrency
- Concurrency means there are multiple active processes making progress at a given time. This is possible even in single-processor systems by simply switching from one process to the next repeatedly. This gives the *illusion* of parallelism. 
- Parallelism means there are multiple things happening at the same time, say each core in a CPU is summing a number at exactly the same time. 
- Parallelism implies concurrency, but concurrency does not imply parallelism. 

### Processes vs Threads
- Threads are smaller units of execution, a process can be split into multiple threads. 
- Processes have separate memory "spaces", while threads all share the same heap. 
- Context switching between processes is a lot more costly than simply going from thread to thread. 

### Lifecycle of Threads
- When a thread is started, it receives the *runnable* status, this means it is waiting to access the CPU and change into the *running* state. Threads are not always runnable for diverse reasons. Maybe it wants to access a block currently guarded by a lock it doesn't possess (more on this later), maybe it is waiting for I/O, etc. In these states, it is *not runnable*. After a thread is done executing, it counts as *terminated*.  

### Interleaving
- Instructions inside a thread are always executed in the specified order, but instructions between any number of threads are decided by **interleaving**, which is unpredictable and not deterministic. 

### Thread Attributes
- `ID` - unique identifier
- `Name` - name of the thread, can be modified
- `Priority` - threads with higher priority are favored by the scheduler
- `State` - running, terminated, runnable, etc. 

### Waiting for Threads
- One can have a loop which always checks if all threads are terminated before proceeding. This is called **busy waiting**. Having the main thread constantly spinning while waiting can be rather inefficient. 
- One can use the `.join()` method to wait for the thread to finish while **sleeping**. This incurs contexts switch overhead and can sometimes have worse performance than busy waiting.  

### Issues with Threads
- An exception in a thread will not always lead to the main method being notified and can lead to errors later on. It is important to always catch these exceptions.
- If a thread does not terminate, main could wait forever. This can be handled using the `.interrupt()` method. 
