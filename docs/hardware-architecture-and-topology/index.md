# Hardware architecture and topology

> **Central question:** What resources execute the work, and how are they connected?

This category examines hardware architecture and topology through the lens of LLM inference and serving engines.

## Scope

CPUs, GPUs/NPUs, memory hierarchy, NUMA, PCIe, NVLink, NIC placement.

## Learning objectives

- Map a serving workload onto compute, memory, and interconnect resources.
- Reason about topology when placing workers and model shards.
- Identify resource limits to investigate in a performance profile.

## Chapters

Chapter outlines are grouped by module. Full content will be developed one chapter at a time.

### Module 3

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M3-C01 | [Following a tensor from CPU to GPU](m3-c01-following-a-tensor-from-cpu-to-gpu.md) | Host versus device, CPU and GPU roles, host RAM and device memory, kernels, weights, activations, KV state, input and output movement |
| M3-C02 | [Reading GPU specifications and capability limits](m3-c02-reading-gpu-specifications-and-capability-limits.md) | GPU model and compute capability, SM count, memory capacity and bandwidth, cache sizes, precision-specific dense versus sparse throughput, power and clock limits, software versions |
| M3-C03 | [Threads, warps, blocks, grids, and streaming multiprocessors](m3-c03-threads-warps-blocks-grids-and-streaming-multiprocessors.md) | SIMT execution, thread indexing, warps, thread blocks, grids, SM assignment, warp scheduling, divergence, block independence |
| M3-C04 | [Occupancy, latency hiding, and hardware utilization](m3-c04-occupancy-latency-hiding-and-hardware-utilization.md) | Resident versus active and eligible warps, occupancy limits, registers and shared-memory budgets, available parallel work, latency hiding, utilization versus occupancy |
| M3-C05 | [Device memory, HBM, and the cache hierarchy](m3-c05-device-memory-hbm-and-the-cache-hierarchy.md) | Global memory, HBM versus GDDR, L2 and L1 caches, cache lines and transactions, bandwidth versus access latency, capacity, working sets, cache hits and misses |
| M3-C06 | [Registers, shared memory, and local resource pressure](m3-c06-registers-shared-memory-and-local-resource-pressure.md) | Per-thread registers, per-block shared memory, storage scope and lifetime, register spills and local memory, bank conflicts, synchronization, architecture-specific resource limits |
| M3-C13 | [PCIe, NVLink, NUMA, and device topology](m3-c13-pcie-nvlink-numa-and-device-topology.md) | Link bandwidth and latency, PCIe generation and width, NVLink availability, peer-access support, CPU socket and NUMA placement, switch paths, NIC placement, topology inspection |

Follow the complete [Module 3 reading order](../module-3.md) to move between categories.

### Module 7

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M7-C02 | [Mapping GPU and network topology before partitioning](m7-c02-mapping-gpu-and-network-topology-before-partitioning.md) | GPU memory and capability, PCIe and NVLink paths, switches, NUMA placement, NIC affinity, intra-node versus inter-node links, peer access, measured versus advertised bandwidth |

Follow the complete [Module 7 reading order](../module-7.md) to move between categories.

### Module 9

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M9-C16 | [Recording hardware conditions that change measurements](m9-c16-recording-hardware-conditions-that-change-measurements.md) | CPU and GPU models, memory capacity and bandwidth, NUMA and interconnect topology, clocks, power and thermal limits, co-tenancy and partitions, driver and runtime versions, telemetry sampling |

Follow the complete [Module 9 reading order](../module-9.md) to move between categories.
