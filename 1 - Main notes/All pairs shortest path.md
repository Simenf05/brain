---
aliases:
  - APSP
  - apsp
---

2025-12-12 12:49

Tags: #algorithms #dsa #shortestpath

# All pairs shortest path

The all pairs shortest path problem is a problem in which you search a graph for the shortest path from each node $u\in{V}$ to every node $v\in{V}$. The length of a path is determined by the weight of each edge in that path. This problem is similar to the [[Single source shortest path]] problem, and we could indeed solve the problem by using [[Dijkstra's algorithm]] or [[Bellman-Ford algorithm]] on every node, and then find all the shortest paths. But this is wasteful, and there is much faster algorithms designed to solve this problem. In this note i take a look at these algorithms:
- [[#Slow-APSP]]
- [[#Faster-APSP]]
- [[#Floyd-Warshall]]

Both the slow and the fast version of the simple APSP algorithm uses the concept of limiting the amount of edges we use in each iteration. [[#Floyd-Warshall]] works in a different way by limiting the amount of nodes we can use in each iteration. 
## Slow-APSP
The Slow-APSP algorithm is based on the [[Triangle inequality]] and uses it to determine the shortest path between each of the vertices. It uses this recursive formula:
$$l_{ij}^{(0)} =
\begin{cases*}
0 & if $i = j$,\\
\infty & if $i \neq j$.
\end{cases*}
$$
This makes a matrix where $r=0$ and therefore the paths cannot use any edges. In this matrix every node will have a distance of 0 to itself, and $\infty$ to every other vertex.
We can then define the distance matrix recursively by using the [[Triangle inequality]]. We get:
$$l_{ij}^{(r)} =
min{ \{ l_{ij}^{(r-1)}, min{ \{ l_{ik}^{(r-1)} + w_{kj} : 1 \le k \le n \} } \} }
$$
Which can be shortened to 

$$l_{ij}^{(r)} =
min{ \{ l_{ik}^{(r-1)} + w_{kj} : 1 \le k \le n \} }
$$

We use [[Dynamic programming]] in order to recursively define the matrix where $r=|V-1|$ and we are allowed to use all the nodes once, which makes for a simple path. This matrix is $L^{(r-1)}$, consisting of $l_{ij}^{(n-1)}$, ($n=|V|$)[^1].

The pseudocode produces $L^{(r)}$ with the weight matrix $W$ and $L^{(r-1)}$:
![[Pasted image 20251212141204.png]]
With each of the for loops iterating n times, we can trivially conclude that this algorithm has $\Theta({n^3})$ as its running time. 
In a way the extention works like [[Matrix multiplication]]. We just use a different kind, this becomes explicit when we use this syntax:
$$L^{(1)}=$$ 
With this subroutine we can define the actual algorithm:
![[Pasted image 20251212144015.png]]

## Faster-APSP
## Floyd-Warshall


## Further reading
- [[Asymptotic notation]]
- [[Algoritmiske problemtyper]]
- [[Single source shortest path]]
- [[Dijkstra's algorithm]]
- [[Bellman-Ford algorithm]]

## Footnote
[^1]: It is normal to use the variable $n$ as the amount of vertices, and also the dimensions of the matrix.