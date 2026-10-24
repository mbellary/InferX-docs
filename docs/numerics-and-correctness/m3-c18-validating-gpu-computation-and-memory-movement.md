# M3-C18: Validating GPU computation and memory movement

> **Status: Outline — chapter content has not been authored.**

**Module:** Learn GPU architecture through data movement

**Category:** [Numerics and correctness](index.md)

[Module 3 reading order](../module-3.md) · [Previous: M3-C17](../scheduling-and-queueing/m3-c17-batching-weight-reuse-and-shifting-bottlenecks.md) · [Next: M3-C19](../measurement-experimentation-and-economics/m3-c19-designing-trustworthy-asynchronous-gpu-benchmarks.md)

## Target concepts

Reference GEMV and GEMM outputs, accumulation precision, absolute and relative tolerances, reduction-order differences, transfer integrity, shape and stride checks, race and lifetime faults.

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
