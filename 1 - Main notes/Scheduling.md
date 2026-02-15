---
aliases:
---
2026-01-19 13:19

Tags: #os #algorithms #scheduling
# Scheduling
Scheduling are policies that determine the order of execution between ready processes and threads. We have many different algorithms for scheduling, with different objectives. The scheduler can have different effects on the performance of the system. 

## Terminologies
We use different metrics to measure the effectiveness of schedulers. These can either be maximized or minimized depending on the effect. 
Maximize:
- CPU utilization (% [[Central Processing Unit|CPU]] busy)
- Throughput ([[Process]] / time)
Minimize:
- Turnaround time (time between arrival and completion)
- Waiting time (time in the ready queue)
- Response time (time between arrival and first output)

# Scheduling algorithms
## Non-preemptive scheduling algorithms
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

## Priority-based Scheduling
We schedule tasks based on priority, each process has an integer representing the priority. The task with the highest priority is always scheduled. 
There can be starvation, because there can always be tasks with better priority that makes one task never get cpu time. To solve this we use aging, and allow old tasks to gain priority. 

### Multi-level feedback queue (MLFQ)
It is a good scheduling algorithm because it does not require prior knowledge of estimated time use for each job. 
#### Rules
1. If `priority(A) > priority(B): A runs`
2. If `priority(A) == priority(B): A and B run with RR`
3. Jobs that enter the system are placed at the highest priority
- 4a If a job uses entire time slice, lower priority
- 4b If a job gives back cpu before time slice, keep priority
5. After time S, move all the jobs to the topmost level
To prevent abuse of rule four by always giving up right before time slice is used up, we instead use time allotment. This works by keeping track of time used per job, and moving jobs down when the time is used up. 
## Proportional share scheduling
This is a type of scheduling that is based on maximizing the fairness of the scheduler. If there is two users of the computer, we want to have each user get the same amount of [[Central Processing Unit|CPU]] time. The [[Linux]] kernel uses [[Completely Fair Scheduler]], which falls into this category. 

### Lottery scheduling
Based on having tickets for each job. Every time a job is scheduled we draw from the tickets, and based on who owns the ticket we decide what to schedule. In the first few draws, it might accidentally be that one job got more CPU. Though it might be erratic at the start, through many draws, probability will even out and the scheduling will become fair. 

### [[Completely Fair Scheduler]] (CFS)

> CFS basically models an "ideal, precise multi-tasking CPU" on real hardware.
-Ingo Molnar

Read more: [[Completely Fair Scheduler]]

## Further reading
- [[Process]]
- [[Operating System]]
- [[Router#Round robin (RR)]]
- [[Linux]]