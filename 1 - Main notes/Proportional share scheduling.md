---
aliases:
  - proportional share scheduling
---

2026-05-22 20:40

Tags: #os #scheduling

# Proportional share scheduling
This is a type of scheduling that is based on maximizing the fairness of the scheduler. If there is two users of the computer, we want to have each user get the same amount of [[Central Processing Unit|CPU]] time. The [[Linux]] kernel uses [[Completely Fair Scheduler (CFS)]], which falls into this category. 
### Lottery scheduling
Based on having tickets for each job. Every time a job is scheduled we draw from the tickets, and based on who owns the ticket we decide what to schedule. In the first few draws, it might accidentally be that one job got more CPU. Though it might be erratic at the start, through many draws, probability will even out and the scheduling will become fair. 

### [[Completely Fair Scheduler (CFS)]] (CFS)

> CFS basically models an "ideal, precise multi-tasking CPU" on real hardware.
-Ingo Molnar

Read more: [[Completely Fair Scheduler (CFS)]]

## Further reading
- [[Scheduling]]
- [[Scheduling algorithms]]
- [[Completely Fair Scheduler (CFS)]]