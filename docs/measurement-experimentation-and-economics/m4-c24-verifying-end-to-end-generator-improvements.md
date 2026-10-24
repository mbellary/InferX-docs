# M4-C24: Verifying end-to-end generator improvements

> **Status: Outline — chapter content has not been authored.**

**Module:** Understand kernels and execution overhead

**Category:** [Measurement, experimentation, and economics](index.md)

[Module 4 reading order](../module-4.md) · [Previous: M4-C23](../runtime-and-concurrency/m4-c23-integrating-a-fused-kernel-into-the-generator.md)

## Target concepts

Critical-path attribution, Amdahl-style speedup limits, prefill and decode separation, time to first token, inter-token and total latency, useful throughput, correctness gates, amortization, tail regressions.

## Concepts

To be developed from foundations to advanced ideas for a reader with basic programming knowledge. Define unfamiliar terms, units, symbols, and assumptions before using them. Include formulas, illustrative diagrams, and specifications relevant to the target concepts above. Keep Rust as the primary host-language context and explain the Triton/Python or CUDA/C++ boundary where required. No code implementation will be provided.

## Experiments

To be designed for these target concepts through the lens of LLM inference kernels, systems engineering, and High-Frequency Trading. Each experiment will specify its name, description, purpose/objective, target concepts, and exit criteria, alongside a baseline, workload, controlled variables, and hardware requirements. Explain the critical path, bounded work, resource usage, and ownership where relevant. No code implementation will be included.

## Verification

To be developed alongside the experiments: reference behavior, invariants, numerical checks, measurement, benchmarking, profiling, and end-to-end acceptance criteria. Separate cold-start and steady-state costs, host and device timing, and kernel speedups from generator improvements. Validate dependencies, memory lifetimes, and replay or randomness contracts where relevant. State workload and hardware assumptions; distinguish predictions from measured results.

## Engineering dimensions and principles

Apply all [six dimensions and eight engineering principles](../learning-approach.md) with chapter-specific reasoning. Explain the connections to model behavior, fusion, execution overhead, dependencies, variability, ownership, and failure handling, including the scope and limits of HFT analogies.

## Specifications, articles, and hardware

Primary sources, relevant specifications, articles, and hardware details will be selected when this chapter is authored. The [Module 4 sources](../module-4.md#sources) provide starting points. Record device architecture, compiler and runtime versions, supported numerical formats, and graph or kernel capabilities for hardware-dependent claims.
