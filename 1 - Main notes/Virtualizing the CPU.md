---
aliases:
---

2026-05-22 11:52

Tags: #os #virtualization #

# Virtualizing the CPU
One of the fundamental motivations for having [[Operating System]]s is to allow software to virtualize the hardware running beneath. Part of that includes providing a virtual layer of the [[Central Processing Unit|CPU]], that [[Process|processes]] can run on. One of the desirable uses for this abstraction is that we want each process running on the computer to act as if it has the entire CPU to itself. The motivation for this is that it makes it easier to make programs for the user. 
## Time sharing
To implement the abstract process, that has the entire CPU to itself, we use the concept of time sharing. Time sharing is when you have one central program (i.e. the operating system) that controls when all the other programs run. This way the computer can run multiple programs at once. But how is it achieved?
## Isolating programs
The way we achieve running multiple programs at the same time is with the concept of [[Process|processes]]. Each process gets swapped into by a method called a context switch, and after that it has the CPU to itself. The operating system makes sure to keep track of the state of the other processes while one is running. 

The operating system needs to provide isolation between processes because of security reasons. If any process can read and write to any other process, then it would be easy for malicious software to take over the computer. That is why we divide the [[Central Processing Unit|CPU]] into two (or more) different modes, kernel mode and user mode. When the CPU is in user mode it only has access to the safe instructions, like adding or dividing numbers in the registers. But when we want to do more advanced instructions, like accessing the disk, the CPU has to be in kernel mode. Kernel mode gives full access, and is used when the kernel is running. 

## Getting the control back
One of the problems is how the operating system can get back the execution from running processes. Obviously the kernel can do other things while [[system calls]] are processed, but what happens if a user program never calls system calls? One of the ways to solve this is with timers.
### Timers
The CPU has a timer that can be used to give control back to the kernel. This is called a *timer interrupt*, and it happens when a process runs for too long without giving control to the kernel. The interrupt stops the execution of the current process, and saves it state. After that it jumps to a known location in the kernel, and start handling the interrupt, often scheduling a new process to run.

## Further reading
- [[Operating System]]
- [[Central Processing Unit]]
- [[Process]]
- [Time sharing at MIT](https://www.youtube.com/watch?v=Q07PhW5sCEk)