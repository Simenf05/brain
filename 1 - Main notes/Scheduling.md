---
aliases:
---
2026-01-19 13:19

Tags: #os #algorithms #scheduling
# Scheduling
Scheduling are policies that determine the order of execution between ready processes and threads. We have many different algorithms for scheduling, with different objectives. The scheduler can have different effects on the performance of the system. 

## Terminologies and metrics
We use different metrics to measure the effectiveness of schedulers. These can either be maximized or minimized depending on the effect. 
Maximize:
- CPU utilization (% [[Central Processing Unit|CPU]] busy)
- Throughput ([[Process]] / time)
Minimize:
- Turnaround time (time between arrival and completion)
- Waiting time (time in the ready queue)
- Response time (time between arrival and first output)
## Proportional share scheduling
This is a type of scheduling that is based on maximizing the fairness of the scheduler. If there is two users of the computer, we want to have each user get the same amount of [[Central Processing Unit|CPU]] time. The [[Linux]] kernel uses [[Completely Fair Scheduler (CFS)]], which falls into this category. 

### Lottery scheduling
Based on having tickets for each job. Every time a job is scheduled we draw from the tickets, and based on who owns the ticket we decide what to schedule. In the first few draws, it might accidentally be that one job got more CPU. Though it might be erratic at the start, through many draws, probability will even out and the scheduling will become fair. 

### [[Completely Fair Scheduler (CFS)]] (CFS)

> CFS basically models an "ideal, precise multi-tasking CPU" on real hardware.
-Ingo Molnar

Read more: [[Completely Fair Scheduler (CFS)]]

## Further reading
- [[Process]]
- [[Operating System]]
- [[Router#Round robin (RR)]]
- [[Linux]]