# Module 5: Learn scheduling, operating systems, and queueing theory

> **Status: Chapter outlines available.** Full chapters will be developed one at a time after the module outlines are in place.

## Learning goal

Understand how a serving framework selects work for an executor: which requests enter a batch, when they run, and how much compute and memory they may consume. Build toward a scheduler for mixed prompt and output lengths, comparing static batching, continuous batching, and chunked prefill under the same arrival trace.

## Prerequisites and scope

Use [Module 1](module-1.md) for token generation and prefill/decode, [Module 2](module-2.md) for KV allocation and lifetime, [Module 3](module-3.md) for hardware limits and timing, and [Module 4](module-4.md) for launch, synchronization, and graph constraints. Introduce processes, threads, IPC, shared memory, asynchronous execution, and queueing terms from first principles.

Rust remains the primary language context. Python or C++ is used only when Rust is unsupported. Chapters describe theory and experimental procedures without code implementation. Start with one executor and explicit request-state ownership; distributed routing and multi-worker coordination belong to later modules.

## Scheduling questions to investigate

The executor runs the supplied batch; the scheduler chooses its membership and resource budgets. Continuous batching changes membership between execution iterations. Chunked prefill makes prompt processing resumable, allowing prefill work and active decoding to share an iteration budget. Their latency and throughput effects must be measured for the actual workload.

**Memory planning must account for future KV growth**, not only the next forward pass. Compare conservative reservations, incremental growth with headroom, and explicitly bounded overcommit. Declare an exhaustion policy and account for shared physical blocks, in-flight readers, and preemption costs. Realized output length is unknown to a live scheduler; declared caps and observable progress must be distinguished from benchmark labels.

## Queueing relationship to investigate

**L = λ × W**

L is the mean number of requests inside a defined system boundary, λ is the effective arrival rate into that boundary, and W is the mean time a request spends inside it. Use consistent populations, units, and a stable long-run measurement regime with finite averages. If the boundary is only a waiting queue, use queue occupancy and queue waiting time together.

Little's law relates means; it does not predict p99 latency or, by itself, establish maximum capacity. Rejections, cancellations, unfinished requests, startup, and measurement-window boundaries must be accounted for consistently. See [Little's original paper](https://pubsonline.informs.org/doi/10.1287/opre.9.3.383).

## Reading order

Chapters remain under their assigned top-level categories. Follow this sequence across categories.

| Chapter ID | Category | Chapter name | Target concepts |
| --- | --- | --- | --- |
| M5-C01 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Separating the model executor from the serving scheduler](scheduling-and-queueing/m5-c01-separating-the-model-executor-from-the-serving-scheduler.md) | Execution versus scheduling, request queues, iteration boundaries, batch membership, compute and memory budgets, policy versus mechanism, service objectives |
| M5-C02 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Processes, threads, and operating-system scheduling](runtime-and-concurrency/m5-c02-processes-threads-and-operating-system-scheduling.md) | Address spaces, stacks and heaps, process isolation, threads, context switches, concurrency versus parallelism, CPU scheduling versus request scheduling, Rust execution contexts |
| M5-C03 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [IPC and shared-memory communication](runtime-and-concurrency/m5-c03-ipc-and-shared-memory-communication.md) | Inter-process communication, pipes, sockets and channels, serialization and copying, shared-memory regions, visibility, synchronization, ownership across process boundaries, worker failure |
| M5-C04 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Producer-consumer queues and bounded work](runtime-and-concurrency/m5-c04-producer-consumer-queues-and-bounded-work.md) | Producers and consumers, bounded versus unbounded queues, enqueue and dequeue contracts, FIFO ordering, ownership transfer, blocking and nonblocking behavior, queue capacity |
| M5-C05 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Synchronization, ownership, and resource lifetimes](runtime-and-concurrency/m5-c05-synchronization-ownership-and-resource-lifetimes.md) | Exclusive and shared access, mutexes, atomics and condition variables, Rust ownership and borrowing, contention, deadlock, lost wakeups, request and buffer lifetimes |
| M5-C06 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Asynchronous execution and completion-driven progress](runtime-and-concurrency/m5-c06-asynchronous-execution-and-completion-driven-progress.md) | Tasks and futures, event loops, blocking versus asynchronous work, completion notifications, host-device dependencies, in-flight batches, single-owner scheduler state, safe reclamation |
| M5-C07 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Describing mixed serving workloads and arrival traces](measurement-experimentation-and-economics/m5-c07-describing-mixed-serving-workloads-and-arrival-traces.md) | Prompt and output lengths, declared output caps versus realized lengths, arrival timestamps, bursts, skew and correlations, reuse, seeds, offered versus admitted load, open-loop versus closed-loop traffic |
| M5-C08 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Queueing delay, service time, and request latency](scheduling-and-queueing/m5-c08-queueing-delay-service-time-and-request-latency.md) | Arrival, admission, first service, first token and completion timestamps, queue versus system boundaries, waiting versus service time, head-of-line blocking, iteration-level interference |
| M5-C09 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Applying Little’s law with consistent boundaries](scheduling-and-queueing/m5-c09-applying-little-s-law-with-consistent-boundaries.md) | Mean requests in system, effective arrival rate, mean residence time, L = lambda times W, queue-only accounting, stable measurement regimes, matched populations, finite-window effects, means versus percentiles |
| M5-C10 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Utilization, variability, and tail latency](scheduling-and-queueing/m5-c10-utilization-variability-and-tail-latency.md) | Service demand, bottleneck utilization, saturation, burstiness, service-time variance, latency distributions, queue growth, simple queueing-model assumptions, limits of fixed-rate models for dynamic batches |
| M5-C11 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Defining a static batching baseline](scheduling-and-queueing/m5-c11-defining-a-static-batching-baseline.md) | Fixed request cohorts, batch formation delay, length mismatch, completion masking, inactive slots, no mid-cohort admission, baseline policy definition, capacity and latency tradeoffs |
| M5-C12 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Continuous batching at execution boundaries](scheduling-and-queueing/m5-c12-continuous-batching-at-execution-boundaries.md) | Iteration-level scheduling, removing completed requests, admitting new work, active-set updates, request identity across reordered batches, decode progress, execution-boundary safety |
| M5-C13 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Budgeting work for each execution iteration](scheduling-and-queueing/m5-c13-budgeting-work-for-each-execution-iteration.md) | Request limits, token budgets, prefill versus decode work, context-dependent costs, sequence limits, kernel and graph shape constraints, batch packing, per-iteration memory checks |
| M5-C14 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Planning for future KV-cache growth](scheduling-and-queueing/m5-c14-planning-for-future-kv-cache-growth.md) | Current versus future cached tokens, declared output limits, conservative reservation, incremental growth, bounded overcommit, headroom, shared physical blocks, unknown future demand, exhaustion policy |
| M5-C15 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Admission control and backpressure](scheduling-and-queueing/m5-c15-admission-control-and-backpressure.md) | Admit-wait-reject decisions, bounded queues, memory-aware admission, upstream backpressure, rejection accounting, capacity reservations, overload thresholds, avoiding admission-growth deadlock |
| M5-C16 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Fairness, priorities, and starvation prevention](scheduling-and-queueing/m5-c16-fairness-priorities-and-starvation-prevention.md) | FIFO and age-based policies, priority classes, request versus token fairness, weighted budgets, starvation, priority inversion, unknown job sizes, avoiding clairvoyant policies |
| M5-C17 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Chunked prefill and resumable prompt processing](scheduling-and-queueing/m5-c17-chunked-prefill-and-resumable-prompt-processing.md) | Splitting prompts into token chunks, partial-prefill state, cache positions, causal dependencies, mixing prefill and decode, semantic equivalence, checkpointing progress within a request |
| M5-C18 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Choosing chunk sizes and balancing prefill with decode](scheduling-and-queueing/m5-c18-choosing-chunk-sizes-and-balancing-prefill-with-decode.md) | Chunk-size budgets, decode interference, time-to-first-token versus inter-token latency, scheduling overhead, throughput tradeoffs, measured cost estimates, workload-dependent tuning |
| M5-C19 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Preemption, resumption, and the cost of lost progress](scheduling-and-queueing/m5-c19-preemption-resumption-and-the-cost-of-lost-progress.md) | Iteration-boundary preemption, victim selection, retained state versus recomputation, optional swap costs, resume semantics, KV reclamation, anti-thrashing rules, bounded starvation |
| M5-C20 | [Reliability and capacity control](reliability-and-capacity-control/index.md) | [Cancellation, deadlines, and worker failure](reliability-and-capacity-control/m5-c20-cancellation-deadlines-and-worker-failure.md) | Queued versus in-flight cancellation, deadline expiry, idempotent terminal transitions, deferred block release, worker error propagation, safe retry boundaries, draining, shutdown, capacity recovery |
| M5-C21 | [Interfaces, protocols, and streaming](interfaces-protocols-and-streaming/index.md) | [Streaming results without unbounded buffering](interfaces-protocols-and-streaming/m5-c21-streaming-results-without-unbounded-buffering.md) | Per-request token ordering, result routing, bounded output queues, slow consumers, output backpressure, disconnect handling, completion delivery, generation versus client-visible timing |
| M5-C22 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Designing the scheduler state machine and executor contract](runtime-and-concurrency/m5-c22-designing-the-scheduler-state-machine-and-executor-contract.md) | Queued, admitted, prefill, decode, preempted and terminal states, event ordering, batch descriptors, completion messages, cache allocator integration, Rust ownership boundaries, failure transitions |
| M5-C23 | [Numerics and correctness](numerics-and-correctness/index.md) | [Validating scheduling and memory invariants](numerics-and-correctness/m5-c23-validating-scheduling-and-memory-invariants.md) | No lost or duplicate work, legal state transitions, request-token identity, future-growth budget invariants, live KV references, cancellation safety, fairness checks, per-request RNG state, batch-dependent numerical tolerances |
| M5-C24 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Comparing scheduling policies on the same arrival trace](measurement-experimentation-and-economics/m5-c24-comparing-scheduling-policies-on-the-same-arrival-trace.md) | Static, continuous and chunked-prefill configurations, fixed arrivals and request contents, identical resource caps, controlled output demand, causal information boundaries, event tracing, warmup and drain, rejection and unfinished-request accounting |
| M5-C25 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Measuring sustainable capacity, fairness, and tail behavior](measurement-experimentation-and-economics/m5-c25-measuring-sustainable-capacity-fairness-and-tail-behavior.md) | Time to first token, inter-token and total latency distributions, SLO definitions, goodput, completed tokens per second, queue depth, KV occupancy, CPU and GPU profiling, offered-load sweeps, coordinated omission, uncertainty, per-class fairness |

## How chapters will be developed

Use the relevant [Module 9 support guidance](module-9.md#support-for-modules-1-7) throughout this module for reference behavior, correctness, measurement, and validation. Create detailed chapters using the [chapter authoring order](chapter-authoring-order.md).

Every chapter follows **Concepts → Experiments → Verification**, applying all [six dimensions and eight engineering principles](learning-approach.md). Connect scheduling choices to systems engineering and High-Frequency Trading concerns such as bounded queues, ownership handoff, critical paths, burst handling, starvation prevention, predictable cleanup, and tail latency. Explain each analogy's limits.

## Planned build and comparison contract

The eventual build serves mixed prompt and output lengths using three defined configurations: fixed-cohort static batching, continuous batching with unchunked prefill, and continuous batching with chunked prefill. Compare identical external arrival timestamps, request contents, resource limits, model settings, and controlled output demand. Record policy-specific rejection and preemption decisions as outcomes rather than changing the offered trace to hide them.

Use the same information available at each simulated or real decision point. Controlled benchmark lengths must not give the scheduler knowledge of future output lengths that a production scheduler would lack. Include queue buildup, warmup, drain or explicit censoring, cancellation, and resource cleanup. Separate scheduler overhead from executor time, kernel time from request latency, and simulator results from hardware measurements.

Success requires correct state transitions and request outputs, no live references to reclaimed KV blocks, bounded resource use under the declared policy, and reproducible comparisons of throughput, latency distributions, and fairness. This module contains outlines only; no scheduler has been implemented and no performance results have been measured.

## Sources

- [The Rust Programming Language: Fearless Concurrency](https://doc.rust-lang.org/book/ch16-00-concurrency.html): threads, ownership, message passing, and shared-state concepts.
- [Linux pthreads manual](https://man7.org/linux/man-pages/man7/pthreads.7.html): process and thread resource relationships.
- [Little: A Proof for the Queuing Formula, L = λW](https://pubsonline.informs.org/doi/10.1287/opre.9.3.383): the foundational queueing relationship.
- [Orca](https://www.usenix.org/conference/osdi22/presentation/yu): iteration-level scheduling for autoregressive serving.
- [Sarathi-Serve](https://arxiv.org/abs/2403.02310): chunked prefill and throughput-latency scheduling tradeoffs.

Record the implementation, source, toolchain, and hardware versions when the chapters are authored.
