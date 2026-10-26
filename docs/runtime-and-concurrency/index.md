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

[M1-C18](m1-c18-understanding-prefill-and-decode.md) and [M2-C10](m2-c10-request-state-transitions-and-safe-block-reuse.md) are completed detailed chapters; the other chapters in this category remain outlines. Full content is developed one chapter at a time using the [execution plan](../chapter-execution-plan.md).

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

### Module 5

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M5-C02 | [Processes, threads, and operating-system scheduling](m5-c02-processes-threads-and-operating-system-scheduling.md) | Address spaces, stacks and heaps, process isolation, threads, context switches, concurrency versus parallelism, CPU scheduling versus request scheduling, Rust execution contexts |
| M5-C03 | [IPC and shared-memory communication](m5-c03-ipc-and-shared-memory-communication.md) | Inter-process communication, pipes, sockets and channels, serialization and copying, shared-memory regions, visibility, synchronization, ownership across process boundaries, worker failure |
| M5-C04 | [Producer-consumer queues and bounded work](m5-c04-producer-consumer-queues-and-bounded-work.md) | Producers and consumers, bounded versus unbounded queues, enqueue and dequeue contracts, FIFO ordering, ownership transfer, blocking and nonblocking behavior, queue capacity |
| M5-C05 | [Synchronization, ownership, and resource lifetimes](m5-c05-synchronization-ownership-and-resource-lifetimes.md) | Exclusive and shared access, mutexes, atomics and condition variables, Rust ownership and borrowing, contention, deadlock, lost wakeups, request and buffer lifetimes |
| M5-C06 | [Asynchronous execution and completion-driven progress](m5-c06-asynchronous-execution-and-completion-driven-progress.md) | Tasks and futures, event loops, blocking versus asynchronous work, completion notifications, host-device dependencies, in-flight batches, single-owner scheduler state, safe reclamation |
| M5-C22 | [Designing the scheduler state machine and executor contract](m5-c22-designing-the-scheduler-state-machine-and-executor-contract.md) | Queued, admitted, prefill, decode, preempted and terminal states, event ordering, batch descriptors, completion messages, cache allocator integration, Rust ownership boundaries, failure transitions |

Follow the complete [Module 5 reading order](../module-5.md) to move between categories.

### Module 6

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M6-C07 | [Integrating prefix caching into prefill and decode](m6-c07-integrating-prefix-caching-into-prefill-and-decode.md) | Lookup and admission, uncached suffix execution, full-prefix hits and next-token logits, last-token boundary handling, publishing reusable state, concurrent lifetime rules, cancellation, correct uncached fallback |
| M6-C16 | [Managing draft and target state during speculation](m6-c16-managing-draft-and-target-state-during-speculation.md) | Separate KV states, tentative versus committed tokens, accepted-prefix commits, rejected-tail rollback, token positions, RNG ownership, EOS and stop boundaries, cancellation, memory budgets |
| M6-C24 | [Composing optimizations without breaking contracts](m6-c24-composing-optimizations-without-breaking-contracts.md) | Prefix caching with adapters and quantized state, constrained speculative distributions, graph and shape compatibility, conversion boundaries, RNG and grammar ownership, interaction tests, incremental feature enablement |
| M6-C27 | [Building prefix caching and one additional optimization](m6-c27-building-prefix-caching-and-one-additional-optimization.md) | Prefix-cache baseline integration, choosing weight or KV quantization, speculation, structured decoding or multi-LoRA, staged validation gates, runtime contracts, feature controls, reproducible configuration, no-code build specification |

Follow the complete [Module 6 reading order](../module-6.md) to move between categories.

### Module 7

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M7-C03 | [Workers, ranks, process groups, and communicators](m7-c03-workers-ranks-process-groups-and-communicators.md) | Worker processes, global and local ranks, device assignment, process groups, communicator membership, initialization and rendezvous, stream ownership, Rust and backend integration boundaries |
| M7-C09 | [Overlapping compute and communication safely](m7-c09-overlapping-compute-and-communication-safely.md) | Dependency graphs, independent work, streams and completion events, buffer lifetimes, shared compute and memory resources, exposed versus hidden communication, stragglers, limits of overlap |
| M7-C28 | [Running a model across two GPUs](m7-c28-running-a-model-across-two-gpus.md) | Supported backend selection, device and rank setup, model and shard compatibility, two-way tensor or pipeline partitioning, weight loading, collective readiness, correctness gates, startup and shutdown contracts |

Follow the complete [Module 7 reading order](../module-7.md) to move between categories.

### Module 9

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M9-C22 | [Verifying ownership and memory safety under concurrency](m9-c22-verifying-ownership-and-memory-safety-under-concurrency.md) | Ownership transfer, shared references, stale handles, use-after-free, double release, races, uninitialized accesses, asynchronous buffer lifetimes, sanitizer scope, allocation conservation, randomized lifecycle traces |

Follow the complete [Module 9 reading order](../module-9.md) to move between categories.
