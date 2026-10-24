# Runtime and concurrency

> **Central question:** How do concurrent operations progress without violating dependencies?

This category examines runtime and concurrency through the lens of LLM inference and serving engines.

## Scope

Processes, threads, async execution, synchronization, ownership, buffer lifetimes, CPU/device overlap.

## Learning objectives

- Trace dependencies across host and device execution.
- Explain synchronization and buffer ownership in concurrent request processing.
- Identify opportunities for overlap without violating lifetimes.

## Chapters

Full content will be developed one chapter at a time.

### Module 1

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M1-C18 | [Understanding prefill and decode](m1-c18-understanding-prefill-and-decode.md) | Prompt processing, first-token selection, subsequent decode steps, phase-specific tensor shapes, cache reads and writes, context-length and batch-size effects |

Follow the complete [Module 1 reading order](../module-1.md) to move between categories.

### Module 2

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M2-C10 | [Request state transitions and safe block reuse](m2-c10-request-state-transitions-and-safe-block-reuse.md) | Allocate-write-read-release lifecycle, exclusive mutation, host and device readers, in-flight work, completion versus submission, pinning, deferred reclamation |
| M2-C19 | [Connecting block allocation to the request generator](m2-c19-connecting-block-allocation-to-the-request-generator.md) | Request-owned block tables, prefill writes, decode appends, block-boundary growth, full attention versus retained windows, cache-reader interface, completion and cancellation integration |

Follow the complete [Module 2 reading order](../module-2.md) to move between categories.

### Module 3

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M3-C11 | [Streams, events, and dependency ordering](m3-c11-streams-events-and-dependency-ordering.md) | Asynchronous submission versus completion, stream ordering, cross-stream events, default-stream semantics, synchronization scope, producer-consumer dependencies, safe buffer reuse |
| M3-C12 | [Asynchronous copies and useful overlap](m3-c12-asynchronous-copies-and-useful-overlap.md) | Copy engines, pinned-memory requirements, double buffering, copy-compute overlap, independence and resource constraints, backpressure, cancellation with in-flight work, asynchronous error observation |

Follow the complete [Module 3 reading order](../module-3.md) to move between categories.

### Module 4

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M4-C13 | [Tracing CPU-to-GPU launch overhead](m4-c13-tracing-cpu-to-gpu-launch-overhead.md) | Host dispatch, language and runtime boundaries, driver submission, launch latency, device scheduling, small-kernel overhead, kernel execution versus request time |
| M4-C14 | [CPU-GPU synchronization and hidden serialization](m4-c14-cpu-gpu-synchronization-and-hidden-serialization.md) | Host waits, stream and event dependencies, device-to-host results, implicit synchronization, critical paths, unnecessary barriers, safe asynchronous buffer ownership |
| M4-C16 | [Replay constraints, graph variants, and buffer lifetimes](m4-c16-replay-constraints-graph-variants-and-buffer-lifetimes.md) | Captured parameters and addresses, buffer stability, supported graph updates, changing shapes and batch sizes, graph variants, warmup, memory-pool ownership, invalidation, cancellation and safe fallback |
| M4-C23 | [Integrating a fused kernel into the generator](m4-c23-integrating-a-fused-kernel-into-the-generator.md) | Rust host boundary, backend capability checks, kernel dispatch contracts, stream compatibility, buffer lifetimes, RNG ownership, graph integration, correct fallback and failure propagation |

Follow the complete [Module 4 reading order](../module-4.md) to move between categories.
