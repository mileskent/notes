---
date: 2026-06-10
---
*Pinned memory* (page-locked memory) is host [[Memory]] that is locked in physical RAM and cannot be paged out by the [[Operating System|OS]]. This allows the [[GPU]] to access it directly via [[DMA]], enabling faster and asynchronous [[CPU]]-to-[[GPU]] transfers compared to pageable memory, which must first be staged through a temporary buffer.

Allocated with `cudaMallocHost()`. The tradeoff is reduced available memory for the [[Operating System|OS]] and other processes.
