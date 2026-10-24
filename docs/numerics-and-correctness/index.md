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

Full content will be developed one chapter at a time.

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
