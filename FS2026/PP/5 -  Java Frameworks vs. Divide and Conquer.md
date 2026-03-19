#FS2026 #PP 

- Until now, we have learned about java threads. However, manually creating and assigning threads is bad. Programmers should focus on on designing good parallel algorithms rather than busying themselves with coordinating threads. 
- Java provides **frameworks** which do the work for us, but it is important to know how they work to make better use of them. 

## Summing elements of an array in parallel
- We would like to split the array into many pieces and have each thread sum those elements up in parallel. 
- This is a classic **divide and conquer** algorithm. More specifically, this is an example of **fork-join** programming.
- Fork-join programming is helpful since it attempts to eliminate race conditions by delegating each piece of memory to a single thread (forking), allowing them to work on them individually, and then combining the results (joining). 

### Using java threads
- If we attempt to recursively start new threads to sum smaller subarrays, we have two problems: 
	- we will very quickly run out of memory.
	- the thread overhead will make this parallel approach more costly than the sequential one. 
- both of these problems stem from the fact java threads are quite heavyweight. 
- these problems can be diminished by having a **sequential cutoff** and by starting one thread while running the other (cuts number of threads generated in half)
- this is not optimal. In the end, we are still trying to fix issues introduced by java's thread framework because it is not optimized for this task. 

```java title:"Thread example"

public class SumThread extends Thread { // or implement runnable
	int[] xs;
	int h, l;
	int result; // No return value supported, need result field

	public SumThread(int[] xs, int l, int h){
	super();
	this.xs = xs;
	this.h = h;
	this.l = l;
}

public void run(){
	int size = h-l;
	if (size < SEQ_CUTOFF) // Sequential cutoff
		for (int i = l; i < h; i++)
			result += xs[i];
	else {
		int mid = size / 2;
		SumThread t1 = new SumThread(xs, l, l + mid);
		SumThread t2 = new SumThread(xs, l + mid, h);
		t1.start();
		t2.start();
		t1.join();
		t2.join();
		result = t1.result + t2.result;
	}
	
	int mid = size / 2;
	SumThread t1 = new SumThread(xs, l, l + mid);
	SumThread t2 = new SumThread(xs, l + mid, h);

	t1.start();
	t2.run(); // Only starting one thread
	t1.join();
	
	result = t1.result + t2.result;
}
```

### Using an executor service
- An executor service assigns a set of tasks to an available thread in a thread pool. 
- After assigning the task, the user who submitted the task gets a **Future** (basically, a variable which in the future will receive a  return value).
- The executor service is also not adequate for the problem at hand, because once a task is submitted, the thread which submitted it will wait idly until the future is returned, and we quickly approach a state where there are no more available threads in the pool and the executor "freezes", deadlock. 
- The executor framework is not adequate for recursive problems which have deep structures. It is better suited for flat structures or independent tasks. 

```java title:"Executor example"
public class SumTask implements Runnable{
	// Implementation
	public Integer call() throws Exception {
		int size = h – l;
		if (size == 1)
			return xs[l];
		
		int mid = size / 2;
		sumRecCall c1 = new sumRecCall(ex, xs, l, l + mid);
		sumRecCall c2 = new sumRecCall(ex, xs, l + mid, h);
		
		Future<Integer> f1 = ex.submit(c1);
		Future<Integer> f2 = ex.submit(c2);
		
		return f1.get() + f2.get();
	}
	public static void main(Strig[] args){
		//...
		ExecutorService exs = Executors.newFixedThreadPool(4);
		//...
		firstTask.execute();
	}
} 
```

### Using ForkJoin
- The ForkJoin framework was developed with these problems in mind. 
- It works similarly to the executor service on the surface.
	- Work is partitioned into smaller parts through divide and conquer. 
	- Tasks are submitted to the FJ interface.
	- Framework assigns tasks to FJ threads. 
- Obs: it is still important to do previous optimizations such as sequential cutoffs and starting a task in the thread itself. Tasks should perform around 100-10000 basic operations before being split.
- In FJ, there is a global queue of tasks and each thread has their own local queue. Work on local queues can be stolen by other threads. 

```java title:"ForkJoin example"
class Globals {
	static ForkJoinPool fjpool = new ForkJoinPool();
}

static long sumArray(int[] arr){
	return Globals.fjpool.invoke(new SumForkJoin(arr, 0, arr.length))
}

class SumForkJoin extends RecursiveTask<Long> {
	int low;
	int high;
	int[] array;

	SumForkJoin(int[] arr, int lo, int hi) {
		array = arr;
		low = lo;
		high = hi;
	}
	
	protected Long compute() {
		if(high - low <= SEQUENTIAL_THRESHOLD) {
			long sum = 0;
			for(int i=low; i < high; ++i)
				sum += array[i];
			return sum;
		} else {
			int mid = low + (high - low) / 2;
			SumForkJoin left = new SumForkJoin(array, low, mid);
			SumForkJoin right = new SumForkJoin(array, mid, high);

			left.fork(); // Submitted
			long rightAns = right.compute(); // Not submitted
			long leftAns = left.join();
			return leftAns + rightAns;
		}
	}
```

