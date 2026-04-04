# SPSC_David – Lock-Free Ring Buffer in C

This repository is my personal lab for exploring and measuring low-latency, lock-free data structures in C.

---

## What It Does
- Lock-free single-producer/single-consumer ring buffer (`spsc_ring_buffer.h`)
- Custom timing stack with calibrated TSC
- Microbenchmarks measuring end-to-end latency at the nanosecond level

---

## Current Results
Tested on a modern x86_64 core (hot-cache conditions, single producer/consumer):

- ~3.6 billion enqueue/dequeue operations over 90 seconds
- ≈ 40 million operations/sec
- ≈ 25 ns per operation

---

## Measurement Notes
- TSC calibrated at startup
- Hot-cache, single-core, SPSC workload (no cross-core contention)
- Focus on consistency and reasoning, not peak benchmark tuning

---

## Why I Built This
I work full-time in carpentry and low-voltage systems (audio/video, electrical, plumbing). Over the past year, I've been teaching myself C and systems programming in small windows around long days on job sites.

This project reflects that progression:
- From basic C syntax to reasoning about atomics and memory ordering
- From "writing code" to understanding latency at the cycle level

> "I spent the last year in a quiet lab learning MOESI/MESI to understand the load paths of the CPU. I built a 7,000-line library from scratch and can whiteboard the physics of an SPSC handoff at 40 million ops/sec."

---

## The Builder's Perspective
> "I approach a CPU the way I approach a high-end framing project. I look for the load-bearing members (the memory bus), the friction points (cache misses), and the structural integrity (atomic guarantees). 40 million ops/sec isn't just a number — it's the result of aligning the grain of the silicon with the flow of data."
