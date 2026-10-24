# State, memory, and caching

> **Central question:** What must be retained, shared, fetched, or reconstructed?

This category examines state, memory, and caching through the lens of LLM inference and serving engines.

## Scope

KV allocation, paging, prefix reuse, window state, snapshots, eviction, replay.

## Learning objectives

- Trace the ownership and lifetime of request state.
- Reason about allocation, prefix reuse, eviction, and reconstruction.
- Define the validity conditions for reusing cached state.

## Chapters

Module 1 chapter outlines, listed in learning order. Full content will be developed one chapter at a time.

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M1-C05 | [How tensors occupy memory](m1-c05-how-tensors-occupy-memory.md) | Bytes, contiguous storage, strides, row-major and column-major layouts, reshaping, transposing, views versus copies, broadcasting |
| M1-C17 | [Reusing attention state with a KV cache](m1-c17-reusing-attention-state-with-a-kv-cache.md) | Repeated computation without caching, per-layer keys and values, cache shapes, appending state, cache growth, position offsets, cached causal masking |

Follow the complete [Module 1 reading order](../module-1.md) to move between categories.
