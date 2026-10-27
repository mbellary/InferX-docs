# Kernels, compilers, and execution

> **Central question:** How is computation mapped efficiently onto hardware?

This category examines kernels, compilers, and execution through the lens of LLM inference and serving engines.

## Scope

GEMMs, attention kernels, tiling, fusion, layouts, compilation, graph replay.

## Learning objectives

- Connect model operations to kernels, layouts, and execution plans.
- Explain the tradeoffs behind tiling, fusion, and graph replay.
- Evaluate a kernel optimization against representative serving shapes.

## Chapters

[M2-C07](m2-c07-how-attention-reads-a-paged-kv-layout.md), [M3-C07](m3-c07-memory-coalescing-alignment-and-tensor-layouts.md), [M3-C08](m3-c08-tiling-and-reuse-through-the-memory-hierarchy.md), [M3-C09](m3-c09-tensor-cores-and-supported-matrix-operations.md), [M4-C01](m4-c01-defining-a-gpu-kernel-and-its-contract.md), [M4-C02](m4-c02-mapping-an-operation-onto-cuda-threads-and-blocks.md), [M4-C03](m4-c03-understanding-the-triton-programming-model.md), [M4-C04](m4-c04-compilation-specialization-and-the-warm-execution-path.md) and [M4-C05](m4-c05-tiling-an-operation-for-data-reuse.md) are completed detailed chapters; the other chapters in this category remain outlines. Full content is developed one chapter at a time using the [execution plan](../chapter-execution-plan.md).

### Module 2

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M2-C07 | [How attention reads a paged KV layout](m2-c07-how-attention-reads-a-paged-kv-layout.md) | Block-table lookup, KV tensor strides and layouts, valid token counts, partial tail blocks, gather access, kernel-layout compatibility, metadata and data movement |

Follow the complete [Module 2 reading order](../module-2.md) to move between categories.

### Module 3

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M3-C07 | [Memory coalescing, alignment, and tensor layouts](m3-c07-memory-coalescing-alignment-and-tensor-layouts.md) | Warp memory accesses, contiguous versus strided access, alignment, memory transactions, useful versus transferred bytes, tensor strides, layout conversion costs |
| M3-C08 | [Tiling and reuse through the memory hierarchy](m3-c08-tiling-and-reuse-through-the-memory-hierarchy.md) | Matrix tiles, global-to-shared-to-register movement, reuse, synchronization, tile-size tradeoffs, edge tiles, shared-memory capacity, data movement versus redundant work |
| M3-C09 | [Tensor cores and supported matrix operations](m3-c09-tensor-cores-and-supported-matrix-operations.md) | Matrix multiply-accumulate, tensor-core versus scalar execution paths, operand and accumulator formats, shape and alignment requirements, dense versus sparse paths, architecture-dependent capabilities |

Follow the complete [Module 3 reading order](../module-3.md) to move between categories.

### Module 4

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M4-C01 | [Defining a GPU kernel and its contract](m4-c01-defining-a-gpu-kernel-and-its-contract.md) | Kernel inputs and outputs, shapes, strides, dtypes, devices, aliasing, valid memory ranges, mathematical reference behavior, launch configuration |
| M4-C02 | [Mapping an operation onto CUDA threads and blocks](m4-c02-mapping-an-operation-onto-cuda-threads-and-blocks.md) | CUDA execution model, thread and block indexing, SIMT execution, memory access, masked boundaries, warp and block cooperation, synchronization scope |
| M4-C03 | [Understanding the Triton programming model](m4-c03-understanding-the-triton-programming-model.md) | Triton programs and launch grids, block-oriented operations, masks, loads and stores, reductions, compile-time parameters, comparison with CUDA, Rust host integration boundaries |
| M4-C04 | [Compilation, specialization, and the warm execution path](m4-c04-compilation-specialization-and-the-warm-execution-path.md) | Ahead-of-time and just-in-time compilation, device targets, generated artifacts, specialization keys, compilation caches, first-use overhead, cold versus warm execution, version compatibility |
| M4-C05 | [Tiling an operation for data reuse](m4-c05-tiling-an-operation-for-data-reuse.md) | Tile selection, register and shared-memory reuse, coalesced accesses, edge tiles, redundant work, data-movement accounting, synchronization costs |
| M4-C06 | [Parallel reductions and synchronization](m4-c06-parallel-reductions-and-synchronization.md) | Tree reductions, warp and block reductions, cross-block decomposition, neutral elements, masked lanes, synchronization, reduction order, accumulation precision |
| M4-C08 | [Kernel fusion and its tradeoffs](m4-c08-kernel-fusion-and-its-tradeoffs.md) | Producer-consumer fusion, intermediate tensors, eliminated reads and writes, reduced launches, dependency boundaries, resource growth, fusion versus recomputation |
| M4-C09 | [Register pressure, occupancy, and spills in kernel design](m4-c09-register-pressure-occupancy-and-spills-in-kernel-design.md) | Live values, register allocation, tile and fusion choices, occupancy limits, local-memory spills, instruction parallelism, measured utilization versus occupancy |
| M4-C10 | [Shape specialization, padding, and dispatch](m4-c10-shape-specialization-padding-and-dispatch.md) | Shape families, strides and alignment, padding overhead, masked lanes, padded reduction identities, specialization count, dispatch guards, generic fallbacks |
| M4-C11 | [FlashAttention as an IO-aware attention algorithm](m4-c11-flashattention-as-an-io-aware-attention-algorithm.md) | Tiled QK and value aggregation, online softmax, HBM versus on-chip storage, avoiding full attention-matrix materialization, mathematical exactness versus floating-point differences, quadratic full-attention arithmetic |
| M4-C12 | [Distinguishing FlashAttention, PagedAttention, and prefix caching](m4-c12-distinguishing-flashattention-pagedattention-and-prefix-caching.md) | Intermediate-data movement, dynamic KV layout, exact-prefix reuse, complementary techniques, applicability and compatibility, correctness boundaries, choosing the constrained stage |
| M4-C15 | [CUDA Graph capture, instantiation, and replay](m4-c15-cuda-graph-capture-instantiation-and-replay.md) | Graph nodes and dependencies, explicit construction versus stream capture, instantiation, repeated submission, setup amortization, capture restrictions, graph versus kernel fusion |
| M4-C17 | [Designing a fused normalization kernel](m4-c17-designing-a-fused-normalization-kernel.md) | LayerNorm versus RMSNorm, row-wise reductions, epsilon placement, affine parameters, residual fusion options, accumulation precision, output dtype, traffic and launch savings |
| M4-C18 | [Designing a fused sampling kernel](m4-c18-designing-a-fused-sampling-kernel.md) | Logit transforms, temperature, greedy selection, top-k and top-p boundaries, normalization, random draws, tie rules, vocabulary padding, exact versus approximate sampling contracts |

Follow the complete [Module 4 reading order](../module-4.md) to move between categories.

### Module 6

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M6-C11 | [Packing, dequantization, and quantized kernel execution](m6-c11-packing-dequantization-and-quantized-kernel-execution.md) | Bit packing, alignment and padding, group metadata, fused versus separate dequantization, compute paths, hardware support, kernel eligibility, conversion overhead, effective memory savings |

Follow the complete [Module 6 reading order](../module-6.md) to move between categories.
