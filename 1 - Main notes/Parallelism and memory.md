---
aliases:
---

2025-12-08 14:47

Tags: #computers #memory #parallelism

# [[Parallelism]] and [[Memory hierarchy|memory]]
When you have multiple cores with their own caches, it becomes a big issue to keep the memory correct. This has two main aspects, *coherence* and *consistency*.
## Coherence
The problem of coherence is for each of the processors in a multi-core [[Central Processing Unit|CPU]] to see the same latest written value, and for all the other processors to read new values written in the same order. This becomes hard when you factor in that each core has its own cache system, and to keep the core fast we need good hit-rate on the cache.  
### How to maintain coherence
We use two techniques to keep the caches coherent, *migration* and *replication*. Migration works by moving the value to the specified cache, and replication means making a copy. 
## Consistency
Consistency is about when a written value is returned by a new read. 
