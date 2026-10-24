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
