# Advanced Heuristic
#### Kahbod Aeini, Mohammadreza Daviran and Sepehr Kianian

First we review some basic definitions

* Distance is a numerical measurement of how far apart objects or points are.
* [Euclidean Distance](https://en.wikipedia.org/wiki/Euclidean_distance) calculates the distance between two real-valued vectors.
* Manhattan Distance is sum of the absolute differences of their Cartesian coordinates.
* ![distance](https://drive.google.com/file/d/1T0z7-N2TerLC1C463f1yo8bF2uxnRz1E/view?usp=sharing)
* Heuristic guidance means how far is the goal state from a given state approximately.

***Admissiblity of a heuristic function means value of the function is always a Lower Bound of the remaining cost.***

So an **Admissible Heuristic** is a *non-negative* function h of nodes, where **h(n)** is *never greater than the actual cost of the shortest path from node n to a goal.* thus it means that the cost to reach the goal is never overestimated.

Effect of **Admissibility** on a Heuristic is shown in the below schema:
![admissible](https://drive.google.com/file/d/1QLsEEby00Ys0YOXIZsTVH7_TaiCtWHuw/view?usp=sharing)

Now we define **f(n)** function as **f(n) = h(n) + g(n)** where g(n) is sum of costs from root to n node.

***Monotonicity or Consistency is that the heuristic function holds in triangle inequality.*** Namely **f(n) is never Decreasing.**
![consistency](https://drive.google.com/file/d/13xMfk7Hfg9rheQMu4SIhx-ja2jaGcA4I/view?usp=sharing)

Effect of **Monotonicity** on a Heuristic is shown in the below schema:
![monotonicity](https://drive.google.com/file/d/1KhQnlO3tQLmNYxgJYLijLo3vw_hLGF5o/view?usp=sharing)

