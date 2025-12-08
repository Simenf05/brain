---
aliases:
  - GPU
  - gpu
---

2025-12-08 20:40

Tags: #computers #acceleration

# Graphical processing unit
The main motivation for using graphical processing units is to enable acceleration on graphical computing tasks. This was developed by and for games, and the gaming industry was the biggest incentive for companies to make graphical acceleration faster. 

## What makes GPUs special?
GPUs:
- supplement [[Central Processing Unit|CPUs]] and can focus everything into making graphics faster
- don't use multilevel caches, but rather uses many threads that can work independently while waiting for the memory fetch
- have less [[Memory hierarchy#DRAM|DRAM]] memory
- is more highly [[Hardware multithreading|multithreaded]]

## MIMD of SIMD
The gpu is in a way a MIMD of [[Parallelism#SIMD|SIMDs]], meaning that they are highly effective at doing SIMD tasks. 
![[Pasted image 20251208211604.png]]



## Further reading
- [[Central Processing Unit]]
- [[Domain-Specific Architectures]]
