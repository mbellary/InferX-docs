# Numerics and correctness

> **Central question:** Which transformations preserve behavior, and which introduce approximation?

This category examines numerics and correctness through the lens of LLM inference and serving engines.

## Scope

Precision, quantization, numerical stability, determinism, batch invariance, quality validation.

## Learning objectives

- Distinguish semantic equivalence from numerical approximation.
- Design quality checks for precision changes and quantized execution.
- Explain why determinism and batch invariance require explicit validation.

## Chapters

[M1-C06](m1-c06-reductions-probabilities-and-stable-softmax.md), [M1-C07](m1-c07-floating-point-arithmetic-and-numerical-correctness.md), [M1-C19](m1-c19-validating-cached-and-uncached-generation.md), [M9-C01](m9-c01-defining-reference-behavior-and-evidence-before-optimizing.md), [M9-C17](m9-c17-comparing-logits-with-justified-numerical-tolerances.md) and [M2-C20](m2-c20-validating-allocator-and-cache-safety.md) are completed detailed chapters; the other chapters in this category remain outlines. Full content is developed one chapter at a time using the [execution plan](../chapter-execution-plan.md).

### Module 1

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M1-C06 | [Reductions, probabilities, and stable softmax](m1-c06-reductions-probabilities-and-stable-softmax.md) | Sums, means, maxima, reduction axes, probability distributions, exponentials, softmax, overflow, underflow, subtracting the maximum |
| M1-C07 | [Floating-point arithmetic and numerical correctness](m1-c07-floating-point-arithmetic-and-numerical-correctness.md) | Floating-point representation, FP32, FP16, BF16, representable range, precision, rounding error, accumulation precision, comparison tolerances |
| M1-C19 | [Validating cached and uncached generation](m1-c19-validating-cached-and-uncached-generation.md) | Full-prefix reference execution, matching next-token logits, numerical tolerances, greedy output comparison, cache lengths, position and masking errors, edge cases |

Follow the complete [Module 1 reading order](../module-1.md) to move between categories.

### Module 2

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M2-C20 | [Validating allocator and cache safety](m2-c20-validating-allocator-and-cache-safety.md) | Reference state model, free-live-retained-pinned accounting, live-reference validity, shared-data immutability, randomized lifecycle traces, stale-handle detection, fault injection, cached-logit equivalence |

Follow the complete [Module 2 reading order](../module-2.md) to move between categories.

### Module 3

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M3-C18 | [Validating GPU computation and memory movement](m3-c18-validating-gpu-computation-and-memory-movement.md) | Reference GEMV and GEMM outputs, accumulation precision, absolute and relative tolerances, reduction-order differences, transfer integrity, shape and stride checks, race and lifetime faults |

Follow the complete [Module 3 reading order](../module-3.md) to move between categories.

### Module 4

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M4-C07 | [Online softmax and stable incremental reductions](m4-c07-online-softmax-and-stable-incremental-reductions.md) | Running maximum, rescaled exponential sums, mergeable reduction state, chunked processing, online weighted sums, masking, numerical stability, equivalence within tolerance |
| M4-C19 | [Randomness, reproducibility, and sampling equivalence](m4-c19-randomness-reproducibility-and-sampling-equivalence.md) | Seed and random-stream ownership, per-request RNG state, draw ordering, counter mapping, deterministic replay conditions, distributional versus token-wise equivalence, statistical uncertainty |
| M4-C20 | [Validating fused kernels and graph replay](m4-c20-validating-fused-kernels-and-graph-replay.md) | Reference comparisons, tolerances, extreme inputs, awkward shapes, strides, masks, aliasing, uninitialized reads, races, stale buffers, graph-versus-eager equivalence, supported input contracts |

Follow the complete [Module 4 reading order](../module-4.md) to move between categories.

### Module 5

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M5-C23 | [Validating scheduling and memory invariants](m5-c23-validating-scheduling-and-memory-invariants.md) | No lost or duplicate work, legal state transitions, request-token identity, future-growth budget invariants, live KV references, cancellation safety, fairness checks, per-request RNG state, batch-dependent numerical tolerances |

Follow the complete [Module 5 reading order](../module-5.md) to move between categories.

### Module 6

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M6-C01 | [Defining an optimization’s correctness and cost contract](m6-c01-defining-an-optimization-s-correctness-and-cost-contract.md) | Mechanism, semantic equivalence, numerical approximation, intentional output constraints, reference behavior, resource savings, added overhead, failure cases, workload-dependent benefit |
| M6-C08 | [Quantization fundamentals: scales, zero points, and rounding](m6-c08-quantization-fundamentals-scales-zero-points-and-rounding.md) | Representable ranges, integer and floating low-bit formats, scale factors, zero points, symmetric and asymmetric schemes, clipping, rounding, dequantization, approximation error |
| M6-C09 | [Weight quantization and grouping granularity](m6-c09-weight-quantization-and-grouping-granularity.md) | Weight-only versus weight-and-activation quantization, per-tensor and per-channel scales, groups, outliers, group-size tradeoffs, metadata bytes, accumulation precision, model-format compatibility |
| M6-C10 | [Calibration and representative data selection](m6-c10-calibration-and-representative-data-selection.md) | Calibration objectives, activation statistics, clipping and scale selection, distribution shift, representative prompts, held-out evaluation, calibration leakage, reproducibility |
| M6-C12 | [KV-cache quantization and attention numerics](m6-c12-kv-cache-quantization-and-attention-numerics.md) | Key versus value distributions, per-token and per-channel scales, cache writes and reads, residual high-precision regions, long-context error, metadata and conversion costs, cache identity |
| M6-C13 | [Validating quantization quality and memory savings](m6-c13-validating-quantization-quality-and-memory-savings.md) | Floating-reference comparisons, layer and logit errors, perplexity and task quality, long-context evaluation, quality thresholds, held-out workloads, actual allocation accounting, failure cases |
| M6-C15 | [Distribution-preserving speculative acceptance](m6-c15-distribution-preserving-speculative-acceptance.md) | Target and proposal probabilities, acceptance ratios, sequential acceptance, first rejection, positive-part residual distribution, all-accepted bonus sampling, support edge cases, greedy versus stochastic contracts |

Follow the complete [Module 6 reading order](../module-6.md) to move between categories.

### Module 7

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M7-C27 | [Validating distributed computation and state](m7-c27-validating-distributed-computation-and-state.md) | Single-device reference outputs, reduction tolerances, rank and shard reconstruction, token and expert routing identity, causal masks, KV consistency, cancellation and fault tests, RNG ownership |

Follow the complete [Module 7 reading order](../module-7.md) to move between categories.

### Module 9

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M9-C01 | [Defining reference behavior and evidence before optimizing](m9-c01-defining-reference-behavior-and-evidence-before-optimizing.md) | Correctness contracts, mathematical and numerical references, invariants, approximations, intentional constraints, falsifiable hypotheses, acceptance criteria, limits of generated-text matching |
| M9-C17 | [Comparing logits with justified numerical tolerances](m9-c17-comparing-logits-with-justified-numerical-tolerances.md) | Reference precision, absolute and relative error, near-zero behavior, per-position and aggregate errors, dtype and reduction effects, extreme values, tolerance justification, locating first divergence |
| M9-C18 | [Testing sampling distributions and random-state behavior](m9-c18-testing-sampling-distributions-and-random-state-behavior.md) | Greedy versus stochastic contracts, seeds and per-request RNG ownership, empirical probabilities, support checks, goodness-of-fit and uncertainty, distribution versus token-sequence equivalence, speculative acceptance |
| M9-C20 | [Validating KV reuse and prefix-cache identity](m9-c20-validating-kv-reuse-and-prefix-cache-identity.md) | Cached versus uncached references, model and adapter identity, positions and masks, partial and full-prefix hits, copy-on-write, eviction, cache-format changes |
| M9-C23 | [Testing batch, schedule, and graph invariance](m9-c23-testing-batch-schedule-and-graph-invariance.md) | Request isolation, batch permutation, varying concurrency, chunked prefill, preemption and resumption, graph versus eager execution, state reset, justified floating-point differences, RNG independence |
| M9-C24 | [Validating approximate and constrained optimization paths](m9-c24-validating-approximate-and-constrained-optimization-paths.md) | Weight and KV quantization quality, held-out evaluation, long-context effects, speculative target distributions, grammar validity, adapter-specific references, capability guards, equivalent fallback versus explicit error |
| M9-C25 | [Validating the text-generation serving pipeline end to end](m9-c25-validating-the-text-generation-serving-pipeline-end-to-end.md) | Tokenizer and template identity, prompt preparation, prefill and decode, cache and scheduler integration, request-token identity, streamed output and stopping, single-GPU and multi-GPU reference comparisons, invalid inputs, terminal-state and resource-cleanup checks |

Follow the complete [Module 9 reading order](../module-9.md) to move between categories.
