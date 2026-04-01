# SPSC_David – Lock-Free Ring Buffer in C

This is my personal playground for building low-latency, lock-free queues and timing infrastructure in C.

## What this does

- Lock-free single-producer/single-consumer ring buffer (`spsc_ring_buffer.h)
- Custom timing stack (`lt_platform` / `lt_timer`) that calibrates TSC
- Microbenchmarks that measure end-to-end latency in nanoseconds

## Current results

On a modern x86_64 core (hot-cache conditions):

- ~3.6B enqueue/dequeue operations over a 90-second run  
- ≈ 40M ops/sec  
- ≈ 25ns per operation

## Why I built this

I work full-time in carpentry and low-voltage (audio/video, electrical, plumbing “mechanicals”), and I’ve been teaching myself C and low-latency systems in 30-minute windows around long days on job sites. This repo tracks that journey from my first “hello world” to treating C as a low-voltage system and trying to understand where every nanosecond goes.
