# M2-C04: Memory ownership, handles, and lifetimes from first principles

> **Status: Outline — chapter content has not been authored.**

**Module:** Treat the KV cache as a first-class systems problem

**Category:** [State, memory, and caching](index.md)

[Module 2 reading order](../module-2.md) · [Previous: M2-C03](../state-memory-and-caching/m2-c03-calculating-kv-memory-and-request-capacity.md) · [Next: M2-C05](../state-memory-and-caching/m2-c05-contiguous-kv-storage-and-its-limits.md)

## Target concepts

Allocation and reclamation, addresses versus handles, Rust ownership and borrowing concepts, request identity, stale handles, use-after-free, double-free.

## Concepts

To be developed from foundations to advanced ideas for a reader with basic programming knowledge. Define unfamiliar terms, units, and notation before using them. Include formulas, illustrative diagrams, and specifications relevant to the target concepts above. Use Rust as the primary language context without providing code implementation.

## Experiments

To be designed for these target concepts through the lens of KV-cache management, systems engineering, and High-Frequency Trading. Each experiment will specify its name, description, purpose/objective, target concepts, and exit criteria, alongside a baseline, workload, controlled variables, and required hardware. No code implementation will be included.

## Verification

To be developed alongside the experiments: reference behavior, invariants, correctness checks, measurements, benchmarking, profiling, and end-to-end acceptance criteria. Validate block ownership and lifetime where relevant. State workload and hardware assumptions; distinguish predicted outcomes from measured results.

## Engineering dimensions and principles

Apply all [six dimensions and eight engineering principles](../learning-approach.md) with chapter-specific reasoning. Explain the connections to KV-cache correctness, capacity, and latency, including the scope and limits of HFT analogies.

## Specifications, articles, and hardware

Primary sources, relevant specifications, articles, and hardware details will be selected when this chapter is authored. The [Module 2 sources](../module-2.md#sources) provide starting points. Hardware-dependent claims must identify the relevant configuration and assumptions.
