# Advanced Heuristic
#### Kahbod Aeini, Mohammadreza Daviran and Sepehr Kianian

First we review some basic definitions

* Distance is a numerical measurement of how far apart objects or points are.
* [Euclidean Distance](https://en.wikipedia.org/wiki/Euclidean_distance) calculates the distance between two real-valued vectors.
* Manhattan Distance is sum of the absolute differences of their Cartesian coordinates.
* ![distance](distance.png)
* Heuristic guidance means how far is the goal state from a given state approximately.

***Admissiblity of a heuristic function means value of the function is always a Lower Bound of the remaining cost.***

So an **Admissible Heuristic** is a *non-negative* function h of nodes, where **h(n)** is *never greater than the actual cost of the shortest path from node n to a goal.* thus it means that the cost to reach the goal is never overestimated.

Effect of **Admissibility** on a Heuristic is shown in the below schema:
![admissible](admissible.png)

Now we define **f(n)** function as **f(n) = h(n) + g(n)** where g(n) is sum of costs from root to n node.

***Monotonicity or Consistency is that the heuristic function holds in triangle inequality.*** Namely **f(n) is never Decreasing.**
![consistency](consistency.png)

Effect of **Monotonicity** on a Heuristic is shown in the below schema:
![monotonicity](monotonic.png)

We will prove that **Consistency** implies **Admissibility** whereas the opposite is not necessarily true.
![proof](proof.png)


Now we want to show an **inconsistent, admissible example!**
So consider this figure:

![example](example.png)

If our heuristic is admissible, we have that **h(n) <= h*(n)** for every node n where **h*** is the real cost to the goal. So we deduct that **h(A) <= 4**, **h(C) <= 3** and **h(G) <= 0**.

If we want our heuristic to be *Consistent* we should have **h(G) = 0** and **h(n) <= cost(n, c) + h(c)** so in our case we have **h(A) <= 1 + h(C)** and **h(C) <= 3 + h(G) = 3**

Because of the *Admissibility* **h(C) should be less than 3**, but if **h(A) > 1 + h(C)** then our heuristic is *Inconsistent!*. Hence if we assume that **h(C) = 1**, **h(G) = 0** and **h(A) = 4** our heuristic is *Admissible but Inconsistent!*
