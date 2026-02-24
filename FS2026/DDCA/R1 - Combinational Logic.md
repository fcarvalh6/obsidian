#FS2026 #DDCA 

Assigned reading:
- Chapters 1, 2 of Harris and Harris (abbrev. H)
- Chapters 1, 2, 3 of Patt and Patel (abbrev. P)

## H

### Chapter 1 - From Zero to One

#### Number Systems
- Binary numbers (base 2) have two possible values for each digit.
- Hexadecimal numbers (base 16) are defined analogously. One can convert any hex number into a binary one by replacing each hex symbol into a base 2 number with four bits. 
- Binary addition is performed like decimal addition, with "carries". If there is a carry out of the most significant column, there is an **overflow**.

#### Signed Binary Numbers
- Sign/Magnitude numbers have one sign digit (the most significant digit).
	- Binary addition does not work with this implementation
	- There are two values for zero ($+0,-0$)
- Two's Complement numbers have one sign digit (the mode significant digit). A negative number is represented by taking the positive value, inverting all bits and adding 1 to the least significant bit position.
	- Binary addition works properly.
	- There is only one value for zero.
- Overflow occurs if the two numbers being added have the same sign and the result has the opposite sign bit.

#### Logic Gates
- Buffer, NOT, AND, OR, XOR, NAND, NOR, XNOR

#### Logic Levels
- Voltage is continuous. It is mapped to a discrete value by using logic values. 
- Logic values are intervals that determine if a value is TRUE or FALSE
- Output values:
	- $V_{OH}$ is the minimum voltage guaranteed when the output is HIGH. 
	- $V_{OL}$ is the maximum voltage guaranteed when the output is LOW.
- This defines two output intervals, $\text{LOW}=[0,V_{OL}]$ and $\text{HIGH}=[V_{OH},V_{DD}]$.
- Input values:
	- $V_{IH}$ is the minimum voltage recognized as HIGH
	- $V_{IL}$ is the maximum voltage recognized as LOW
- This defines two input intervals, $\text{LOW}=[0,V_{IL}]$ and $\text{HIGH}=[V_{IH},V_{DD}]$.
- For a reliable operation, we must ensure $V_{OH}>V_{IH}$ and $V_{IL}>V_{OL}$, these are called noise margins. 

#### Physics of Transistors
- Silicon forms a crystalline lattice (cubic crystal). It is by itself a poor conductor since all electrons are tied up in covalent bonds. 
- Small impurities are added to make it more conductive, these are called **dopant atoms**.
- Depending on the dopant atoms added, the transistor will either be **n-type** or **p-type**. 
- If the dopant atom is a group V atom, its electron will be able to move freely, so negative charges propagate, n for negative, n-type. 
- If the dopant atom is a group III atom, electrons will be able to move towards it to "fill the hole", so the absence of negative charges propagate, p for positive, p-type.
- More specifically, we will talk about MOSFETs
	- nMOS transistors pass $0$'s well and $1$'s poorly, they turn ON when the gate is $1$
	- pMOS transistors do the opposite

### Chapter 2 - Combinational Logic Design

#### Intro
- A **circuit** is a network that processes discrete-valued variables. Circuits have:
	- input terminals
	- output terminals
	- a functional specification (how the circuit behaves logically)
	- a timing specification (how quickly the circuit responds)
- A **combinational** circuit has no memory, a **sequential** circuit has memory
- There are often many implementations for the same logical function, and one must pick the one that better suits your constraints (area, speed, power, design time)

#### Boolean Equations
- A *minterm* is a product involving all inputs
- A *maxterm* is a sum involving all inputs
- By taking a truth table, one can find the **sum-of-products canonical form** of this function by taking every line that outputs TRUE and writing a sum (OR) between all the *minterms* "in" these lines. 
- The **product-of-sums** form is found analogously by taking lines that output FALSE and writing a product between all *maxterms*.
- These equations can be simplified by using **boolean algebra**. Simplifying them usually means using less gates in practice, which can mean less material costs, etc.

#### Boolean Algebra
- There are axioms and theorems of boolean algebra (see page 61) which define what operations can be performed without impacting the logical behavior of the function. 
- To simplify an equation in sum-of-products form, the main principle is combining terms using $PA+P\bar{A}=P$, this is similar to resolution calculi in discrete mathematics. 
- For functions with up to 4 input variables, one can use **Karnaugh maps** to assist in the simplification process (see page 75)

#### X and Z
- $X$ represents an unknown or illegal value and is usually obtained if a node is being driven to both 0 and 1 at the same time. 
- $X$ values are also sometimes used by circuit simulators to represent an uninitialized value. 
- $X$ values can be used (when optimal) to create simplification groups in Karnaugh maps. 
- $Z$ represents a node is neither HIGH or LOW
- $Z$ is also called the **floating value**. A floating node can be either $0$ or $1$ or some voltage in between. 

#### Combinational Building Blocks
- These building blocks are groups of gates and represent a higher level of abstraction. Remember that gates are themselves abstractions of groups of transistors. 
- **Multiplexers** have $n$ inputs, $1$ output and $\log_{2}n$ "keys" which allow you to choose any input. They can be used as **lookup tables** to perform logic functions. 
- **Decoders** have $n$ inputs and $2^{n}$ outputs. The inputs choose which output is set to HIGH. They can be used with OR gates to build logic functions. 

## P

Only what wasn't covered by H will be mentioned here
### Chapter 1 - Welcome Aboard
- A computer may appear to be a very complex organism, but it is a very large, systematically interconnected collection of very simple parts. 
- All information must be encoded as a sequence of zeros and ones, and we will operate on these encoded sequences. 
- Two important ideas:
	- All computers can do exactly the same things (some do it faster).
	- We must transform our problems from natural language to "electron language"

### Chapter 2 - Bits, Data Types and Operations

#### Addition and Subtraction
- To subtract (in 2's complement), just invert one and sum. 

#### Floating Point Numbers
- One floating point data type is *float*, it consists of 32 bits, where:
	- 1 bit represents the sign
	- 8 bits represent the range (exponent field in scientific notation)
	- 23 bits represent the precision (fraction field in scientific notation)

#### ASCII codes
- Every key on the keyboard is represented by its unique ASCII code

### Chapter 3 - Digital Logic Structures

#### One-Bit Adder
- Keep track of what "stays" and the "carry".
- Diagram in page 70. 
- Chaining $n$ one-bit adders gives us a $n$-bit adder

#### Programmable Logic Arrays (PLA)
- AND array followed by OR array
- As many AND gates as input combinations in the truth table (rows)
- As many OR gates as functions to implement (output columns)

#### Logical Completeness
- $\{ \text{AND}, \text{OR}, \text{NOT} \}$ is **logically complete** since we can implement any logical function using only these three gates. 
- $\{ \text{NAND} \}$ is also logically complete.

The chapter continues with storage elements, but the notes stop here since these are related to sequential logic structures. The end of Chapter 3 will be present in R2. 