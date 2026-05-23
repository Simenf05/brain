---
aliases:
  - scheduling algorithms
---

2026-05-22 19:50

Tags: #os #scheduling #algorithms 

# Scheduling algorithms
This document includes the most simple algorithms for scheduling. These are mostly theoretical, for learning purposes and therefore not useful in practice. To read about actual useful scheduling algorithms see: [[Multi-Level Feedback Queue (MLFQ)|MLFQ]] and [[Completely Fair Scheduler (CFS)|CFS]].
## Preemption
Preemption, also sometimes called descheduling, is when the scheduler stops a startet job, and schedules another job. For modern applications this is a critical functionality of the scheduler, as we never know how long any job will run. For all we know it might be a server, and continue running forever. This is one of the reasons that the [[#Non-preemptive scheduling algorithms]] of this document is fully theoretical. 
But to begin with we assume that the scheduler cannot preempt the jobs. 
## Non-preemptive scheduling algorithms
The non-preemptive scheduling algorithms are the simplest algorithms for scheduling. They assume, no preemption. 
### First in first out (FIFO)
The first scheduling algorithm is just using FIFO. It works like a queue, by executing processes based on arrival time. Can be implemented simply by using the queue data structure. 
#### Downside
The turnaround time can be bad, if a long process enters the queue first. All the other processes has to wait until the first one is completed. This makes FIFO a terrible algorithm in practice. This problem is called the convoy effect. 
### Shortest Job First (SJF)
The tasks with the shortest execution time is scheduled first, otherwise it works like FIFO. We assume that we cannot deschedule a process once it has started. For this type of theoretical scheduling, SJF is provably optimum. But when we allow tasks to arrive at different times it becomes bad. 
#### Downside
If task A is long is started, then if task B and C is ready while A is executing, then we have to wait for A to complete. 
## Preemptive scheduling algorithms
We now move on to the preemptive scheduling algorithms. These algorithms can stop execution of processes while they are running, and therefore are closer to real world algorithms. 
### Shortest Time-to-Complete First (STCF)
When minimizing the turnover time, we can use the STCF policy. It suggests switching to the task that has the shortest time to complete. Using this strategy we get the optimal turnaround time short tasks will get priority.
#### Downside
The fatal flaw of STCF is that it might cause starvation of tasks with long execution time. This happens when shorter tasks always arrives before the long tasks gets to run.
### Round Robin (RR)
Turnaround time is not always the most effective metric to use for evaluating the scheduler. Sometimes you want greater response time, for example when you write on the keyboard. For these cases you can use Round Robin (RR).
RR introduces a concept of time slice/time quantum/scheduling quantum, which is a small fixed slice of execution time. It will execute each process for the time slice, before switching to the next. The algorithm will switch regardless whether the task is completed, and if it is not finished it will be added to the tail of the FIFO queue. 
Is good for response-time, every process gets a good response time. 
The size of the time-slice can change the entire behavior of the algorithm. If the size is bigger then processes, then it works like FIFO. If it is small we need a lot of context switches.
#### Downside
It has poor turnaround-time. Because every task has to wait for every other task. 
There can be overhead when switching context. 

## Further reading
- [[Scheduling]]
- [[Multi-Level Feedback Queue (MLFQ)]]
- [[Completely Fair Scheduler (CFS)]]