# M1-C17: Reusing attention state with a KV cache

> **Status: Outline — chapter content has not been authored.**

**Module:** Understand exactly what happens when an LLM generates a token

**Category:** [State, memory, and caching](index.md)

[Module 1 reading order](../module-1.md) · [Previous: M1-C16](../interfaces-protocols-and-streaming/m1-c16-building-the-single-request-generation-loop.md) · [Next: M1-C18](../runtime-and-concurrency/m1-c18-understanding-prefill-and-decode.md)

## Target concepts

Repeated computation without caching, per-layer keys and values, cache shapes, appending state, cache growth, position offsets, cached causal masking.

## Concepts

To be developed from foundations to advanced ideas for a reader with basic programming knowledge. Define unfamiliar terms and notation before using them. Include formulas with explained symbols, illustrative diagrams, and relevant specifications.

## Experiments

To be designed specifically for these target concepts through the lens of LLM inference, systems engineering, and High-Frequency Trading. Each experiment will state its name, description, purpose/objective, target concepts, and exit criteria. No code implementation will be included.

## Verification

To be developed alongside the experiments: reference behavior, correctness checks, measurements, benchmarks, profiling, and end-to-end acceptance criteria. State workload assumptions and hardware specifications; distinguish proposed measurements from observed results.

## Engineering dimensions and principles

Apply all [six dimensions and eight engineering principles](../learning-approach.md) to the concepts, experiments, and verification in this chapter. Explain each connection in beginner-friendly terms.

## Specifications, articles, and hardware

Primary sources, relevant specifications, articles, and hardware details will be selected when this chapter is authored. Hardware-dependent claims must identify the relevant configuration and assumptions.
