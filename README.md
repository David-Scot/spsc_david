SPSC_David – Lock-Free Ring Buffer in C

This repository is a personal project focused on building and measuring low-latency, lock-free data structures in C.

Overview
Lock-free single-producer/single-consumer (SPSC) ring buffer (spsc_ring_buffer.h)
Custom timing harness using calibrated TSC
Microbenchmarks measuring throughput and propagation latency
Results

Tested on a modern x86_64 CPU under controlled conditions (hot cache, pinned threads, single producer/consumer):

~3.6 billion operations over 90 seconds
~40 million operations/sec
~25 ns per enqueue/dequeue pair
Measurement Notes
TSC calibrated at startup
Measurements taken under hot-cache conditions
Single-core SPSC workload (no cross-core contention)
Focus on consistency and reproducibility over peak tuning
## Why I Built This
I work full-time in carpentry and low-voltage systems (audio/video, electrical, plumbing). Over the past year, I've been teaching myself C and systems programming in small windows around long days on job sites.

This project reflects that progression:
- From basic C syntax to reasoning about atomics and memory ordering
- From "writing code" to understanding latency at the cycle level

> "I spent the last year in a quiet lab learning TSO/MOESI/MESI to understand the load paths of the CPU, evaluating cache-coherent behavior in SPSC pipelines, including batching, shadow indices, and structure layout tradeoffs.. I built a 7,000-line library from scratch and can whiteboard the physics of an SPSC handoff at 40 million ops/sec."
---

## The Builder's Perspective
> "I approach a CPU the way I approach a high-end framing project. I look for the load-bearing members (the memory bus), the friction points (cache misses), and the structural integrity (atomic guarantees). 40 million ops/sec isn't just a number — it's the result of aligning the flow of data."
