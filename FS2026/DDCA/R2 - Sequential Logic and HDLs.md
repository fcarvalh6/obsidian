#FS2026 #DDCA 

Assigned reading:
- H: Chapters 3 and 4
- P: Chapter 3

## H

### Chapter 3 - Sequential Logic Design
- Sequential logic circuits are circuits that can remember prior input values.
- These circuits can assume a certain state which can be described by a state variable. 

#### Cross-Coupled Inverters
- Two cross-coupled NOT gates
- Can store information
- This presents two problems:
	- How can we set the value we want to be stored?
	- How can we prevent metastable states?

#### SR Latch
- Two cross-coupled NOR gates
- Solves the setting problem:
	- Setting S to 0 stores 1 (set)
	- Setting R to 0 stores 0 (reset)
- Setting both to 1 keeps the previous value stored
- Does not solve both issues, since setting both to 0 leads to a metastable state

#### D Latch
- SR Latch with two safeguards:
	- Only one data input, D, which represents the bit to be stored (prevents setting both S and R to 0)
	- Clock (also called WE) input to define when the latch is sensitive to writes or not
- This presents another issue: we want to synchronize changes on the rising edge of the clock, but D latches are sensitive for the entire high period. 

#### D Flip-Flop
- Two D latches in a row controlled by complementary clocks
- Solves the rising edge issue
- A **register** is a bank of N flip-flops sharing the same clock
- In general, latches will describe circuits sensitive during the stable high clock period and flip-flops describe those sensitive only during the rising edge

#### Synchronous Sequential Circuits
- Combinational logic feeds into registers, etc. 
- The registers store state, all state changes should be synchronized to the clock
- Rules of SSCs
	- Every circuit is either combinational logic or a register
	- At least one register to store state
	- All register are synced to the same clock signal
	- Every cycle path has at least one register
- In asynchronous circuits, timing is not limited by clocked registers

#### Finite State Machines
- Machine with finite states (duh)
- $k$ registers mean a circuit can be in one of $2^{k}$ states (finite)
- In **Moore Machines**, outputs only depend on current state
- In **Mealy Machines**, outputs depend on current state and current input
- Diagram representation: circles are states and arcs are transitions
- One can encode states in an FSM using binary or one-hot encoding
- To design an FSM:
	- Identify inputs and outputs
	- Sketch state transition diagram
	- Moore:
		- Write state transition table
		- Write output table
	- Mealy:
		- Write combined state transition and output table
	- Select state encodings (only affects hardware design)
	- Write boolean equations for state transition and output logic
	- Sketch circuit schematic

#### Timing of Sequential Logic
- What happens if $D$ changes at the same time the clock rises? We need to be careful about timing. 
- $t_{ccq}$ : clock-to-Q contamination delay, outputs may start to change after this
- $t_{pcq}$ : clock-to-Q propagation delay, outputs may settle within this
- $t_{setup}$ : inputs must have stabilized for this much before rising edge
- $t_{hold}$ : inputs must be held for this much after rising edge

#### Parallelism
- a **token** is a group of inputs that are processed
- the **latency** is the time required for a token to pass through the circuit
- the **throughput** is the number of tokens that can be produced per unit time
- **spatial parallelism** is like parallelism in pprog
- **temporal parallelism** is like concurrency in pprog (pipelining goes here)

### Chapter 4 - Hardware Description Languages
- Skipped

## P

### Chapter 3 - Continuation

#### Memory
- **Address space** is the total number of uniquely identifiable memory locations 
- **Addressability** is the number of bits stored in each location