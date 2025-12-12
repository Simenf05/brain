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
## Faster-APSP
## Floyd-Warshall


## Further reading
- [[Asymptotic notation]]
- [[Algoritmiske problemtyper]]
- [[Single source shortest path]]
- [[Dijkstra's algorithm]]
- [[Bellman-Ford algorithm]]