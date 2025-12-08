---
aliases:
  - parallelism
---

2025-12-08 18:57

Tags: #parallelism #computers 

# Parallelism
Parallelism refers to the execution of multiple tasks at the same time. A normal way of categorizing this is to look at how many streams of data and [[instructions]] one processor has. If there is one at most one instruction at a time, and only one data-stream, then the execution would be classified as *single instruction-streams single data-streams*. This is the most basic model that is used by a uni-processor. When you look at the other side of the equation you get the *multiple instruction-streams multiple data-streams*, and this is the normal multiprocessor in used widely today.
## SI/MI and SD/MD

|     | SD                  | MD                        |
| --- | ------------------- | ------------------------- |
| SI  | SISD: uni-processor | SIMD: GPU or vector based |
| MI  | MISD: n/a           | MIMD: multiprocessor      |
## SIMD
The most important of and most related to parallelism is the *SIMD* processors. They are normally found in [[Graphical processing unit|graphical processing units]], and are a more specialized compute then normal [[Central Processing Unit|CPUs]]. The motivation for *SIMD* is to be able to do one instruction on many data-streams at the same time, for example it might be able to add 64 numbers by sending the 64 numbers to 64 [[Arithmetic Logic Unit|ALUs]] and compute all the sums in one clock cycle. The principle is to allow for great use of more hardware in order to accelerate specific tasks on large amounts of data. 
### Skipping instruction fetch
One of the benefits of allowing SIMD is that it can fetch the instruction once, and use the same instruction on many different data-streams. That way all the memory overhead you normally would get from fetching instructions can be skipped. 

### Vector instructions
There also exists vector instructions, that are instruction that work on entire vectors of data at once. They work by  [[Pipelined computer architecture|pipe-lining]] the operations and computing multiple at the same time. Thereby increasing the performance. They are great with much data-level parallelism. A vector implementation of SIMD gets truly efficient when you introduce multiple lanes in the pipelines. T
In the picture below we can see that the one on the right has four adders and this corresponds to having four lanes. Therefore it compute the sums from the vector four at a time. The one one the left can only compute one sum each clock cycle. 
![[Pasted image 20251208194331.png]]

## Further reading at
- [[Parallelism and memory]]
- [[Graphical processing unit]]
- [[Hardware multithreading]]
