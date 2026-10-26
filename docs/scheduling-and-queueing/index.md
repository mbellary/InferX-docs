# Scheduling and queueing

> **Central question:** Which work runs next, with what budget?

This category examines scheduling and queueing through the lens of LLM inference and serving engines.

## Scope

Continuous batching, chunked prefill, priorities, fairness, admission, backpressure, queueing theory.

## Learning objectives

- Reason about prefill and decode scheduling under mixed workloads.
- Compare throughput, latency, and fairness objectives.
- Use admission and backpressure to control queued work.

## Chapters

[M2-C15](m2-c15-admission-and-growth-under-a-finite-kv-budget.md) is a completed detailed chapter; the other chapters in this category remain outlines. Full content is developed one chapter at a time using the [execution plan](../chapter-execution-plan.md).

### Module 2

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M2-C15 | [Admission and growth under a finite KV budget](m2-c15-admission-and-growth-under-a-finite-kv-budget.md) | Free-block budgets, growth reservations, headroom, admit-wait-reject decisions, backpressure, mixed request lengths, fairness, capacity versus latency |

Follow the complete [Module 2 reading order](../module-2.md) to move between categories.

### Module 3

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M3-C17 | [Batching, weight reuse, and shifting bottlenecks](m3-c17-batching-weight-reuse-and-shifting-bottlenecks.md) | Batch size and matrix shapes, weight reuse, arithmetic intensity changes, prefill versus decode tendencies, working-set limits, saturation, batching delay versus service time |

Follow the complete [Module 3 reading order](../module-3.md) to move between categories.

### Module 5

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M5-C01 | [Separating the model executor from the serving scheduler](m5-c01-separating-the-model-executor-from-the-serving-scheduler.md) | Execution versus scheduling, request queues, iteration boundaries, batch membership, compute and memory budgets, policy versus mechanism, service objectives |
| M5-C08 | [Queueing delay, service time, and request latency](m5-c08-queueing-delay-service-time-and-request-latency.md) | Arrival, admission, first service, first token and completion timestamps, queue versus system boundaries, waiting versus service time, head-of-line blocking, iteration-level interference |
| M5-C09 | [Applying Little’s law with consistent boundaries](m5-c09-applying-little-s-law-with-consistent-boundaries.md) | Mean requests in system, effective arrival rate, mean residence time, L = lambda times W, queue-only accounting, stable measurement regimes, matched populations, finite-window effects, means versus percentiles |
| M5-C10 | [Utilization, variability, and tail latency](m5-c10-utilization-variability-and-tail-latency.md) | Service demand, bottleneck utilization, saturation, burstiness, service-time variance, latency distributions, queue growth, simple queueing-model assumptions, limits of fixed-rate models for dynamic batches |
| M5-C11 | [Defining a static batching baseline](m5-c11-defining-a-static-batching-baseline.md) | Fixed request cohorts, batch formation delay, length mismatch, completion masking, inactive slots, no mid-cohort admission, baseline policy definition, capacity and latency tradeoffs |
| M5-C12 | [Continuous batching at execution boundaries](m5-c12-continuous-batching-at-execution-boundaries.md) | Iteration-level scheduling, removing completed requests, admitting new work, active-set updates, request identity across reordered batches, decode progress, execution-boundary safety |
| M5-C13 | [Budgeting work for each execution iteration](m5-c13-budgeting-work-for-each-execution-iteration.md) | Request limits, token budgets, prefill versus decode work, context-dependent costs, sequence limits, kernel and graph shape constraints, batch packing, per-iteration memory checks |
| M5-C14 | [Planning for future KV-cache growth](m5-c14-planning-for-future-kv-cache-growth.md) | Current versus future cached tokens, declared output limits, conservative reservation, incremental growth, bounded overcommit, headroom, shared physical blocks, unknown future demand, exhaustion policy |
| M5-C15 | [Admission control and backpressure](m5-c15-admission-control-and-backpressure.md) | Admit-wait-reject decisions, bounded queues, memory-aware admission, upstream backpressure, rejection accounting, capacity reservations, overload thresholds, avoiding admission-growth deadlock |
| M5-C16 | [Fairness, priorities, and starvation prevention](m5-c16-fairness-priorities-and-starvation-prevention.md) | FIFO and age-based policies, priority classes, request versus token fairness, weighted budgets, starvation, priority inversion, unknown job sizes, avoiding clairvoyant policies |
| M5-C17 | [Chunked prefill and resumable prompt processing](m5-c17-chunked-prefill-and-resumable-prompt-processing.md) | Splitting prompts into token chunks, partial-prefill state, cache positions, causal dependencies, mixing prefill and decode, semantic equivalence, checkpointing progress within a request |
| M5-C18 | [Choosing chunk sizes and balancing prefill with decode](m5-c18-choosing-chunk-sizes-and-balancing-prefill-with-decode.md) | Chunk-size budgets, decode interference, time-to-first-token versus inter-token latency, scheduling overhead, throughput tradeoffs, measured cost estimates, workload-dependent tuning |
| M5-C19 | [Preemption, resumption, and the cost of lost progress](m5-c19-preemption-resumption-and-the-cost-of-lost-progress.md) | Iteration-boundary preemption, victim selection, retained state versus recomputation, optional swap costs, resume semantics, KV reclamation, anti-thrashing rules, bounded starvation |

Follow the complete [Module 5 reading order](../module-5.md) to move between categories.

### Module 6

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M6-C06 | [Balancing cache locality, fairness, and load](m6-c06-balancing-cache-locality-fairness-and-load.md) | Prefix-aware ordering, shared-prefix workloads, reuse skew, starvation prevention, cache affinity, queueing versus saved work, worker-load tradeoffs, limits of local policies |
| M6-C23 | [Batching requests across multiple LoRA adapters](m6-c23-batching-requests-across-multiple-lora-adapters.md) | Adapter selection, heterogeneous ranks, low-rank batched operations, grouping versus mixing, dispatch and padding costs, locality versus fairness, rare adapters, memory-aware admission |

Follow the complete [Module 6 reading order](../module-6.md) to move between categories.

### Module 7

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M7-C13 | [Pipeline bubbles, stage balance, and scheduling](m7-c13-pipeline-bubbles-stage-balance-and-scheduling.md) | Fill and drain, idle slots, stage imbalance, microbatch count and size, decode dependencies, queueing between stages, throughput versus single-request latency, tail effects |
| M7-C18 | [Expert imbalance, capacity, and token correctness](m7-c18-expert-imbalance-capacity-and-token-correctness.md) | Hot experts, skewed token routing, variable expert batches, straggler ranks, capacity limits, padding, load redistribution costs, token dropping versus model-preserving handling |

Follow the complete [Module 7 reading order](../module-7.md) to move between categories.
