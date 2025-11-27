2025-11-27 10:27

Tags: #computers #datamaskiner #sevengreatideas

# Seven great ideas in computer architecture

## Abstraction
The use of abstraction is needed in order to simplify design. This way users of the computer don't have to worry about the little details of every piece of hardware. One big abstraction is the [[operating system]], that provides a layer of abstraction from the hardware. The operating system is a software abstraction, but we also have abstractions within the hardware. 

## Make the common case fast
This is a principle about making the most basic instructions in the machine as fast as possible. Without this you might end up making some parts of the system really fast, and spend much time and effort on it. But if only a handful of instructions use that part of the system. Therefore you should always optimize the part of the system that is used the most. 

## Performance via Parallelism 
Parallelism can be achieved by having multiple cores in a chip. With this the chip will need more logic, and the complexity will grow, but the gain can be massive. For some tasks that are able to be sped up in parallell the running time becomes proportional to the amount of cores that your chip has. Tasks like this can be [[compiling]] software, and calculating graphics. 

## Performance via Pipelining
Pipelining is a technique where you split up the task needed to be completed into multiple parts of a pipeline. This way the clock cycle frequency can be increased, and the system is able to achieve higher performance. The [[The processor#Pipelined datapath|pipelined datapath]] is a implementation of the use of pipelining in processors. 

## Performance via Prediction
Prediction can often be faster than waiting to be certain of what to do. It is mostly used in piplined architectures, and used on branching instructions. This is because branch instruction have a binary outcome. This way just by guessing randomly, and the branching instructions jumping and not jumping as frequently as each other, then you should get 50% on average. With some more advanced algorithms you can achieve way better branching, and modern chips usually is above 90%. 

## [[Hierarchy of Memory]]
Memory can often be the bottleneck in speed, and therefore memory should be both fast and big. For this to work we need a system that has multiple layers of memory. The first layer is small but fast, this is the first memory we check and is called L1 cache. If the L1 cache misses, we go to the next layer. This is L2 cache and here we have more storage but it is slower. The layers continue like this until every layer is exhausted, and we use the main memory that contains every value. 

## Dependability via Redundancy
If some parts of the system breaks, we need the chip to still work. And therefore we include redundant parts that can take over, this way the chip still can work. 

