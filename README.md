SPSC_David – Lock-Free Ring Buffer in C

This repository is my personal lab for building and measuring low-latency, lock-free data structures in C.

What this does
Lock-free single-producer / single-consumer ring buffer (spsc_ring_buffer.h)
Custom timing stack (lt_platform, lt_timer) with calibrated TSC
Microbenchmarks measuring end-to-end latency at the nanosecond level
Current Results

On a modern x86_64 core (hot-cache conditions, single producer/consumer):

~3.6 billion enqueue/dequeue operations over 90 seconds
≈ 40 million operations/sec
≈ 25 ns per operation
Measurement Notes
TSC calibrated at startup
Measurements taken under hot-cache conditions
Single-core, SPSC workload (no cross-core contention yet)
Focus is on consistency and reasoning, not peak benchmark tuning
Why I built this

I work full-time in carpentry and low-voltage systems (audio/video, electrical, plumbing).
Over the past year, I’ve been teaching myself C and systems programming in small windows around long days on job sites.

This project tracks that progression:

from basic C
to understanding atomics and memory ordering
to reasoning about latency at the cycle level

I approach C the same way I approach physical systems:

load paths, failure points, and where energy (or time) is lost
"I spent the last year in a 'lonely' lab learning MOESI/MESI because I wanted to understand the load paths of the CPU. 
I've built a 7,000-line library from scratch, and I can whiteboard the physics of an SPSC handoff at 40 million ops/sec."

The Builder’s Perspective: > "I approach a CPU the way I approach a high-end framing project. 
I look for the load-bearing members (the memory bus), the friction points (cache misses), and the structural integrity (atomic guarantees). 
40 million ops/sec isn't just a number; it’s the result of ensuring the 'grain' of the silicon is aligned with the flow of the data."
