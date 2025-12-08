---
aliases:
  - DSA
  - dsa
---

2025-12-08 21:17

Tags: #computers #acceleration 

# Domain-Specific Architectures
The point of using DSA is to make specific operations like matrix multiplication faster on specialized chips. With these kinds of chips we reduce the problem down to the most optimized chip for this task. Making the speed improvements good, but the chip will be useless in other domains. 

## Five DSA principles
1. Use dedicated memories to minimize the distance over which data are moved
2. Invest the resources saved from dropping advanced microarchitectural
optimizations into more arithmetic units or bigger memories
3. Use the easiest form of parallelism that matches the domain
4. Reduce data size and type to the simplest needed for the domain
5. Use a domain-specific programming language to port code to the DSA


## Further reading
- [[Graphical processing unit]]
- [[Central Processing Unit]]
- [[Heterogeneous System Architecture]]
