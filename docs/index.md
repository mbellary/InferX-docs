# LLM inference and serving engines

InferX is a growing collection of learning modules about the computation and systems that turn a language model into a serving engine.

Follow a request from input processing and model execution to scheduling, distributed state, streamed results, and production operations. Each chapter will connect its concepts to decisions an inference engine makes and the evidence needed to evaluate them.

## Start learning

Begin with [Module 1: Understand exactly what happens when an LLM generates a token](module-1.md). Its reading order connects chapters across categories. Read the [learning approach](learning-approach.md) for the beginner assumptions and chapter requirements.

## Explore the curriculum

The 14 categories below define the curriculum. Category overviews and the 20 chapter outlines for Module 1 are available. Full chapters will be developed one at a time.

| # | Category | Central question | Includes |
| --- | --- | --- | --- |
| 1 | [Model computation and semantics](model-computation-and-semantics/index.md) | What computation produces a correct output? | Transformers, attention, MoE, multimodal encoders, positional encoding, sampling |
| 2 | [Numerics and correctness](numerics-and-correctness/index.md) | Which transformations preserve behavior, and which introduce approximation? | Precision, quantization, numerical stability, determinism, batch invariance, quality validation |
| 3 | [Hardware architecture and topology](hardware-architecture-and-topology/index.md) | What resources execute the work, and how are they connected? | CPUs, GPUs/NPUs, memory hierarchy, NUMA, PCIe, NVLink, NIC placement |
| 4 | [Kernels, compilers, and execution](kernels-compilers-and-execution/index.md) | How is computation mapped efficiently onto hardware? | GEMMs, attention kernels, tiling, fusion, layouts, compilation, graph replay |
| 5 | [State, memory, and caching](state-memory-and-caching/index.md) | What must be retained, shared, fetched, or reconstructed? | KV allocation, paging, prefix reuse, window state, snapshots, eviction, replay |
| 6 | [Runtime and concurrency](runtime-and-concurrency/index.md) | How do concurrent operations progress without violating dependencies? | Processes, threads, async execution, synchronization, ownership, buffer lifetimes, CPU/device overlap |
| 7 | [Scheduling and queueing](scheduling-and-queueing/index.md) | Which work runs next, with what budget? | Continuous batching, chunked prefill, priorities, fairness, admission, backpressure, queueing theory |
| 8 | [Parallelism and decomposition](parallelism-and-decomposition/index.md) | How is computation divided across devices and stages? | DP, TP, PP, EP, CP, encoder/prefill/decode separation |
| 9 | [Networking and communication](networking-and-communication/index.md) | How does data move between execution domains? | Collectives, dispatch/combine, RPC transport, RDMA, transfer completion, congestion, overlap |
| 10 | [Distributed coordination and routing](distributed-coordination-and-routing/index.md) | How do independent workers cooperate using incomplete information? | Discovery, membership, placement, load balancing, reservations, consistency, stale telemetry |
| 11 | [Storage and persistence](storage-and-persistence/index.md) | What survives beyond a worker’s memory or lifetime? | Shared block storage, metadata indexes, durability, replication, erasure coding, retention, GC |
| 12 | [Interfaces, protocols, and streaming](interfaces-protocols-and-streaming/index.md) | How are user requests translated into computation and results? | API contracts, templates, tokenization, control-token identity, incremental parsing, structured outputs |
| 13 | [Reliability and capacity control](reliability-and-capacity-control/index.md) | How does service continue through overload, failures, and changing demand? | Timeouts, retries, draining, migration, failure domains, autoscaling, headroom |
| 14 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | How do we establish correctness, explain performance, and assess cost? | Profiling, benchmarks, p50/p99, goodput, workload design, statistical uncertainty, cost and energy |

## How to use the modules

Choose a category using the navigation or the table above. The categories are topic boundaries, rather than a mandatory reading order. Each future chapter should state its prerequisites and link to related concepts across categories.

Modules will pair a concrete serving problem with a conceptual explanation, an engine walkthrough, tradeoffs, and a small experiment or exercise. Correctness conditions and measurement assumptions should accompany performance claims.
