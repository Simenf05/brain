---
aliases:
  - recovery
---

2026-05-06 10:25

Tags: #database #dbms 

# Recovery
Recovery is a critical part of [[Database management system (DBMS)|DBMS]], and serves as one of the important part in order to comply with [[Transactions#ACID|ACID]]. Databases will need to recover, and for that we need to keep track of recovery. 

## Schedules
A schedule is a compilation of operations from [[Transactions|transactions]] that happen in a specified order.
### Recoverable schedules 
Recoverable schedules are schedules that can be saved in recovery. For example:
$$
\text{H}_1: \text{w}_2(\text{A});\text{w}_1(\text{B});\text{w}_1(\text{A});\text{r}_2(\text{B});\text{c}_1;\text{c}_2
$$
This is a recoverable history. That is because every transaction commits after each of the other transactions that it has read from. Transaction 2 reads from transaction 1, and therefore it has to commit after transaction 1. If $\text{c}_1$  and $\text{c}_2$ was swapped, it would not be recoverable. 
### Avoid Cascading Aborts (ACA)
Avoid Cascading Aborts is the next level for schedules, and every ACA schedule is also recoverable. The new rule is that each transaction only can read from committed data objects from other transactions. $\text{H}_1$ is not ACA, but $\text{H}_2$ is:
$$
\text{H}_2:
\text{w}_1(\text{A});\text{w}_1(\text{B});\text{w}_2(\text{A});\text{c}_1;\text{r}_2(\text{B});\text{c}_2
$$
### Strict 
Strict schedule means that other transactions never can either write or read from uncommitted values. This means that we can do undo recovery by before images. 

The schedules have the subset property:
$\text{Strict}\subset\text{ACA}\subset\text{Recoverable}\subset\text{All schedules}$

## Further reading
- [[Transactions]]