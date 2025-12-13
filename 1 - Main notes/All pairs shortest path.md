---
aliases:
  - APSP
  - apsp
---

2025-12-12 12:49

Tags: #algorithms #dsa #shortestpath #graph

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

$$
L^{(1)}=L^{(0)}\cdot{W}=W^1
$$
$$
L^{(2)}=L^{(1)}\cdot{W}=W^2
$$
$$
L^{(3)}=L^{(2)}\cdot{W}=W^3
$$ 

With this subroutine we can define the actual algorithm:
![[Pasted image 20251212144015.png]]

We get $n-1$ because a shortest simple path can at most contain $|V|-1$ vertices. 
We get a running time of $\Theta{(n^4)}$ for the entire algorithm. But this can be improved on. 
## Faster-APSP
The Faster-APSP works just the same way as [[#Slow-APSP]] but it uses the a property of matrix multiplication. Since each time you multiply $W$ with $L^{(r)}$ you get $L^{(r+1)}$, by the laws of matrix multiplication, you can $L^{(2r)} = L^{(r)} \cdot L^{(r)}$
$$
L^{(1)}={W}
$$
$$
L^{(2)}=L^{(1)}\cdot L^{(1)}=W^2
$$
$$
L^{(4)}=L^{(2)}\cdot L^{(2)}=W^4
$$
$$
L^{(8)}=L^{(4)}\cdot L^{(4)}=W^8
$$ 

With this knowledge we can speed up the entire process. This is because we only need to compute $\lceil {lg(n - 1)} \rceil$ matrices to reach the desired $L^{(n-1)}$. We do this in an iterative way. 
![[Pasted image 20251212162102.png]]
## Floyd-Warshall
This next algorithm uses similar principles as the slow and faster APSP, but instead of limiting the amount of edges, we limit what vertices to use. This way we check if there is a faster way that uses the current iteration's vertex. We use this formula where $k$ is the current iteration's vertex:
$$
d_{ij}^{(k)} = 
\begin{cases*}
w_{ij} & if k = 0,\\
min{ \{ d_{ij}^{k(-1)}, d_{ik}^{(k-1)} + d_{kj}^{(k-1)} \} } & if $k \ge 1$.
\end{cases*}
$$
With this formula we get the matrix $D^{k}=(d_{ij}^{k})$, which when $k=n$ we get the shortest path from each node to every other node, including itself. 
To implement this we use a bottom up [[Dynamic programming]] strategy where we first iterate over the $k$ nodes we are allowed to use. Then we calculate $d_{ij}^{(k)}$ for each of the $(i, j) \in V^2$. 
We get a running time of $\Theta(n^3)$, because we have three for loops. 
![[Pasted image 20251213112703.png]]

## Further reading
- [[Graph theory]]
- [[Asymptotic notation]]
- [[Algoritmiske problemtyper]]
- [[Single source shortest path]]
- [[Dijkstra's algorithm]]
- [[Bellman-Ford algorithm]]

## Footnote
[^1]: It is normal to use the variable $n$ as the amount of vertices, and also the dimensions of the matrix.