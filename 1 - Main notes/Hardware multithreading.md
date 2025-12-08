---
aliases:
  - multithreading
---

2025-12-08 19:50

Tags: #computers #parallelism #threading

# Hardware multithreading
While [[Parallelism|parallelism]] can be done by keeping multiple [[Central Processing Unit|processors]] busy, concurrency can also be implemented by letting multiple *threads* use the same processor. This is done by keeping different copies of the PC and register files for each of the threads. For threads to be effective we need to be able to switch thread fast, and thereby have it be way faster than process switching. 
## Fine-grained multithreading
Fine-grained multithreading works by switching in a [[Router#Round robin (RR)|round robin]] fashion, meaning it will change thread very often. For this reason it is often a requirement for fine-grained multithreading to be able to switch thread on every clock cycle. 
## Course-grained multithreading
An alternative to using fine-grained multithreading is to use course-grained multithreading, where the concept is to only switch thread on expensive stalls, like expensive cache misses. 
The issue with this strategy is that the [[Pipelined computer architecture|pipeline]] startup time becomes a big problem. For every thread that stalls, the entire pipeline has to be emptied, and the next thread has to fill up the thread before work starts again. 
## Simultaneous multithreading
SMT combines thread level [[Parallelism|parallelism]] and [[Instructions|instruction]] level parallelism to make the most use out of the processor at any given time. It works by slotting each part of instructions into any part of the instruction level parallelism, and thereby splitting up each instruction and using doing multiple at once. 
![[Pasted image 20251208203224.png]]


## Further reading
- [[Parallelism]]
