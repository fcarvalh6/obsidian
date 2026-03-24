#FS2026 #PP 

- Thinking about how hardware was optimized for a single thread may give us insights that help us produce better parallel code.
- Programs are a series of instructions and the way in which instructions are executed can be made faster. 
- We would like to have better **throughput** and less **stalls**, but there is a limit, which is when **multicore** systems come into play. 
- In multicore systems, there is more work on the software level to ensure the hardware is used to its best ability. 
- One of the most important optimizations is **pipelining**, which, in essence, will separate every instruction into different parts which can be executed at the same time. 
- A basic pipeline consists of:
	- Instruction Fetch
	- Instruction Decode
	- Execution
	- Memory Access
	- Write-Back
- Note that fast code is not necessarily efficient. 
- There could always be some bottlenecks, such as data structures or algorithms themselves. 
- Consider $T_{p}$ to be the time to execute after parallelization on $p$ devices
- Consider $T_{1}$ to be the sequential execution time
- We will usually observe that $T_{p}>T_{1}/p$ (performance loss)
- Our speedup will be $S_{p}=T_{1}/T_{p}$ and efficiency $S_{p}/p$.
- To examine scalability, $T_{1}$ should probably be the time to execute the parallel program in a single component.
- The fairest comparison would be to set $T_{1}$ as the optimized sequential program. 
- **Amdahl's Law** will describe a limit to the speedup that can be obtained based on how much of the program must execute sequentially. This makes sense, as no matter how quick the parallel part runs, the sequential part will limit the total speedup. 
- If $f$ is the non-parallelizable serial fractions of the total work, then the following equalities hold:
- $W_{\text{ser}}=fT_{1}$ (time spent doing non-parallelizable work)
- $W_{\text{par}}=(1-f)T_{1}$ (time spent doing parallelizable work)
- Which gives:

$$
S_{p}\le \frac{1}{f+\frac{1-f}{P}}
$$
TODO: add Gustafson's law
