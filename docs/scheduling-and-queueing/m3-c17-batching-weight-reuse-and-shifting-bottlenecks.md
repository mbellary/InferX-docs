# M3-C17: Batching, weight reuse, and shifting bottlenecks

> **Status: Outline — chapter content has not been authored.**

**Module:** Learn GPU architecture through data movement

**Category:** [Scheduling and queueing](index.md)

[Module 3 reading order](../module-3.md) · [Previous: M3-C16](../measurement-experimentation-and-economics/m3-c16-using-the-roofline-model-to-predict-bottlenecks.md) · [Next: M3-C18](../numerics-and-correctness/m3-c18-validating-gpu-computation-and-memory-movement.md)

## Target concepts

Batch size and matrix shapes, weight reuse, arithmetic intensity changes, prefill versus decode tendencies, working-set limits, saturation, batching delay versus service time.

## Concepts

To be developed from foundations to advanced ideas for a reader with basic programming knowledge and no assumed hardware or GPU background. Define unfamiliar terms, units, and notation before using them. Include formulas, illustrative diagrams, and specifications relevant to the target concepts above. Use Rust as the primary language context, with Python or C++ when Rust is unsupported, without providing code implementation.

## Experiments

To be designed for these target concepts through the lens of LLM tensor movement, systems engineering, and High-Frequency Trading. Each experiment will specify its name, description, purpose/objective, target concepts, and exit criteria, alongside a baseline, workload, controlled variables, and required hardware. No code implementation will be included.

## Verification

To be developed alongside the experiments: reference behavior, invariants, correctness checks, measurements, benchmarking, profiling, and end-to-end acceptance criteria. Define memory-traffic and timing boundaries, account for asynchronous completion, and validate data and buffer lifetimes where relevant. State workload, device capabilities, and hardware assumptions; distinguish predicted outcomes from measured results.

## Engineering dimensions and principles

Apply all [six dimensions and eight engineering principles](../learning-approach.md) with chapter-specific reasoning. Explain the connections to tensor placement, data movement, dependencies, capacity, and latency, including the scope and limits of HFT analogies.

## Specifications, articles, and hardware

Primary sources, relevant specifications, articles, and hardware details will be selected when this chapter is authored. The [Module 3 sources](../module-3.md#sources) provide starting points. Hardware-dependent claims must identify the relevant configuration, architecture, and assumptions. Separate baseline single-GPU requirements from optional multi-device or network hardware.
