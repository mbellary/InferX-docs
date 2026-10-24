# LLM inference and serving engines

InferX is a growing collection of learning modules about the computation and systems that turn a language model into a serving engine.

Follow a request from input processing and model execution to scheduling, distributed state, streamed results, and production operations. Each chapter will connect its concepts to decisions an inference engine makes and the evidence needed to evaluate them.

## Start learning

- [Module 1: Understand exactly what happens when an LLM generates a token](module-1.md)
- [Module 2: Treat the KV cache as a first-class systems problem](module-2.md)
- [Module 3: Learn GPU architecture through data movement](module-3.md)
- [Module 4: Understand kernels and execution overhead](module-4.md)
- [Module 5: Learn scheduling, operating systems, and queueing theory](module-5.md)
- [Module 6: Study optimizations as explicit tradeoffs](module-6.md)
- [Module 7: Learn distributed inference after understanding one GPU](module-7.md)
- [Module 9: Make measurement and correctness part of the foundation](module-9.md)

Module 8 is excluded from the curriculum. Module 9 must support Modules 1–7 throughout, providing the relevant measurement and correctness foundations as each capability is developed. Read the [learning approach](learning-approach.md) for the beginner assumptions and chapter requirements.

## Explore the curriculum

See the [complete chapter outline inventory](chapter-outline-inventory.md) for chapter IDs, categories, chapter names, and target concepts in one table.

Use the [detailed chapter authoring order](chapter-authoring-order.md) to create full chapters with their prerequisites in place, including measurement and correctness chapters from Module 9.

Follow the [chapter execution plan and progress ledger](chapter-execution-plan.md) to create and review one detailed chapter at a time and track its concepts, experiments, verification, and completion evidence.

The 14 categories below define the curriculum. Category overviews and 201 chapter entries across Modules 1–7 and 9 are available. [M1-C01](model-computation-and-semantics/m1-c01-from-a-prompt-to-the-next-token.md), [M1-C02](interfaces-protocols-and-streaming/m1-c02-representing-text-as-tokens.md), [M1-C03](model-computation-and-semantics/m1-c03-numbers-vectors-matrices-and-tensors.md), [M1-C04](model-computation-and-semantics/m1-c04-dot-products-and-matrix-multiplication.md), [M1-C05](state-memory-and-caching/m1-c05-how-tensors-occupy-memory.md), [M1-C06](numerics-and-correctness/m1-c06-reductions-probabilities-and-stable-softmax.md) and [M1-C07](numerics-and-correctness/m1-c07-floating-point-arithmetic-and-numerical-correctness.md) are completed detailed chapters; 194 remain outlines. Full chapters are developed one at a time in the dependency-aware authoring order.

| # | Category | Central question | Includes |
| --- | --- | --- | --- |
| 1 | [Model computation and semantics](model-computation-and-semantics/index.md) | What computation produces a correct output? | Transformers, attention, MoE, positional encoding, sampling |
| 2 | [Numerics and correctness](numerics-and-correctness/index.md) | Which transformations preserve behavior, and which introduce approximation? | Precision, quantization, numerical stability, determinism, batch invariance, quality validation |
| 3 | [Hardware architecture and topology](hardware-architecture-and-topology/index.md) | What resources execute the work, and how are they connected? | CPUs, GPUs/NPUs, memory hierarchy, NUMA, PCIe, NVLink, NIC placement |
| 4 | [Kernels, compilers, and execution](kernels-compilers-and-execution/index.md) | How is computation mapped efficiently onto hardware? | GEMMs, attention kernels, tiling, fusion, layouts, compilation, graph replay |
| 5 | [State, memory, and caching](state-memory-and-caching/index.md) | What must be retained, shared, fetched, or reconstructed? | KV allocation, paging, prefix reuse, window state, snapshots, eviction, replay |
| 6 | [Runtime and concurrency](runtime-and-concurrency/index.md) | How do concurrent operations progress without violating dependencies? | Processes, threads, async execution, synchronization, ownership, buffer lifetimes, CPU/device overlap |
| 7 | [Scheduling and queueing](scheduling-and-queueing/index.md) | Which work runs next, with what budget? | Continuous batching, chunked prefill, priorities, fairness, admission, backpressure, queueing theory |
| 8 | [Parallelism and decomposition](parallelism-and-decomposition/index.md) | How is computation divided across devices and stages? | DP, TP, PP, EP, CP, prefill/decode separation |
| 9 | [Networking and communication](networking-and-communication/index.md) | How does data move between execution domains? | Collectives, dispatch/combine, RPC transport, RDMA, transfer completion, congestion, overlap |
| 10 | [Distributed coordination and routing](distributed-coordination-and-routing/index.md) | How do independent workers cooperate using incomplete information? | Discovery, membership, placement, load balancing, reservations, consistency, stale telemetry |
| 11 | [Storage and persistence](storage-and-persistence/index.md) | What survives beyond a worker’s memory or lifetime? | Shared block storage, metadata indexes, durability, replication, erasure coding, retention, GC |
| 12 | [Interfaces, protocols, and streaming](interfaces-protocols-and-streaming/index.md) | How are user requests translated into computation and results? | API contracts, templates, tokenization, control-token identity, incremental parsing, structured outputs |
| 13 | [Reliability and capacity control](reliability-and-capacity-control/index.md) | How does service continue through overload, failures, and changing demand? | Timeouts, retries, draining, migration, failure domains, autoscaling, headroom |
| 14 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | How do we establish correctness, explain performance, and assess cost? | Profiling, benchmarks, p50/p99, goodput, workload design, statistical uncertainty, cost and energy |

## How to use the modules

Choose a category using the navigation or the table above. The categories are topic boundaries, rather than a mandatory reading order. Each future chapter should state its prerequisites and link to related concepts across categories.

Modules will pair a concrete serving problem with a conceptual explanation, an engine walkthrough, tradeoffs, and a small experiment or exercise. Correctness conditions and measurement assumptions should accompany performance claims.
