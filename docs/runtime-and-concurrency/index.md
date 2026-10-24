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
