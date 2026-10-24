# M9-C16: Recording hardware conditions that change measurements

> **Status: Outline — chapter content has not been authored.**

**Module:** Make measurement and correctness part of the foundation

**Category:** [Hardware architecture and topology](index.md)

[Module 9 reading order](../module-9.md) · [Previous: M9-C15](../state-memory-and-caching/m9-c15-accounting-for-weights-kv-state-workspace-and-fragmentation.md) · [Next: M9-C17](../numerics-and-correctness/m9-c17-comparing-logits-with-justified-numerical-tolerances.md)

## Target concepts

CPU and GPU models, memory capacity and bandwidth, NUMA and interconnect topology, clocks, power and thermal limits, co-tenancy and partitions, driver and runtime versions, telemetry sampling.

## Concepts

To be developed from foundations to advanced ideas for a reader with basic programming knowledge and no assumed statistics, profiling, or systems background. Define unfamiliar terms, units, symbols, assumptions, and correctness or measurement boundaries before using them. Include formulas, illustrative diagrams, and relevant specifications. Use Rust as the primary language context, with Python or C++ only when Rust is unsupported. No code implementation will be provided.

## Experiments

To be designed for these target concepts through the lens of LLM serving, systems engineering, and High-Frequency Trading. Each experiment will specify its name, description, purpose/objective, target concepts, and exit criteria, alongside a reference, workload, controlled variables, and hardware requirements. Require a prediction, correctness evidence, and an explanation of observed latency, resource, or quality effects. No code implementation will be included.

## Verification

To be developed alongside the experiments: reference behavior, invariants, correctness checks, measurement, benchmarking, profiling, and end-to-end acceptance criteria. Define timestamp boundaries, units, populations, sample counts, outcome accounting, and uncertainty. Validate instrumentation and account for its overhead. Distinguish equivalent computation, numerical approximation, distributional correctness, and intentional constraints; separate proposed or simulated outcomes from measured evidence.

## Engineering dimensions and principles

Apply all [six dimensions and eight engineering principles](../learning-approach.md) with chapter-specific reasoning. Explain how semantics, workload, resource limits, distributions, ownership, and failure handling affect the evidence, including the scope and limits of HFT analogies.

## Specifications, articles, and hardware

Primary sources, relevant specifications, articles, and hardware details will be selected when this chapter is authored. The [Module 9 sources](../module-9.md#sources) provide starting points. Record model, tokenizer, adapter, precision, cache state, workload, CPU/GPU and interconnect specifications, software versions, tools, and measurement boundaries as applicable.
