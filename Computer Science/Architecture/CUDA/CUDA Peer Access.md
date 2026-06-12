---
date: 2026-06-10
---
*CUDA Peer Access* allows one [[GPU]] to directly read from or write to another GPU's device [[Memory|memory]] without routing data through the [[CPU]] or host memory. It is enabled explicitly with `cudaDeviceEnablePeerAccess()` and requires compatible hardware (devices on the same PCIe root complex or connected via NVLink).

Direct GPU-to-GPU transfers reduce latency and free the CPU from mediating inter-GPU communication.
