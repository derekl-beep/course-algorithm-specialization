# 1 - Introcution


## Why study algorithms?

- Important for all other branches of computer science
	- routing communcation networks ~ classical shortest path algorithms
	- the effectiveness of public key cryptography relies on number-theoretic algorithms
	- computer graphics needs the computational primitives supplied by geometric algorithms
	- databases indices rely on balanced search tree data structures
	- computational biology uses dynamic programming algorithms to measure genome simiarity

- Plays a key role in modern technological innovation
	- search engines use algorithms to efficiently compute the relevance of various webpages to its given search query
	- Page rank algorithm

- Provides novel "lens" on processes outside of computer science and technology
	- study of quantum computation provide a new viewpoint for quantum mechanics
	- price fluctuations in economic markets  can be viewd as an algorithmic process
	- evolution can be thought as an effective search algorithm

- Challenging and fun

## Merge Sort

- John Von Neumann, 1945
- improves over Selection, Insertion, Bubble sorts
- recursive
- divide-and-conquer 

**Input**: array of n numbers, unsorted.
**Output**: same numbers, sorted in increasing order.
**Assume**: distinct numbers

```c
// Insert merge sort picture
```

### Pseudocode

#### Merge steps

C = output array [Lenght = n]
A = 1st sorted array [n/2]
B = 2nd sorted array [n/2]

```
for k = 1 to n
	if A(i) < B(j)
		C(k) = A(i)
		i++
	else [B(j) < A(i)]
		C(k) = B(j)
		j++
end
(ignores end cases)
```

*Python:*
```python
for k in range(n):
	if A[i] < B[j]:
		C[k] = A[i]
		i += 1
	else:
		C[k] = B[j]
		j += 1
```

#### Running Time

running time of merge on array of m number is $\leq 4m + 2 \leq 6m$, given $m \geq 1$

**Claim**: Merge Sort requires $\leq 6n \log_2 n + 6n$ operations to sort $n$ numbers.

#### Analysis

Recursion tree method

```c
// Insert pic
```

Numbe of levels: $\log_2{n} + 1$

At each level $j=0,1,2,...,\log_2{n}$, there are $2^j$ subproblems, each of size $\frac{n}{2^j}$.

Total number of operations at level $j = 2^j \times 6(\frac{n}{2^j})=6n$, which is independent of $j$.

Total number of operations $= 6n(\log_2{n} + 1) = 6n \log_2 n + 6n$.


## Guiding Principles for Analysis of Algorithms

### Guilding Principle #1

- **Worst-case analysis**: our running time bound holds for every input of length $n$, i.e. upper bounds
	- particularly appropreciate for "general-purose" rountines
	- usually easier to analyze
- **Average-case analysis**: average running time based on input distribution assumptions, which requires domain knowledge

### Guilding Principle #2

### Guilding Principle #3

- **Asymptotic analysis**: focus on running time for ***large*** input size $n$
- Example: $6n\log_2{n}+6n$ for Merge Sort is "better than" $\frac{n^2}{2}$ for Insertion Sort if $n$ is large.
- Justification: only big problems are interesting!

### What is a "Fast" Algorithm?

An algorithm whose worst-case running time grows slowly with input size.



# References

- Algorithm Specialization - Coursera
[Tim Roughgarden](https://www.coursera.org/instructor/~768), Professor of Computer Science
Stanford University
URL: https://www.coursera.org/specializations/algorithms


> Written with [StackEdit](https://stackedit.io/).
