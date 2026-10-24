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

Chapter outlines are grouped by module. Full content will be developed one chapter at a time.

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
