# Advanced Heuristic
#### Kahbod Aeini, Mohammadreza Daviran and Sepehr Kianian

First we review some basic definitions

* Distance is a numerical measurement of how far apart objects or points are.
* [Euclidean Distance](https://en.wikipedia.org/wiki/Euclidean_distance) calculates the distance between two real-valued vectors.
* Manhattan Distance is sum of the absolute differences of their Cartesian coordinates.
<img src="distance.png" alt="distance" width="400" height="300"/>
* Heuristic guidance means how far is the goal state from a given state approximately.

***Admissiblity of a heuristic function means value of the function is always a Lower Bound of the remaining cost.***

So an **Admissible Heuristic** is a *non-negative* function h of nodes, where **h(n)** is *never greater than the actual cost of the shortest path from node n to a goal.* thus it means that the cost to reach the goal is never overestimated.

Effect of **Admissibility** on a Heuristic is shown in the below schema:
<img src="admissible.png" alt="admissible" width="600" height="300"/>

Now we define **f(n)** function as **f(n) = h(n) + g(n)** where g(n) is sum of costs from root to n node.

***Monotonicity or Consistency is that the heuristic function holds in triangle inequality.*** Namely **f(n) is never Decreasing.**
<img src="consistency.png" alt="consistency" width="600" height="300"/>

Effect of **Monotonicity** on a Heuristic is shown in the below schema:
<img src="monotonic.png" alt="monotonic" width="600" height="300"/>

We will prove that **Consistency** implies **Admissibility** whereas the opposite is not necessarily true.
<img src="proof.png" alt="proof" width="800" height="300"/>


Now we want to show an **inconsistent, admissible example!**
So consider this figure:

![example](example.png)

If our heuristic is admissible, we have that **h(n) <= h*(n)** for every node n where **h*** is the real cost to the goal. So we deduct that **h(A) <= 4**, **h(C) <= 3** and **h(G) <= 0**.

If we want our heuristic to be *Consistent* we should have **h(G) = 0** and **h(n) <= cost(n, c) + h(c)** so in our case we have **h(A) <= 1 + h(C)** and **h(C) <= 3 + h(G) = 3**

Because of the *Admissibility* **h(C) should be less than 3**, but if **h(A) > 1 + h(C)** then our heuristic is *Inconsistent!*. Hence if we assume that **h(C) = 1**, **h(G) = 0** and **h(A) = 4** our heuristic is *Admissible but Inconsistent!*


We also can make a non-monotonic heuristic, monotonic with some changes!
For this we only need to define a new and more appropriate heuristic like the below schema.

<img src="Screen Shot 1400-08-05 at 00.31.06.png" alt="new heuristic" width="500" height="150"/>

