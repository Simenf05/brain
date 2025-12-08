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

## Simultaneous multithreading



