# M6-C17: When speculative decoding helps or hurts

> **Status: Outline — chapter content has not been authored.**

**Module:** Study optimizations as explicit tradeoffs

**Category:** [Measurement, experimentation, and economics](index.md)

[Module 6 reading order](../module-6.md) · [Previous: M6-C16](../runtime-and-concurrency/m6-c16-managing-draft-and-target-state-during-speculation.md) · [Next: M6-C18](../interfaces-protocols-and-streaming/m6-c18-grammar-constrained-decoding-from-tokens-to-parser-state.md)

## Target concepts

Draft cost, target verification cost, acceptance rate and accepted length, useful output tokens, proposal length, batch and context effects, shared-resource contention, extra memory, break-even workloads.

## Concepts

To be developed from foundations to advanced ideas for a reader with basic programming knowledge. Define unfamiliar terms, units, symbols, and assumptions before using them. Explain the mechanism, correctness conditions, resource costs, and failure cases for these target concepts. Include formulas, illustrative diagrams, and relevant specifications. Use Rust as the primary language context, with Python or C++ only when Rust is unsupported. No code implementation will be provided.

## Experiments

To be designed for these target concepts through the lens of LLM serving optimizations, systems engineering, and High-Frequency Trading. Each experiment will specify its name, description, purpose/objective, target concepts, and exit criteria, alongside a baseline, workload, controlled variables, and hardware requirements. Compare workloads where the change helps and hurts; preserve the prefix-caching-first build sequence. No code implementation will be included.

## Verification

To be developed alongside the experiments: reference behavior, invariants, correctness and quality checks, measurement, benchmarking, profiling, and end-to-end acceptance criteria. Distinguish computation-equivalent reuse, numerical approximation, distributional equivalence, and intentional grammar constraints. Evaluate ownership, cancellation, fallback, and workload variability where relevant. State resource and hardware assumptions; distinguish predictions from measured results.

## Engineering dimensions and principles

Apply all [six dimensions and eight engineering principles](../learning-approach.md) with chapter-specific reasoning. Explain the connections to semantics, workload, resource bottlenecks, latency distributions, state ownership, and failure adaptation, including the scope and limits of HFT analogies.

## Specifications, articles, and hardware

Primary sources, relevant specifications, articles, and hardware details will be selected when this chapter is authored. The [Module 6 sources](../module-6.md#sources) provide starting points. Record model, adapter, tokenizer, quantization format, compiler/runtime, device, and configuration identities when relevant. Hardware-dependent speedups require measurements on the stated configuration.
