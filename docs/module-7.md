# Module 7: Learn distributed inference after understanding one GPU

> **Status: Chapter outlines available.** Full chapters will be developed one at a time after the module outlines are in place.

## Learning goal

Explain how computation, weights, requests, and attention state are partitioned across GPUs, and how topology and message size determine communication cost. Build toward running a model across two GPUs, separating compute, communication, waiting, and overlap to explain when an additional GPU helps or hurts latency.

## Prerequisites and scope

Use [Module 1](module-1.md) for model semantics, [Module 2](module-2.md) for state and ownership, [Module 3](module-3.md) for GPU topology and data movement, [Module 4](module-4.md) for execution dependencies, [Module 5](module-5.md) for queueing and scheduling, and [Module 6](module-6.md) for optimization contracts. Introduce ranks, collectives, communication protocols, and distributed coordination from first principles.

Rust remains the primary language context. Python or C++ is used only where Rust is unsupported, with explicit backend and host-language boundaries. Chapter content and experiments contain no implementation code.

The core build requires two compatible GPUs and one supported two-way tensor-parallel or pipeline-parallel model configuration. Start within one host when possible; multi-node transport, expert/context-parallel execution, and prefill-decode disaggregation are later experiments requiring appropriate models, backends, and hardware. The build does not require implementing every strategy at once.

## Parallelism strategies to investigate

| Strategy | What is partitioned | Main concern |
| --- | --- | --- |
| Tensor parallelism | Operations within layers | Frequent collectives, shard shapes, and replicated state |
| Pipeline parallelism | Layers across stages | Activation transfers, stage balance, bubbles, and decode dependencies |
| Data parallelism | Requests across replicas | Routing, load balance, replicated weights, and cache locality |
| Expert parallelism | MoE experts | Dispatch/combine traffic, expert storage, and token imbalance |
| Context parallelism | Sequence-related computation and state | Attention communication, state partitioning, masks, and positions |

For MoE models, distinguish total parameters, active computation, and stored weights. Sparse expert activation does not remove the storage of inactive experts or the communication needed to route tokens. Any capacity or dropping policy that changes which tokens reach their required experts must be evaluated as a semantic change rather than a transparent scheduling optimization.

## Communication and scaling questions

Study AllReduce, AllGather, ReduceScatter, and AllToAll as tensor transformations before measuring their costs. Model a simple transfer as **time ≈ startup latency + bytes / effective bandwidth**; collective costs also depend on algorithm-specific steps and traffic, rank count, topology, concurrency, and imbalance. Validate the assumptions against measured message-size sweeps rather than treating the model as a hardware guarantee.

Compute and communication may overlap, so summing all kernel durations across ranks does not give request elapsed time. Measure the critical path and distinguish total communication activity from the portion exposed on that path.

Prefill-decode disaggregation is studied after these foundations. Its benefit depends on phase demand, pool sizing, cache-transfer volume, format compatibility, network capacity, queueing, and latency objectives. Safe handoff must reserve destination capacity, establish completion, and define when source state may be released.

## Reading order

Chapters remain under their assigned top-level categories. Follow this sequence across categories.

| Chapter ID | Category | Chapter name | Target concepts |
| --- | --- | --- | --- |
| M7-C01 | [Parallelism and decomposition](parallelism-and-decomposition/index.md) | [Why distribute inference across GPUs?](parallelism-and-decomposition/m7-c01-why-distribute-inference-across-gpus.md) | Model fit, aggregate capacity, single-request latency, replicas versus sharding, strong versus weak scaling, communication overhead, two-GPU versus single-GPU goals |
| M7-C02 | [Hardware architecture and topology](hardware-architecture-and-topology/index.md) | [Mapping GPU and network topology before partitioning](hardware-architecture-and-topology/m7-c02-mapping-gpu-and-network-topology-before-partitioning.md) | GPU memory and capability, PCIe and NVLink paths, switches, NUMA placement, NIC affinity, intra-node versus inter-node links, peer access, measured versus advertised bandwidth |
| M7-C03 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Workers, ranks, process groups, and communicators](runtime-and-concurrency/m7-c03-workers-ranks-process-groups-and-communicators.md) | Worker processes, global and local ranks, device assignment, process groups, communicator membership, initialization and rendezvous, stream ownership, Rust and backend integration boundaries |
| M7-C04 | [Networking and communication](networking-and-communication/index.md) | [Point-to-point transfers and communication contracts](networking-and-communication/m7-c04-point-to-point-transfers-and-communication-contracts.md) | Send and receive matching, tensor shapes and dtypes, buffer ownership, asynchronous submission and completion, peer access versus host staging, ordering, backpressure |
| M7-C05 | [Networking and communication](networking-and-communication/index.md) | [Reductions and AllReduce from first principles](networking-and-communication/m7-c05-reductions-and-allreduce-from-first-principles.md) | Elementwise reductions across ranks, sum and maximum, replicated results, collective participation and ordering, shape compatibility, floating-point reduction order |
| M7-C06 | [Networking and communication](networking-and-communication/index.md) | [AllGather and ReduceScatter as layout transformations](networking-and-communication/m7-c06-allgather-and-reducescatter-as-layout-transformations.md) | Sharded and replicated tensors, rank-ordered concatenation, reduce-and-partition semantics, buffer sizes, AllReduce decomposition, divisibility and padding, ownership of output shards |
| M7-C07 | [Networking and communication](networking-and-communication/index.md) | [AllToAll and variable-size token exchange](networking-and-communication/m7-c07-alltoall-and-variable-size-token-exchange.md) | Per-destination partitions, dispatch and combine patterns, send and receive counts, variable-size exchanges, packing and unpacking, permutation metadata, imbalance, backend capability limits |
| M7-C08 | [Networking and communication](networking-and-communication/index.md) | [Modeling communication latency and bandwidth costs](networking-and-communication/m7-c08-modeling-communication-latency-and-bandwidth-costs.md) | Message size, startup latency, effective bandwidth, alpha-beta models, rank count, algorithm-dependent traffic and steps, rings and trees, small versus large messages, topology and contention |
| M7-C09 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Overlapping compute and communication safely](runtime-and-concurrency/m7-c09-overlapping-compute-and-communication-safely.md) | Dependency graphs, independent work, streams and completion events, buffer lifetimes, shared compute and memory resources, exposed versus hidden communication, stragglers, limits of overlap |
| M7-C10 | [Parallelism and decomposition](parallelism-and-decomposition/index.md) | [Tensor parallelism for linear layers](parallelism-and-decomposition/m7-c10-tensor-parallelism-for-linear-layers.md) | Row and column partitioning, weight and activation shards, partial outputs, collective placement, replication, layer boundaries, frequent communication, shape compatibility |
| M7-C11 | [Parallelism and decomposition](parallelism-and-decomposition/index.md) | [Tensor-parallel attention and KV ownership](parallelism-and-decomposition/m7-c11-tensor-parallel-attention-and-kv-ownership.md) | Query and KV head partitioning, MHA and GQA constraints, replicated versus sharded KV state, head-count divisibility, output projection, position and mask consistency, rank-local cache budgets |
| M7-C12 | [Parallelism and decomposition](parallelism-and-decomposition/index.md) | [Pipeline parallelism for inference](parallelism-and-decomposition/m7-c12-pipeline-parallelism-for-inference.md) | Layer partitions, stage interfaces, activation transfers, per-stage KV state, forward-only execution, microbatches, request-token identity, autoregressive feedback dependencies |
| M7-C13 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Pipeline bubbles, stage balance, and scheduling](scheduling-and-queueing/m7-c13-pipeline-bubbles-stage-balance-and-scheduling.md) | Fill and drain, idle slots, stage imbalance, microbatch count and size, decode dependencies, queueing between stages, throughput versus single-request latency, tail effects |
| M7-C14 | [Parallelism and decomposition](parallelism-and-decomposition/index.md) | [Data parallelism across serving replicas](parallelism-and-decomposition/m7-c14-data-parallelism-across-serving-replicas.md) | Request partitioning, replicated model weights, independent worker queues, replica-local KV caches, capacity scaling, single-request limits, shared resource contention |
| M7-C15 | [Distributed coordination and routing](distributed-coordination-and-routing/index.md) | [Routing requests with load and cache locality](distributed-coordination-and-routing/m7-c15-routing-requests-with-load-and-cache-locality.md) | Discovery and membership, replica selection, outstanding work versus request counts, prefix affinity, stale telemetry, reservations, locality versus fairness, overload and retry routing |
| M7-C16 | [Model computation and semantics](model-computation-and-semantics/index.md) | [Mixture-of-experts computation and storage](model-computation-and-semantics/m7-c16-mixture-of-experts-computation-and-storage.md) | Routers and expert selection, top-k expert activation, shared versus routed experts, total parameters, active computation, stored weights, routing weights, sparse-compute limits |
| M7-C17 | [Parallelism and decomposition](parallelism-and-decomposition/index.md) | [Expert parallelism and dispatch-combine execution](parallelism-and-decomposition/m7-c17-expert-parallelism-and-dispatch-combine-execution.md) | Expert placement, token routing, AllToAll dispatch, grouped expert computation, weighted combine, token permutation, expert replication choices, communication and storage costs |
| M7-C18 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Expert imbalance, capacity, and token correctness](scheduling-and-queueing/m7-c18-expert-imbalance-capacity-and-token-correctness.md) | Hot experts, skewed token routing, variable expert batches, straggler ranks, capacity limits, padding, load redistribution costs, token dropping versus model-preserving handling |
| M7-C19 | [Parallelism and decomposition](parallelism-and-decomposition/index.md) | [Context parallelism and distributed attention state](parallelism-and-decomposition/m7-c19-context-parallelism-and-distributed-attention-state.md) | Sequence partitions, query versus KV partitioning, attention communication, ring exchange or partial-output reductions, online-softmax merging, causal masks, positions, prefill versus decode differences |
| M7-C20 | [Parallelism and decomposition](parallelism-and-decomposition/index.md) | [Combining parallelism strategies and placement](parallelism-and-decomposition/m7-c20-combining-parallelism-strategies-and-placement.md) | TP, PP, DP, EP and CP groups, rank mapping, nested partitioning, topology-aware placement, compatible dimensions, replicated versus sharded state, communication domains |
| M7-C21 | [State, memory, and caching](state-memory-and-caching/index.md) | [Distributed weights, KV caches, and memory accounting](state-memory-and-caching/m7-c21-distributed-weights-kv-caches-and-memory-accounting.md) | Shard loading, model and adapter identity, rank-local weights, KV partitions, replicated metadata, communication buffers, workspace peaks, transfer staging, headroom, ownership and reclamation |
| M7-C22 | [Distributed coordination and routing](distributed-coordination-and-routing/index.md) | [Coordinating requests and execution across workers](distributed-coordination-and-routing/m7-c22-coordinating-requests-and-execution-across-workers.md) | Request and iteration IDs, agreed batch membership, control-plane versus data-plane messages, metadata consistency, stale events, epochs, completion aggregation, cancellation propagation |
| M7-C23 | [Reliability and capacity control](reliability-and-capacity-control/index.md) | [Collective failures, timeouts, and recovery boundaries](reliability-and-capacity-control/m7-c23-collective-failures-timeouts-and-recovery-boundaries.md) | Rank mismatch, divergent collective ordering, hung or failed workers, stragglers, asynchronous errors, timeout scopes, coordinated abort, retry boundaries, lost volatile state, safe cleanup |
| M7-C24 | [Parallelism and decomposition](parallelism-and-decomposition/index.md) | [Prefill-decode disaggregation and its tradeoffs](parallelism-and-decomposition/m7-c24-prefill-decode-disaggregation-and-its-tradeoffs.md) | Separate phase workers, compute and memory specialization, interference reduction, extra queues, KV transfer volume, resource split, latency objectives, workload-dependent benefit |
| M7-C25 | [Networking and communication](networking-and-communication/index.md) | [Transferring KV state with a safe handoff](networking-and-communication/m7-c25-transferring-kv-state-with-a-safe-handoff.md) | Source and destination identities, cache format and shard compatibility, block mapping, receiver reservations, bulk transfer and metadata, completion versus submission, ownership commit, cancellation and partial failures |
| M7-C26 | [Distributed coordination and routing](distributed-coordination-and-routing/index.md) | [Balancing disaggregated stages and transfer capacity](distributed-coordination-and-routing/m7-c26-balancing-disaggregated-stages-and-transfer-capacity.md) | Prefill and decode pool sizing, phase-aware routing, KV availability, receiving capacity, bandwidth bottlenecks, reservations, stale telemetry, backpressure, admission and tail-latency objectives |
| M7-C27 | [Numerics and correctness](numerics-and-correctness/index.md) | [Validating distributed computation and state](numerics-and-correctness/m7-c27-validating-distributed-computation-and-state.md) | Single-device reference outputs, reduction tolerances, rank and shard reconstruction, token and expert routing identity, causal masks, KV consistency, cancellation and fault tests, RNG ownership |
| M7-C28 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Running a model across two GPUs](runtime-and-concurrency/m7-c28-running-a-model-across-two-gpus.md) | Supported backend selection, device and rank setup, model and shard compatibility, two-way tensor or pipeline partitioning, weight loading, collective readiness, correctness gates, startup and shutdown contracts |
| M7-C29 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Profiling compute, communication, and waiting](measurement-experimentation-and-economics/m7-c29-profiling-compute-communication-and-waiting.md) | Per-rank timelines, kernel and collective durations, host waits, overlap, exposed communication, critical-path attribution, timestamp correlation, profiler overhead, avoiding double-counted elapsed time |
| M7-C30 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [When adding a GPU reduces latency and when it does not](measurement-experimentation-and-economics/m7-c30-when-adding-a-gpu-reduces-latency-and-when-it-does-not.md) | Matched single-GPU and two-GPU workloads, message-size sweeps, prefill and decode timing, strong and weak scaling, latency distributions, useful throughput, memory capacity, cost, topology, load balance, uncertainty |

## How chapters will be developed

Use the relevant [Module 9 support guidance](module-9.md#support-for-modules-1-7) throughout this module for reference behavior, correctness, measurement, and validation. Create detailed chapters using the [chapter authoring order](chapter-authoring-order.md).

Every chapter follows **Concepts → Experiments → Verification**, applying all [six dimensions and eight engineering principles](learning-approach.md). Connect distributed inference to systems engineering and High-Frequency Trading concerns such as locality, communication startup costs, bounded queues, ownership handoff, synchronization, stragglers, stale information, and tail latency. Explain the limits of each analogy.

## Planned build and validation sequence

1. Record GPU, CPU, interconnect, backend, model, precision, cache, and workload identities. Establish a correct single-GPU reference when the same model fits.
2. Verify collective semantics and tensor layouts with known inputs, then characterize communication across message sizes on the actual topology.
3. Run the model across two GPUs using one supported tensor or pipeline partition. Validate outputs, KV ownership, collective order, and startup/shutdown behavior before benchmarking.
4. Profile prefill and decode separately, correlating rank timelines and separating compute, exposed communication, overlap, and waiting. Account for profiler overhead and timestamp boundaries.
5. Compare the same model and request workload on one and two GPUs when feasible. Evaluate two replicas separately for capacity; do not interpret replica throughput gains as proof of lower single-request service time.
6. Sweep shapes, lengths, batch sizes, and offered load. Report latency distributions, useful throughput, per-device memory, resource cost, and regressions. Label inability to fit a model on one GPU as a capacity result rather than inventing a single-GPU latency speedup.

Training-oriented parallelism papers provide foundational partitioning ideas, but their schedules and performance results must not be transferred directly to forward-only autoregressive serving. This module contains outlines only; no distributed model has been run and no performance results have been measured.

## Sources

- [NCCL collective operations](https://docs.nvidia.com/deeplearning/nccl/user-guide/docs/usage/collectives.html): collective semantics, rank ordering, and participation contracts.
- [NVIDIA NCCL Tests](https://github.com/NVIDIA/nccl-tests): communication benchmarks and metric conventions.
- [Megatron-LM](https://arxiv.org/abs/1909.08053): foundational tensor-parallel partitioning; training results are not inference benchmarks.
- [GPipe](https://arxiv.org/abs/1811.06965): pipeline partitioning and microbatch foundations from training.
- [Switch Transformers](https://arxiv.org/abs/2101.03961): sparse expert activation, routing, and communication concerns.
- [Ring Attention](https://arxiv.org/abs/2310.01889): blockwise sequence distribution and attention communication.
- [DistServe](https://arxiv.org/abs/2401.09670): prefill-decode disaggregation and latency objectives.
- [Mooncake](https://arxiv.org/abs/2407.00079): cache-centric disaggregation, transfers, and scheduling.

Record source revisions, implementation/backend versions, model configuration, and hardware specifications when the chapters are authored.
