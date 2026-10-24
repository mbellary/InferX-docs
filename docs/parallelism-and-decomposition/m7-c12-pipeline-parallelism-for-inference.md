# M7-C12: Pipeline parallelism for inference

> **Status: Outline — chapter content has not been authored.**

**Module:** Learn distributed inference after understanding one GPU

**Category:** [Parallelism and decomposition](index.md)

[Module 7 reading order](../module-7.md) · [Previous: M7-C11](../parallelism-and-decomposition/m7-c11-tensor-parallel-attention-and-kv-ownership.md) · [Next: M7-C13](../scheduling-and-queueing/m7-c13-pipeline-bubbles-stage-balance-and-scheduling.md)

## Target concepts

Layer partitions, stage interfaces, activation transfers, per-stage KV state, forward-only execution, microbatches, request-token identity, autoregressive feedback dependencies.

## Concepts

To be developed from foundations to advanced ideas for a reader with basic programming knowledge and no assumed distributed-systems or networking background. Define unfamiliar terms, units, symbols, and assumptions before using them. Include formulas, illustrative diagrams, and relevant specifications. Use Rust as the primary language context and explain Python or C++ backend boundaries when Rust is unsupported. No code implementation will be provided.

## Experiments

To be designed for these target concepts through the lens of distributed LLM inference, systems engineering, and High-Frequency Trading. Each experiment will specify its name, description, purpose/objective, target concepts, and exit criteria, alongside a baseline, workload, controlled variables, and hardware requirements. Distinguish baseline two-GPU experiments from optional multi-node extensions. Explain topology, rank ownership, message size, dependencies, and failure handling where relevant. No code implementation will be included.

## Verification

To be developed alongside the experiments: reference behavior, invariants, correctness checks, measurement, benchmarking, profiling, and end-to-end acceptance criteria. Separate model fit, service capacity, and single-request latency; distinguish exposed communication from overlapped work. Validate rank participation, state compatibility, token identity, buffer lifetimes, and cancellation where relevant. State workload and hardware assumptions; distinguish predicted or simulated outcomes from measured results.

## Engineering dimensions and principles

Apply all [six dimensions and eight engineering principles](../learning-approach.md) with chapter-specific reasoning. Explain the connections to semantics, workload variability, resource bottlenecks, critical paths and tails, ownership and coordination, and failure adaptation, including the scope and limits of HFT analogies.

## Specifications, articles, and hardware

Primary sources, relevant specifications, articles, and hardware details will be selected when this chapter is authored. The [Module 7 sources](../module-7.md#sources) provide starting points. Record GPU count and models, interconnect paths, CPU and NIC placement, transport/backend versions, model identity, and parallelism configuration where relevant. A simulated topology cannot establish hardware communication performance.
