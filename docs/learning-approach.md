# Learning approach

## Starting assumptions

Assume an absolute beginner with basic programming knowledge. Introduce systems, hardware, networking, distributed systems, GPUs, memory, and caching from first principles. Do not assume prior Rust knowledge or fluency in Python.

Rust is the primary programming language for the eventual inference engine. Use Python or C++ when Rust is unsupported, explaining the reason. Chapters provide explanations and experimental procedures without code implementation.

The curriculum consists of Modules 1–7, with Module 9 providing required measurement and correctness support throughout. Module 8 is excluded. The planned module outlines are in place. Develop full chapter content one chapter at a time using the [detailed chapter authoring order](chapter-authoring-order.md). Preserve the 14 top-level categories; place each chapter under its assigned category and connect chapters through the module reading order.

## Chapter structure

Use the [chapter execution plan](chapter-execution-plan.md) as the progress record. Keep at most one chapter active, update its concepts, experiments, verification, and review stages at every stopping point, and mark it complete only after its content review, strict documentation build, and rendered-page review pass.

### Concepts

Progress from foundations to advanced ideas in simple language. Define terms, units, mathematical symbols, and assumptions. Use worked numerical examples, formulas, and illustrative diagrams. Explain specifications before relying on them.

Connect model computation, execution, memory management, and scheduling as they become relevant. Use High-Frequency Trading (HFT) as an engineering lens for critical paths, predictable latency, ownership, overload, and tail behavior. Explain the HFT context and the limits of each analogy; identify the actual inference workload and its constraints.

### Experiments

Every experiment must include these fields:

| Field | Required content |
| --- | --- |
| Name | A specific, identifiable experiment name |
| Description | What will be varied, observed, and compared |
| Purpose/objective | The question or hypothesis being investigated |
| Target concepts | Which chapter concepts the experiment exercises |
| Exit criteria | Observable conditions for completion, including correctness and any justified performance thresholds |

Also state prerequisites, required hardware, workload, baseline, controlled variables, and procedure in prose. Make the HFT, systems engineering, and target-module connections explicit. Require a prediction before measurement and an explanation of the outcome afterward.

### Verification

Provide measurements, benchmark design, and profiling approaches for each experiment. Define reference behavior, invariants, tolerances, pass/fail checks, and failure cases. Explain unfamiliar measurement tools and metrics before asking the reader to use them.

Record hardware specifications, software versions, model and weight identity, workload parameters, warmup, repetition counts, timing boundaries, and sources of uncertainty. Include latency distributions when relevant, with enough observations to support the percentiles claimed. Account for instrumentation overhead.

Evaluate local changes through their effect on the complete request. Label expected outcomes and proposed benchmarks clearly; report results only when measured. Distinguish equivalent implementations from approximations and validate each appropriately.

### Supporting material

Each completed chapter must include formulas, illustrative diagrams, relevant specifications and articles, benchmark designs, validation approaches, and hardware specifications or requirements. Cite primary sources for technical claims. Name versions or commits for implementation-specific behavior. State when a resource or hardware characteristic is irrelevant and explain why.

## Six dimensions

Apply every dimension within each chapter's explanations, experiments, and verification. If a condition lies beyond the chapter's runnable scope, explain it conceptually and identify what a later experiment would need.

| Dimension | Questions to ask |
| --- | --- |
| Semantics and invariants | What must remain true? What counts as correct? |
| Workload and variability | How do lengths, arrivals, modalities, reuse, and skew change behavior? |
| Resources and bottlenecks | What consumes compute, memory, bandwidth, storage, or CPU time? |
| Time and distributions | What lies on the critical path? What causes queueing and tail latency? |
| Ownership and coordination | Who owns the state? When can it move, change, or be reclaimed? |
| Failure and adaptation | What happens under cancellation, stale information, overload, or component loss? |

## Eight engineering principles

These are practical principles rather than mathematical axioms.

1. **Correctness defines the optimization boundary.** Separate equivalent implementations from approximations, and validate each appropriately.
2. **Performance depends on workload and operating point.** An optimization can help one batch size, context length, or concurrency level and hurt another.
3. **Data movement is part of the algorithm.** FLOPs alone cannot explain execution time; placement, layout, and communication matter.
4. **State has ownership, lifetime, and recovery cost.** These determine allocation, caching, persistence, migration, and reclamation.
5. **Dependencies determine latency; bottlenecks determine capacity.** Asynchronous execution hides work only when dependencies and available resources permit overlap.
6. **Variability and synchronization shape the tail.** Average efficiency does not establish p99 behavior, especially with shared queues and collective execution.
7. **Local improvements must be evaluated end to end.** Faster kernels, higher cache hits, or better balance matter only through their effect on useful service.
8. **Claims require reproducible evidence.** Use reference behavior, explicit invariants, representative workloads, fault tests, and clearly defined metrics.

## Completion standard

Each detailed chapter in Modules 1–7 must identify and use the applicable Module 9 reference, correctness, measurement, workload, or validation guidance. Use the [Module 9 support map](module-9.md#support-for-modules-1-7) to select relevant chapters; do not make every Module 9 chapter a prerequisite for every chapter. Introduce the basic checks locally whenever the advanced treatment depends on later capabilities.

An outline establishes scope; it is not a completed chapter. A completed chapter explains its target concepts, specifies experiments without providing implementation code, and defines how to verify the outcomes. All six dimensions and eight principles must be addressed with chapter-specific reasoning.
