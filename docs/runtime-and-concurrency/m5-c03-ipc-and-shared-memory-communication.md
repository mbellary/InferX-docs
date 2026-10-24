# M5-C03: IPC and shared-memory communication

> **Status: Outline — chapter content has not been authored.**

**Module:** Learn scheduling, operating systems, and queueing theory

**Category:** [Runtime and concurrency](index.md)

[Module 5 reading order](../module-5.md) · [Previous: M5-C02](../runtime-and-concurrency/m5-c02-processes-threads-and-operating-system-scheduling.md) · [Next: M5-C04](../runtime-and-concurrency/m5-c04-producer-consumer-queues-and-bounded-work.md)

## Target concepts

Inter-process communication, pipes, sockets and channels, serialization and copying, shared-memory regions, visibility, synchronization, ownership across process boundaries, worker failure.

## Concepts

To be developed from foundations to advanced ideas for a reader with basic programming knowledge and no assumed operating-system, concurrency, or queueing background. Define unfamiliar terms, units, symbols, and assumptions before using them. Include formulas, illustrative diagrams, and specifications relevant to the target concepts above. Use Rust as the primary language context, with Python or C++ only when Rust is unsupported. No code implementation will be provided.

## Experiments

To be designed for these target concepts through the lens of LLM serving, systems engineering, and High-Frequency Trading. Each experiment will specify its name, description, purpose/objective, target concepts, and exit criteria, alongside a baseline, workload, controlled variables, and hardware requirements. Use matched arrival traces and resource limits when comparing policies. Explain critical paths, queueing, ownership, future cache growth, and bounded work where relevant. No code implementation will be included.

## Verification

To be developed alongside the experiments: reference behavior, invariants, correctness checks, measurement, benchmarking, profiling, and end-to-end acceptance criteria. Define populations and timestamp boundaries; account for offered, admitted, completed, rejected, cancelled, and unfinished requests. Validate request identity, legal state transitions, resource lifetimes, and capacity reservations where relevant. State workload and hardware assumptions; distinguish simulated estimates and predictions from measured results.

## Engineering dimensions and principles

Apply all [six dimensions and eight engineering principles](../learning-approach.md) with chapter-specific reasoning. Explain the connections to semantics, arrivals, resource budgets, latency distributions, ownership, coordination, overload, and failures, including the scope and limits of HFT analogies.

## Specifications, articles, and hardware

Primary sources, relevant specifications, articles, and hardware details will be selected when this chapter is authored. The [Module 5 sources](../module-5.md#sources) provide starting points. Record CPU and GPU specifications, operating system, execution topology, runtime versions, and measurement tools when relevant. CPU-side simulation can validate policy logic but cannot establish hardware serving performance.
