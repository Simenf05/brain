---
aliases:
  - routing al
---

2025-05-27 10:45

Status: #in-writing 
Tags: #communication #networklayer #controlplane #algorithms 

# Routing algorithms
The main goal with routing algorithms is to determine the best path from one router to another router on a network. This is done by implementing and applying the algorithms on the network. This can be done in two different ways, either every router will take part in computing the forwarding table in a distributed manner, or the computation will be done on a separate server. The later approach is called a [[Software defined network|software defined network]] (SDN). When computing the path, there might be different qualities to the different links in the network, for example links can have variable speed and congestion. The abstraction used for networks is fundamentally [[Graph theory|graph theory]], and this means that we apply graph algorithms to the networks. 
## Link state routing
When we talk about an algorithm being a "link state" algorithm it means that all the routers in the network needs to know everything about the network. An example of a like state algorithm is the Dijkstra's algorithm, which is widely used on the internet. 
### [[Dijkstra's algorithm]]
Dijkstra's algorithm works by finding the shortest path from one node to all the other nodes in the graph. Read more about Dijkstra's algorithm [[Dijkstra's algorithm|here]]. In computer networks the algorithm will be used with a cost for each vertices and this can either be the same in both directions of different based on direction. In networks the cost will be based on some value chosen by the network administrator (e. g. distance, congestion etc.).
The computational complexity we get with using [[Dijkstra's algorithm]] is $O(n^2)$ for n nodes. And for the message complexity we also get $O(n^2)$. For the computational complexity will it be possible to reach a better complexity with different algorithms and the best is $O(n\log{n})$.
## Distance vector routing
The other type of routing algorithm is "distance vector" algorithms, and these are more distributed and work in an iterative manner. For each iteration they will exchange information with neighbors and improve the routing. With this they get a distance vector representing different routing paths. 
### Bellman-Ford algorithm





