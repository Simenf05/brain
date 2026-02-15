---
aliases:
---

2026-02-15 17:39

Tags: #os #scheduling #algorithms 

# Completely Fair Scheduler
It is the currently in use algorithm for the [[Linux]] scheduler. It has a focus on keeping overhead low while still being fair between processes. 

## Scheduling method
- Choose the process with lowest virtual runtime (vruntime)
- Run each process for a time slice.
- Determine time slice based on sched_latency, the number of processes, and priority
### Nice value
The priority is based on the nice value. It ranges from -20 to 19 and the default is 0. Positive nice value indicates low priority and negative is high priority. The nice value is used to determine the time slice.


## Further reading
- [[Scheduling]]
- [[Operating System]]
- [[Linux]]
