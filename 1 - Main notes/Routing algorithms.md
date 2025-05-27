---
aliases:
  - routing al
---

2025-05-27 10:45

Status: #in-writing 
Tags: #communication #networklayer #controlplane #algorithms 

# Routing algorithms
The main goal with routing algorithms is to determine the best path from one router to another router on a network. This is done by implementing and applying the algorithms on the network. This can be done in two different ways, either every router will take part in computing the forwarding table in a distributed manner, or the computation will be done on a separate server. The later approach is called a [[Software defined network|software defined network]] (SDN). When computing the path, there might be different qualities to the different links in the network, for example links can have variable speed and congestion. The abstraction used for networks is fundamentally [[Graph theory|graph theory]], and this means that we apply graph algorithms to the networks. 
## Types of routing algorithms
### Link state routing
When we talk about an algorithm being a "link state" algorithm it means that all the routers in the network needs to know everything about the network. An example of a like state algorithm is the Dijkstra's algorithm, which is widely used on the internet. 
#### [[Dijkstra's algorithm]]
Dijkstra's algorithm works by finding the shortest path from one node to all the other nodes in the graph. Read more about Dijkstra's algorithm [[Dijkstra's algorithm|here]]. In computer networks the algorithm will be used with a cost for each vertices and this can either be the same in both directions of different based on direction. In networks the cost will be based on some value chosen by the network administrator (e. g. distance, congestion etc.).
The computational complexity we get with using [[Dijkstra's algorithm]] is $O(n^2)$ for n nodes. And for the message complexity we also get $O(n^2)$. For the computational complexity will it be possible to reach a better complexity with different algorithms and the best is $O(n\log{n})$.

A real world implementation of the algorithm is the [[Open Shortest Path First]] algorithm, and this protocol is widely used on the internet. 
### Distance vector routing
The other type of routing algorithm is "distance vector" algorithms, and these are more distributed and work in an iterative manner. For each iteration they will exchange information with neighbors and improve the routing. With this they get a distance vector representing different routing paths. 
#### [[Bellman-Ford algorithm]]
The Bellman-Ford algorithm is a distributed algorithm based on the [[Bellman-Ford algorithm#Bellman-Ford equation|Bellman-Ford equation]] and uses a recursive approach and therefore it is [[Dynamic programming|dynamic programming]]. The Bellman-Ford equation is really simple, and that is part of what makes it smart:
$$
D_x(y)=\min\nolimits_v({c_{x,v} + D_v(y)})
$$
The algorithm will propagate over a network of routers, where every router only needs to know what is called the *distance vector* for that router. The distance vector is like a table containing values for the distance between that router and all other routers. Each time the Bellman-Ford algorithm iterates it will update the distance vectors and try to optimize for the minimum cost. In practice this makes it a very effective algorithm for determining the routing on a network, because not every router needs to know the exact shortest path from itself to every other node. 
##### The flow of Bellman-Ford
The algorithm has 3 simple steps:
1. Wait for neighbor to change its distance vector
2. Recompute its own distance vector
3. If distance vector has changed notify neighbors and repeat

With only these three steps all the nodes in the network update all the distance vectors and create the best forwarding tables. 
##### Issues with Bellman-Ford routing
There are some downsides to using this algorithm:
- Count-to-infinity problem, where one change in the network can cause all the routers to start changing the distance vectors
- It is also possible to have routing loops
- Nodes that falsely advertise a short path to one node can end up as black holes
## Routing in the real world
With implementing these algorithms in the real world comes a whole lot of problems, and the first and hardest one is to scale the entire network. For networks with the size of the internet it will be way possible to compute algorithms with the complexity of $O(n^2)$. And even with the smartness of the Bellman-Ford algorithm all the bandwidth will be used up by the updates to the distance vectors. Therefore techniques to limit the computation for each vector will have to be used. Another argument for splitting up all the networks is that each administrator will want to control the routing in its own network, and this can only be achieved by splitting the internet. 
### Autonomous systems
The approach used for scaling can be described by 