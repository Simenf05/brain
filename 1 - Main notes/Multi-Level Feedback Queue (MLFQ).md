---
aliases:
  - mlfq
  - MLFQ
---

2026-05-22 19:53

Tags: #os #scheduling #algorithms #onlinealgorithms

# Multi-Level Feedback Queue (MLFQ)

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


## Further reading
- [[Scheduling]]
- [[Scheduling algorithms]]
