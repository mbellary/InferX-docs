# Module 3: Learn GPU architecture through data movement

> **Status: 23 of 23 detailed chapters complete.** M3-C01–M3-C23 are complete. Module 3 detailed documentation is complete; hardware experiments remain proposed. Next in authoring order is [M4-C01](kernels-compilers-and-execution/m4-c01-defining-a-gpu-kernel-and-its-contract.md). Track one-chapter-at-a-time development in the [execution plan](chapter-execution-plan.md).

## Learning goal

Explain where each important inference tensor lives, how it moves, which operations consume it, and which resources constrain execution. Build from beginner hardware concepts toward measurements of matrix-vector multiplication, matrix-matrix multiplication, and memory copies across shapes and sizes.

Use a Rust-first learning path, with Python or C++ when Rust is unsupported. Chapters explain concepts and experimental procedures without code implementation.

## Prerequisites and scope

Follow [Module 1](module-1.md) for tensor shapes, numerical computing, and generation, and [Module 2](module-2.md) for cache storage and ownership. Introduce GPU architecture, memory hierarchy, execution units, and interconnect terminology from first principles.

The baseline experiments require one supported GPU. NVIDIA CUDA documentation is the primary reference for NVIDIA-specific concepts; actual capabilities depend on the installed device and software. CPU-side reasoning can prepare the workload and reference results, but does not establish GPU performance. Multi-GPU and network-path measurements are optional extensions requiring the corresponding hardware. Detailed kernel implementation, compilation, graph replay, and distributed inference will be developed in later modules.

## Models to investigate

**Arithmetic intensity = FLOPs / bytes moved**

Define the memory level and accounting boundary for the bytes: algorithmic payload, device-memory traffic, cache traffic, and interconnect traffic are different quantities.

**Estimated kernel-time floor ≈ max(FLOPs / effective compute throughput, bytes moved / effective memory bandwidth)**

Use compatible precision, operation-count conventions, and measurement boundaries for both terms. This is a modeling estimate under stated assumptions, not a guaranteed prediction. Launch overhead, dependencies, synchronization, and communication also affect actual execution. The roofline and byte-accounting chapters will explain these assumptions and how to test them.

Batching may let more computation reuse weights and increase arithmetic intensity. The learning path investigates when that happens, when cache capacity or another resource becomes limiting, and how batching delay changes end-to-end latency.

## Reading order

Chapters remain under their assigned top-level categories. Follow this sequence across categories.

| Chapter ID | Category | Chapter name | Target concepts |
| --- | --- | --- | --- |
| M3-C01 | [Hardware architecture and topology](hardware-architecture-and-topology/index.md) | [Following a tensor from CPU to GPU](hardware-architecture-and-topology/m3-c01-following-a-tensor-from-cpu-to-gpu.md) | Host versus device, CPU and GPU roles, host RAM and device memory, kernels, weights, activations, KV state, input and output movement |
| M3-C02 | [Hardware architecture and topology](hardware-architecture-and-topology/index.md) | [Reading GPU specifications and capability limits](hardware-architecture-and-topology/m3-c02-reading-gpu-specifications-and-capability-limits.md) | GPU model and compute capability, SM count, memory capacity and bandwidth, cache sizes, precision-specific dense versus sparse throughput, power and clock limits, software versions |
| M3-C03 | [Hardware architecture and topology](hardware-architecture-and-topology/index.md) | [Threads, warps, blocks, grids, and streaming multiprocessors](hardware-architecture-and-topology/m3-c03-threads-warps-blocks-grids-and-streaming-multiprocessors.md) | SIMT execution, thread indexing, warps, thread blocks, grids, SM assignment, warp scheduling, divergence, block independence |
| M3-C04 | [Hardware architecture and topology](hardware-architecture-and-topology/index.md) | [Occupancy, latency hiding, and hardware utilization](hardware-architecture-and-topology/m3-c04-occupancy-latency-hiding-and-hardware-utilization.md) | Resident versus active and eligible warps, occupancy limits, registers and shared-memory budgets, available parallel work, latency hiding, utilization versus occupancy |
| M3-C05 | [Hardware architecture and topology](hardware-architecture-and-topology/index.md) | [Device memory, HBM, and the cache hierarchy](hardware-architecture-and-topology/m3-c05-device-memory-hbm-and-the-cache-hierarchy.md) | Global memory, HBM versus GDDR, L2 and L1 caches, cache lines and transactions, bandwidth versus access latency, capacity, working sets, cache hits and misses |
| M3-C06 | [Hardware architecture and topology](hardware-architecture-and-topology/index.md) | [Registers, shared memory, and local resource pressure](hardware-architecture-and-topology/m3-c06-registers-shared-memory-and-local-resource-pressure.md) | Per-thread registers, per-block shared memory, storage scope and lifetime, register spills and local memory, bank conflicts, synchronization, architecture-specific resource limits |
| M3-C07 | [Kernels, compilers, and execution](kernels-compilers-and-execution/index.md) | [Memory coalescing, alignment, and tensor layouts](kernels-compilers-and-execution/m3-c07-memory-coalescing-alignment-and-tensor-layouts.md) | Warp memory accesses, contiguous versus strided access, alignment, memory transactions, useful versus transferred bytes, tensor strides, layout conversion costs |
| M3-C08 | [Kernels, compilers, and execution](kernels-compilers-and-execution/index.md) | [Tiling and reuse through the memory hierarchy](kernels-compilers-and-execution/m3-c08-tiling-and-reuse-through-the-memory-hierarchy.md) | Matrix tiles, global-to-shared-to-register movement, reuse, synchronization, tile-size tradeoffs, edge tiles, shared-memory capacity, data movement versus redundant work |
| M3-C09 | [Kernels, compilers, and execution](kernels-compilers-and-execution/index.md) | [Tensor cores and supported matrix operations](kernels-compilers-and-execution/m3-c09-tensor-cores-and-supported-matrix-operations.md) | Matrix multiply-accumulate, tensor-core versus scalar execution paths, operand and accumulator formats, shape and alignment requirements, dense versus sparse paths, architecture-dependent capabilities |
| M3-C10 | [State, memory, and caching](state-memory-and-caching/index.md) | [Host and device buffer placement and lifetime](state-memory-and-caching/m3-c10-host-and-device-buffer-placement-and-lifetime.md) | Pageable versus pinned host memory, device allocations, unified addressing versus unified memory, migration and residency, buffer reuse, ownership across transfers, allocation outside timed regions |
| M3-C11 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Streams, events, and dependency ordering](runtime-and-concurrency/m3-c11-streams-events-and-dependency-ordering.md) | Asynchronous submission versus completion, stream ordering, cross-stream events, default-stream semantics, synchronization scope, producer-consumer dependencies, safe buffer reuse |
| M3-C12 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Asynchronous copies and useful overlap](runtime-and-concurrency/m3-c12-asynchronous-copies-and-useful-overlap.md) | Copy engines, pinned-memory requirements, double buffering, copy-compute overlap, independence and resource constraints, backpressure, cancellation with in-flight work, asynchronous error observation |
| M3-C13 | [Hardware architecture and topology](hardware-architecture-and-topology/index.md) | [PCIe, NVLink, NUMA, and device topology](hardware-architecture-and-topology/m3-c13-pcie-nvlink-numa-and-device-topology.md) | Link bandwidth and latency, PCIe generation and width, NVLink availability, peer-access support, CPU socket and NUMA placement, switch paths, NIC placement, topology inspection |
| M3-C14 | [Networking and communication](networking-and-communication/index.md) | [Moving tensors between devices and hosts](networking-and-communication/m3-c14-moving-tensors-between-devices-and-hosts.md) | Host-device, device-device, peer-to-peer and staged transfers, network fabrics, RDMA and GPUDirect concepts, transfer completion, shared-link contention, communication scope and limits |
| M3-C15 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Counting FLOPs and bytes at a defined boundary](measurement-experimentation-and-economics/m3-c15-counting-flops-and-bytes-at-a-defined-boundary.md) | GEMV and GEMM dimensions, multiply-add counting, theoretical versus observed traffic, memory-level boundaries, cache reuse, reads and writes, units, achieved throughput and bandwidth |
| M3-C16 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Using the roofline model to predict bottlenecks](measurement-experimentation-and-economics/m3-c16-using-the-roofline-model-to-predict-bottlenecks.md) | Arithmetic intensity, compute and bandwidth roofs, ridge point, idealized kernel-time estimates, effective versus peak rates, hierarchical rooflines, launch and dependency limits |
| M3-C17 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Batching, weight reuse, and shifting bottlenecks](scheduling-and-queueing/m3-c17-batching-weight-reuse-and-shifting-bottlenecks.md) | Batch size and matrix shapes, weight reuse, arithmetic intensity changes, prefill versus decode tendencies, working-set limits, saturation, batching delay versus service time |
| M3-C18 | [Numerics and correctness](numerics-and-correctness/index.md) | [Validating GPU computation and memory movement](numerics-and-correctness/m3-c18-validating-gpu-computation-and-memory-movement.md) | Reference GEMV and GEMM outputs, accumulation precision, absolute and relative tolerances, reduction-order differences, transfer integrity, shape and stride checks, race and lifetime faults |
| M3-C19 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Designing trustworthy asynchronous GPU benchmarks](measurement-experimentation-and-economics/m3-c19-designing-trustworthy-asynchronous-gpu-benchmarks.md) | Device-event versus host-wall timing, timing boundaries, completion waits, launch overhead, warmup, repeated trials, cache state, clocks and thermals, interference, distributions, profiler overhead |
| M3-C20 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Benchmarking memory copies across sizes and paths](measurement-experimentation-and-economics/m3-c20-benchmarking-memory-copies-across-sizes-and-paths.md) | Host-to-device, device-to-host and device-to-device copies, pageable versus pinned buffers, size sweeps, setup versus transfer costs, payload versus read-plus-write bandwidth, overlap and contention |
| M3-C21 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Benchmarking matrix-vector multiplication across shapes](measurement-experimentation-and-economics/m3-c21-benchmarking-matrix-vector-multiplication-across-shapes.md) | GEMV shape sweeps, weight and vector traffic, output writes, cache-resident versus device-memory working sets, bandwidth utilization, small-workload overhead, correctness checks |
| M3-C22 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Benchmarking matrix-matrix multiplication across shapes](measurement-experimentation-and-economics/m3-c22-benchmarking-matrix-matrix-multiplication-across-shapes.md) | GEMM shape and batch sweeps, operand reuse, tensor-core eligibility, tile utilization, alignment and edge effects, precision controls, achieved compute throughput, GEMV comparison |
| M3-C23 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Explaining GPU profiles and end-to-end serving effects](measurement-experimentation-and-economics/m3-c23-explaining-gpu-profiles-and-end-to-end-serving-effects.md) | Nsight Systems timelines, Nsight Compute counters, kernel versus request critical paths, memory traffic, occupancy and stalls, roofline reconciliation, controlled comparisons, tail latency, reproducible evidence |

## How chapters will be developed

Use the relevant [Module 9 support guidance](module-9.md#support-for-modules-1-7) throughout this module for reference behavior, correctness, measurement, and validation. Create detailed chapters using the [chapter authoring order](chapter-authoring-order.md).

Every chapter follows **Concepts → Experiments → Verification**, applying all [six dimensions and eight engineering principles](learning-approach.md). Connect inference data movement to systems engineering and High-Frequency Trading concerns such as critical-path latency, preallocated buffers, bounded resource use, ownership, asynchronous completion, and variability. Explain the limits of each analogy.

The eventual build is a benchmark suite for memory copies, matrix-vector multiplication, and matrix-matrix multiplication. Require correctness before performance comparisons; record shapes, precision, layouts, placement, hardware, software, cache state, and timing boundaries. Compare predictions with measured traffic and utilization, then assess implications for full-request behavior. This page and its chapter outlines contain no benchmark results or implementation code.

## Sources

- [NVIDIA CUDA Toolkit documentation](https://docs.nvidia.com/cuda/): the documentation entry point requested for this module.
- [CUDA Programming Guide](https://docs.nvidia.com/cuda/cuda-programming-guide/): execution, memory, synchronization, and device capabilities.
- [CUDA Best Practices Guide](https://docs.nvidia.com/cuda/cuda-c-best-practices-guide/): data movement, memory access, performance measurement, and optimization guidance.
- [Nsight Compute Profiling Guide](https://docs.nvidia.com/nsight-compute/ProfilingGuide/): kernel metrics, roofline analysis, and profiling overhead.
- [Nsight Systems User Guide](https://docs.nvidia.com/nsight-systems/UserGuide/): host/device timelines and application-level profiling.

Select device-specific hardware specifications and record the versions of these references when each chapter is authored.
