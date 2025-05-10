---
tags:
  - Computing
---
What is CUDA? 
General purpose computing on graphical processing units.

What is OpenGL
OpenGL (Open Graphics Library[3]) is a cross-language, cross-platform application programming interface (API) for rendering 2D and 3D vector graphics. The API is typically used to interact with a graphics processing unit (GPU), to achieve hardware-accelerated rendering.

# Concurrent programming with GPUs

Multiprocessing/Parallel/Concurrent programming are synonymous

What are cores?

What are threads?
https://www.guru99.com/cpu-core-multicore-thread.html

Difference between Core vs. Threads

Parameters	| Core | Threads
------|--------|------
Definition	 | CPU cores mean the actual hardware component.	| Threads refer to the virtual component which manages the tasks.
Process	| The CPU is fed tasks from a thread. Therefore, it only accesses the second thread when the information sent by the first thread is not reliable.	|There are many different variations of how CPU can interacts with multiple threads.
Implementation | Achieved through interleaving operation| Performed through suing multiple CPU’S
Benefit	|Increase the amount of work accomplished at a time.	|Improve throughput, computational speed-up.
Make use of	|Core uses content switching	|Uses multiple CPUs for operating numerous processes.
Processing units required	|Requires only signal process unit.	|Requires multiple processing units.
Example	|Running multiple application at the same time.	|Running web crawler on a cluster.

Common Pitfall in Concurrent Programming
- Race Conditions
- Resource contention
- dead Lock
- live lock
- non-optimal resource utilization

Concurrent Programming Problems and Algorithms
