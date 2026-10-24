# M3-C11: Streams, events, and dependency ordering

> **Status: Outline — chapter content has not been authored.**

**Module:** Learn GPU architecture through data movement

**Category:** [Runtime and concurrency](index.md)

[Module 3 reading order](../module-3.md) · [Previous: M3-C10](../state-memory-and-caching/m3-c10-host-and-device-buffer-placement-and-lifetime.md) · [Next: M3-C12](../runtime-and-concurrency/m3-c12-asynchronous-copies-and-useful-overlap.md)

## Target concepts

Asynchronous submission versus completion, stream ordering, cross-stream events, default-stream semantics, synchronization scope, producer-consumer dependencies, safe buffer reuse.

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
