---
aliases:
---
2026-01-19 13:19

Tags: #os #algorithms #scheduling
# Scheduling
Scheduling are policies that determine the order of execution between ready processes and threads. We have many different algorithms for scheduling, with different objectives. The scheduler can have different effects on the performance of the system. 
## Metrics
We use different metrics to measure the effectiveness of schedulers. These can either be maximized or minimized depending on the effect. Each of the [[Scheduling algorithms|scheduling algorithms]] usually aims to achieve good performance either in one of these metrics, or to be decent in multiple. Therefore determining what scheduler is the best is entirely dependent on the tasks and goals in the specific domain. 
**Maximize:**
- CPU utilization (% [[Central Processing Unit|CPU]] busy)
- Throughput ([[Process]] / time)
**Minimize:**
- Turnaround time (time between arrival and completion)
- Waiting time (time in the ready queue)
- Response time (time between arrival and first output)
- Fairness

Documents to edit:
- [[Scheduling algorithms]]
- [[Multi-Level Feedback Queue (MLFQ)]]
- [[Completely Fair Scheduler (CFS)]]
- [[Proportional share scheduling]]

## Further reading
- [[Process]]
- [[Operating System]]
- [[Router#Round robin (RR)]]
- [[Linux]]