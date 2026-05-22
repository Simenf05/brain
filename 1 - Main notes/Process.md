---
aliases:
  - process
---
2025-02-09 12:12

Tags: #it #os #linux #communication 

# Process 
A process is defined as an isolated running program. Where a program is stored statically on the disk, and running the program is loading it into memory and running the instructions on a [[Central Processing Unit|CPU]]. The process also has state associated with it, and this state is usually isolated from other processes to provide a level of security. One of the many tasks of the [[Operating System|operating system]] is to manage all the current processes, and share the physical resources of the computer between all the running processes. 
## pid
The pid is the unique identifier for each process on a [[Unix]]-like operating system. It is a incremental number generated 
### pid 1
T

## How to make a process
On [[Unix]]-like systems, making a process is done through the [[fork]] system call. This splits the currently running process into two of itself. To the process fork acts like a black box (like all system calls), and when it returns the process either is the child or the parent. The operating system gives the child a return code of 0, and the parent a return code of the pid of the child. 


### Inter-process communication

#### Message passing
Involves the kernel to pass messages across processes. 
#### Shared memory
You need synchronization, and that can be complex to implement.
## Further reading
- [[Thread]]
- [[Virtual machines]]
- [[Operating System]]
- [[Scheduling]]
