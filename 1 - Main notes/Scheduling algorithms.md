---
aliases:
  - scheduling algorithms
---

2026-05-22 19:50

Tags: #os #scheduling #algorithms 

# Scheduling algorithms

## Non-preemptive scheduling algorithms
The non-preemptive scheduling algorithms are the simplest algorithms for scheduling. Non-preemptive means that the algorithm cannot deschedule any of the tasks after scheduling them. In practice you always want to deschedule, because you might have long running tasks that runs long. 
### First in first out (FIFO)
Works like a queue, by executing processes based on arrival time. Can be implemented simply by using the queue data structure. 
#### Downside
The turnaround time can be bad, if a long process enters the queue first. All the other processes has to wait until the first one is completed. This makes FIFO a terrible algorithm in practice. This problem is called the convoy effect. 
### Shortest Job First (SJF)
The tasks with the shortest execution time is scheduled first, otherwise it works like FIFO. We assume that we cannot de-schedule a process once it has started.
#### Downside
If task A is long is started, then if task B and C is ready while A is executing, then we have to wait for A to complete. 
## Preemptive scheduling algorithms
These algorithms can stop execution of processes while they are running. 
### Shortest Time-to-Complete First (STCF)
Always switch to the task that has the shortest time to complete. This is better because short tasks will get priority.
#### Downside
May cause starvation of tasks with long execution time, when shorter tasks always gets the prioritized. 

### Round Robin (RR)
Introduces a concept of time slice/time quantum/scheduling quantum, which is a small fixed slice of execution time. It will execute each process for the time slice, before switching to the next. The algorithm will switch regardless whether the task is completed, and if it is not finished it will be added to the tail of the FIFO queue. 
Is good for response-time, every process gets a good response time. 
The size of the time-slice can change the entire behavior of the algorithm. If the size is bigger then processes, then it works like FIFO. If it is small we need a lot of context switches.
#### Downside
It has poor turnaround-time. Because every task has to wait for every other task. 
There can be overhead when switching context. 


## Further reading
- [[Scheduling]]