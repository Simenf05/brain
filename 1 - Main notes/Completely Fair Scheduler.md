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




## Further reading
- [[Scheduling]]
- [[Operating System]]
- [[Linux]]
