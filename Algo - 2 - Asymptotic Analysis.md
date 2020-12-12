
# 2 - Asymptotic Analysis

## Motivation

- **Importance**: vocabulary for the design and analysis of algorithms (e.g. "big-oh" notation)

- **Sweet spot** for high-level reasoning about algorithms
	- coarse enough to suppress architecture / language / compiler-dependent details
	- sharp enough to make useful comparsions between different algorithms, especially on large inputs, e.g. sorting or integer multiplication)

 
- **High-level idea**: suppress constant factors and lower-order terms
	- constant factors - too system-dependent
	- lower-order terms - irrelevant for large inputs

- **Example**: equate $(6n\log_2{n}+6n)$ with just $(n\log{n})$

- **Terminology**: running time is $O(n\log{n})$


## Big-Oh Notation

Let $T(n)$ be a function on $n=1,2,3,...$

What is $T(n)=O(f(n))$?

**English definition**: If eventually (for all sufficiently large $n$), $T(n)$ is bounded above by a constant multiple of $f(n)$.


**Mathematical definition**: $T(n) = O(f(n))$ if and only if there exists constants $c, n_0 > 0$ such that $$T(n) \leq c \cdot f(n), \forall n \geq n_0$$.


### Basic Examples #1

**Claim**: if $T(n) = a_k n^k + \cdots +a_1 n + a_0$ then $T(n) = O(n^k)$.
**Proof**: Choose $n_0 = 1$ and $c = |a_k| +|a_{k-1}| + \cdots + |a_1| + |a_0|$. Need to show that $\forall n \geq 1, T(n) \leq c \cdot n^k$.

We have, for every $n \geq 1$,

$$
\begin{aligned}
T(n) &\leq |a_k| n^k +|a_{k-1}| n^{k-1} + \cdots + |a_1| n + |a_0| \\
&\leq |a_k| n^k +|a_{k-1}| n^{k} + \cdots + |a_1| n^{k} + |a_0| n^{k} \\
&\leq c \cdot n^k
\end{aligned}
$$


### Basic Examples #2

**Claim**: for every $k \geq 1$, $n^k$ is not $O(n^{k-1})$.
**Proof**: by contradiction. Suppose $n^k = O(n^{k-1})$. Then there exists constants $c, n_0 > 0$ such that $$n^k \leq c \cdot n^{k-1}, \forall n \geq n_0$$. But then, $$n\leq c, \forall n \geq n_0$$, which is clearly False.


## Big Omega and Theta

### Omega Notation

**Definition** : $T(n) = \Omega(f(n))$ if and only if $\exist$ constants $c, n_0 > 0$ such that $$T(n) \geq c \cdot f(n)$$, for all $n \geq n_0$.


### Theta Notation


**Definition**: $T(n) = \Theta(f(n))$ if and only if $T(n) = O(f(n))$ and $T(n) = \Omega(O(n))$.

**Equivalent**: $\exist$ constants $c_1, c_2, n_0 > 0$ such that $$c_1f(n) \leq T(n) \leq c_2f(n)$$, for all $n \geq n_0$.


### Little-Oh Notation

Definition: $T(n) = o(f(n))$ if and only if for all constant $c > 0$, $\exist$ a constant $n_0$ such that $$T(n) \leq c \cdot f(n), \forall n \geq n_0$$.

## Additional Examples [Review - Optional] 

### Example #1

**Claim**: $2^{n+10}=O(2^n)$.
**Proof**: need to pick constants $c, n_0 > 0$ such that $$2^{n+10} \leq c \cdot 2^n, \forall n \geq n_0$$.
**Note**: $2^{n+10}=2^{10} \cdot 2^n = (1024) \cdot 2^n$
**So**: if we choose $c=1024, n_0=1$, then the claim holds.





# References

- Algorithm Specialization - Coursera
[Tim Roughgarden](https://www.coursera.org/instructor/~768), Professor of Computer Science
Stanford University
URL: https://www.coursera.org/specializations/algorithms

---

> Written with [StackEdit](https://stackedit.io/).
