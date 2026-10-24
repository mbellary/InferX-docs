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

Full content will be developed one chapter at a time.

### Module 1

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M1-C05 | [How tensors occupy memory](m1-c05-how-tensors-occupy-memory.md) | Bytes, contiguous storage, strides, row-major and column-major layouts, reshaping, transposing, views versus copies, broadcasting |
| M1-C17 | [Reusing attention state with a KV cache](m1-c17-reusing-attention-state-with-a-kv-cache.md) | Repeated computation without caching, per-layer keys and values, cache shapes, appending state, cache growth, position offsets, cached causal masking |

Follow the complete [Module 1 reading order](../module-1.md) to move between categories.

### Module 2

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M2-C01 | [What the KV cache retains and why](m2-c01-what-the-kv-cache-retains-and-why.md) | Cached keys and values, model weights versus request state, reuse versus recomputation, prefill and decode cache access, logical token positions |
| M2-C03 | [Calculating KV memory and request capacity](m2-c03-calculating-kv-memory-and-request-capacity.md) | Uniform full-attention KV formula, bytes per element, KiB and GiB, cached token counts, 128 KiB per token example, concurrency and context budgets, payload versus overhead |
| M2-C04 | [Memory ownership, handles, and lifetimes from first principles](m2-c04-memory-ownership-handles-and-lifetimes-from-first-principles.md) | Allocation and reclamation, addresses versus handles, Rust ownership and borrowing concepts, request identity, stale handles, use-after-free, double-free |
| M2-C05 | [Contiguous KV storage and its limits](m2-c05-contiguous-kv-storage-and-its-limits.md) | Contiguous allocation, reserved versus used capacity, growth and copying, external fragmentation, allocation failure despite free space, contiguous baseline |
| M2-C06 | [Paged KV storage and logical-to-physical mapping](m2-c06-paged-kv-storage-and-logical-to-physical-mapping.md) | Operating-system paging analogy and limits, fixed-size token blocks, block tables, block offsets, noncontiguous physical storage, PagedAttention, mapping metadata |
| M2-C08 | [Designing a fixed-size KV block allocator](m2-c08-designing-a-fixed-size-kv-block-allocator.md) | Preallocated block pools, block IDs, free lists, allocation and release contracts, capacity accounting, all-or-nothing multi-block allocation, rollback |
| M2-C09 | [Choosing block size and measuring fragmentation](m2-c09-choosing-block-size-and-measuring-fragmentation.md) | Tokens per block, ceiling-based block counts, internal versus external fragmentation, tail waste, metadata overhead, allocation granularity, block-size tradeoffs |
| M2-C11 | [Reference counting and shared block ownership](m2-c11-reference-counting-and-shared-block-ownership.md) | Multiple owners, request references versus cache references, retain and release rules, reference-count invariants, zero-reference eligibility, in-flight pins |
| M2-C12 | [Copy-on-write for branching requests](m2-c12-copy-on-write-for-branching-requests.md) | Immutable shared blocks, divergent continuations, partially filled blocks, private writable tails, copying costs, ownership transfer, failure-safe copy-on-write |
| M2-C13 | [Prefix reuse and cache identity](m2-c13-prefix-reuse-and-cache-identity.md) | Exact token-prefix matching, block-granular reuse, prefix indexes, model and adapter identity, position and mask compatibility, dtype and layout compatibility, collision checks, isolation boundaries |
| M2-C14 | [Eviction, retention, and reconstruction](m2-c14-eviction-retention-and-reconstruction.md) | Active versus retained blocks, eviction eligibility, recency and reuse, policy metadata, reference-safe eviction, recomputation cost, exact reconstruction versus lossy state removal |

Follow the complete [Module 2 reading order](../module-2.md) to move between categories.

### Module 3

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M3-C10 | [Host and device buffer placement and lifetime](m3-c10-host-and-device-buffer-placement-and-lifetime.md) | Pageable versus pinned host memory, device allocations, unified addressing versus unified memory, migration and residency, buffer reuse, ownership across transfers, allocation outside timed regions |

Follow the complete [Module 3 reading order](../module-3.md) to move between categories.
