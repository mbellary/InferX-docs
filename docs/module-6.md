# Module 6: Study optimizations as explicit tradeoffs

> **Status: Chapter outlines available.** Full chapters will be developed one at a time after the module outlines are in place.

## Learning goal

For each optimization, explain its mechanism, correctness conditions, failure cases, saved resources, added costs, and workload-dependent effects. Build toward prefix caching first, then select one additional optimization and establish the workloads where it helps or hurts the complete serving system.

## Prerequisites and scope

Use [Module 1](module-1.md) for model semantics and sampling, [Module 2](module-2.md) for cache ownership and paging, [Module 3](module-3.md) for data movement and hardware, [Module 4](module-4.md) for kernels and execution, and [Module 5](module-5.md) for scheduling and workload comparisons. Introduce radix trees, quantization, rejection sampling, grammars, and low-rank adaptation from first principles.

Rust remains the primary language context; use Python or C++ only when Rust is unsupported. Chapter content and experiments contain no implementation code. Multi-worker placement is introduced only where it affects correctness or tradeoffs; its full treatment belongs to Module 7. The curriculum covers text-generation serving.

## Optimization contracts to investigate

| Optimization | Mechanism and correctness boundary | Costs and failure cases to evaluate |
| --- | --- | --- |
| Prefix caching / RadixAttention | Radix-tree-based KV reuse for equivalent computation | Lookup and metadata costs, eviction, ownership, stale identity, locality versus fairness and worker load |
| Weight quantization | Low-precision weight representation with explicit approximation | Quality loss, scales and grouping, calibration, packing, dequantization, kernel support |
| KV-cache quantization | Lower-precision cached state with explicit attention-quality validation | Cache metadata, conversion costs, long-context error, capacity versus useful throughput |
| Speculative decoding | Draft proposals verified using a valid acceptance and correction algorithm | Draft and verification costs, acceptance behavior, state rollback, extra memory, stopping and RNG rules |
| Structured decoding | Grammar state restricts legal next-token choices | Compilation and mask overhead, tokenizer compatibility, incomplete output, empty masks, supported schema semantics |
| Multi-LoRA serving | Select and batch adapter-specific low-rank computation over a shared base model | Adapter residency, rank heterogeneity, dispatch overhead, fragmentation of batches, identity and cache compatibility |

Prefix-cache identity must represent equivalent computation: token IDs alone are insufficient when models, adapters, positions, or masks differ. Validate the entire cache contract against uncached reference execution, including full-prefix hits and next-token logits. See the [SGLang paper](https://arxiv.org/abs/2312.07104).

The original speculative-sampling method preserves the target distribution through modified rejection sampling within numerical limits; accepting merely plausible draft tokens is not sufficient. Validation must distinguish target-distribution equivalence from identical random streams or token sequences. See the [speculative-sampling paper](https://arxiv.org/abs/2302.01318).

## Reading order

Chapters remain under their assigned top-level categories. Follow this sequence across categories. The curriculum covers all techniques; the build requires prefix caching plus only one additional optimization.

| Chapter ID | Category | Chapter name | Target concepts |
| --- | --- | --- | --- |
| M6-C01 | [Numerics and correctness](numerics-and-correctness/index.md) | [Defining an optimization’s correctness and cost contract](numerics-and-correctness/m6-c01-defining-an-optimization-s-correctness-and-cost-contract.md) | Mechanism, semantic equivalence, numerical approximation, intentional output constraints, reference behavior, resource savings, added overhead, failure cases, workload-dependent benefit |
| M6-C02 | [State, memory, and caching](state-memory-and-caching/index.md) | [Defining prefix identity through equivalent computation](state-memory-and-caching/m6-c02-defining-prefix-identity-through-equivalent-computation.md) | Token prefixes, model and weight versions, adapters, positions, attention masks, cache precision and layout, isolation namespaces, compatibility checks |
| M6-C03 | [State, memory, and caching](state-memory-and-caching/index.md) | [Tries, radix trees, and longest-prefix matching](state-memory-and-caching/m6-c03-tries-radix-trees-and-longest-prefix-matching.md) | Tree nodes and edges, token paths, path compression, longest-prefix lookup, insertion, edge splitting, lookup cost, metadata overhead, RadixAttention concepts |
| M6-C04 | [State, memory, and caching](state-memory-and-caching/index.md) | [Connecting a radix index to paged KV blocks](state-memory-and-caching/m6-c04-connecting-a-radix-index-to-paged-kv-blocks.md) | Logical prefix ranges, block-granular reuse, partial-block boundaries, tree-to-block mappings, immutable shared prefixes, copy-on-write tails, index and allocator consistency |
| M6-C05 | [State, memory, and caching](state-memory-and-caching/index.md) | [Reference-safe retention, eviction, and cancellation](state-memory-and-caching/m6-c05-reference-safe-retention-eviction-and-cancellation.md) | Request and cache ownership, reference counts, pinning, eviction eligibility, recency policies, memory pressure, cancellation, deferred reclamation, recomputation costs |
| M6-C06 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Balancing cache locality, fairness, and load](scheduling-and-queueing/m6-c06-balancing-cache-locality-fairness-and-load.md) | Prefix-aware ordering, shared-prefix workloads, reuse skew, starvation prevention, cache affinity, queueing versus saved work, worker-load tradeoffs, limits of local policies |
| M6-C07 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Integrating prefix caching into prefill and decode](runtime-and-concurrency/m6-c07-integrating-prefix-caching-into-prefill-and-decode.md) | Lookup and admission, uncached suffix execution, full-prefix hits and next-token logits, last-token boundary handling, publishing reusable state, concurrent lifetime rules, cancellation, correct uncached fallback |
| M6-C08 | [Numerics and correctness](numerics-and-correctness/index.md) | [Quantization fundamentals: scales, zero points, and rounding](numerics-and-correctness/m6-c08-quantization-fundamentals-scales-zero-points-and-rounding.md) | Representable ranges, integer and floating low-bit formats, scale factors, zero points, symmetric and asymmetric schemes, clipping, rounding, dequantization, approximation error |
| M6-C09 | [Numerics and correctness](numerics-and-correctness/index.md) | [Weight quantization and grouping granularity](numerics-and-correctness/m6-c09-weight-quantization-and-grouping-granularity.md) | Weight-only versus weight-and-activation quantization, per-tensor and per-channel scales, groups, outliers, group-size tradeoffs, metadata bytes, accumulation precision, model-format compatibility |
| M6-C10 | [Numerics and correctness](numerics-and-correctness/index.md) | [Calibration and representative data selection](numerics-and-correctness/m6-c10-calibration-and-representative-data-selection.md) | Calibration objectives, activation statistics, clipping and scale selection, distribution shift, representative prompts, held-out evaluation, calibration leakage, reproducibility |
| M6-C11 | [Kernels, compilers, and execution](kernels-compilers-and-execution/index.md) | [Packing, dequantization, and quantized kernel execution](kernels-compilers-and-execution/m6-c11-packing-dequantization-and-quantized-kernel-execution.md) | Bit packing, alignment and padding, group metadata, fused versus separate dequantization, compute paths, hardware support, kernel eligibility, conversion overhead, effective memory savings |
| M6-C12 | [Numerics and correctness](numerics-and-correctness/index.md) | [KV-cache quantization and attention numerics](numerics-and-correctness/m6-c12-kv-cache-quantization-and-attention-numerics.md) | Key versus value distributions, per-token and per-channel scales, cache writes and reads, residual high-precision regions, long-context error, metadata and conversion costs, cache identity |
| M6-C13 | [Numerics and correctness](numerics-and-correctness/index.md) | [Validating quantization quality and memory savings](numerics-and-correctness/m6-c13-validating-quantization-quality-and-memory-savings.md) | Floating-reference comparisons, layer and logit errors, perplexity and task quality, long-context evaluation, quality thresholds, held-out workloads, actual allocation accounting, failure cases |
| M6-C14 | [Model computation and semantics](model-computation-and-semantics/index.md) | [Draft proposals and parallel target verification](model-computation-and-semantics/m6-c14-draft-proposals-and-parallel-target-verification.md) | Draft and target models, proposal length, autoregressive draft generation, causal target scoring, conditional distributions, accepted prefixes, bonus or correction tokens, stopping rules |
| M6-C15 | [Numerics and correctness](numerics-and-correctness/index.md) | [Distribution-preserving speculative acceptance](numerics-and-correctness/m6-c15-distribution-preserving-speculative-acceptance.md) | Target and proposal probabilities, acceptance ratios, sequential acceptance, first rejection, positive-part residual distribution, all-accepted bonus sampling, support edge cases, greedy versus stochastic contracts |
| M6-C16 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Managing draft and target state during speculation](runtime-and-concurrency/m6-c16-managing-draft-and-target-state-during-speculation.md) | Separate KV states, tentative versus committed tokens, accepted-prefix commits, rejected-tail rollback, token positions, RNG ownership, EOS and stop boundaries, cancellation, memory budgets |
| M6-C17 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [When speculative decoding helps or hurts](measurement-experimentation-and-economics/m6-c17-when-speculative-decoding-helps-or-hurts.md) | Draft cost, target verification cost, acceptance rate and accepted length, useful output tokens, proposal length, batch and context effects, shared-resource contention, extra memory, break-even workloads |
| M6-C18 | [Interfaces, protocols, and streaming](interfaces-protocols-and-streaming/index.md) | [Grammar-constrained decoding from tokens to parser state](interfaces-protocols-and-streaming/m6-c18-grammar-constrained-decoding-from-tokens-to-parser-state.md) | Regular versus context-free languages, finite-state machines and parser stacks, token-to-byte transitions, grammar state, valid continuations, accepting states, tokenizer compatibility |
| M6-C19 | [Interfaces, protocols, and streaming](interfaces-protocols-and-streaming/index.md) | [Grammar compilation and vocabulary-mask execution](interfaces-protocols-and-streaming/m6-c19-grammar-compilation-and-vocabulary-mask-execution.md) | Grammar and schema compilation, mask generation, token filtering, mask caching, state advancement, CPU-GPU coordination, preprocessing versus per-token overhead, constraint and sampling order |
| M6-C20 | [Interfaces, protocols, and streaming](interfaces-protocols-and-streaming/index.md) | [Structured-output validity, termination, and failure](interfaces-protocols-and-streaming/m6-c20-structured-output-validity-termination-and-failure.md) | Syntactic validity versus semantic correctness, incomplete outputs, empty allowed-token sets, EOS legality, unsupported schema features, compilation failures, length limits, cancellation, explicit failure contracts |
| M6-C21 | [Model computation and semantics](model-computation-and-semantics/index.md) | [LoRA foundations and adapter-specific computation](model-computation-and-semantics/m6-c21-lora-foundations-and-adapter-specific-computation.md) | Low-rank updates, base weights, adapter matrices, rank and scaling, target layers, merged versus unmerged computation, adapter identity, reference outputs, heterogeneous adapter requests |
| M6-C22 | [State, memory, and caching](state-memory-and-caching/index.md) | [Adapter residency, lifetime, and cache compatibility](state-memory-and-caching/m6-c22-adapter-residency-lifetime-and-cache-compatibility.md) | Adapter loading and residency, host versus device storage, versioned identities, in-flight references, eviction, load failures, adapter-aware KV reuse, memory competition with KV state |
| M6-C23 | [Scheduling and queueing](scheduling-and-queueing/index.md) | [Batching requests across multiple LoRA adapters](scheduling-and-queueing/m6-c23-batching-requests-across-multiple-lora-adapters.md) | Adapter selection, heterogeneous ranks, low-rank batched operations, grouping versus mixing, dispatch and padding costs, locality versus fairness, rare adapters, memory-aware admission |
| M6-C24 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Composing optimizations without breaking contracts](runtime-and-concurrency/m6-c24-composing-optimizations-without-breaking-contracts.md) | Prefix caching with adapters and quantized state, constrained speculative distributions, graph and shape compatibility, conversion boundaries, RNG and grammar ownership, interaction tests, incremental feature enablement |
| M6-C25 | [Reliability and capacity control](reliability-and-capacity-control/index.md) | [Handling unsupported cases and optimization failures](reliability-and-capacity-control/m6-c25-handling-unsupported-cases-and-optimization-failures.md) | Capability checks, invalidated cache identities, missing adapters, grammar errors, allocation failures, safe fallback versus explicit rejection, cancellation, cleanup, bounded recovery costs |
| M6-C26 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Designing the optimization workload and comparison matrix](measurement-experimentation-and-economics/m6-c26-designing-the-optimization-workload-and-comparison-matrix.md) | Prefix reuse and skew, context and output lengths, arrivals and concurrency, precision settings, draft agreement, grammar complexity, adapter mix, fixed resource budgets, cold and warm runs, ablations |
| M6-C27 | [Runtime and concurrency](runtime-and-concurrency/index.md) | [Building prefix caching and one additional optimization](runtime-and-concurrency/m6-c27-building-prefix-caching-and-one-additional-optimization.md) | Prefix-cache baseline integration, choosing weight or KV quantization, speculation, structured decoding or multi-LoRA, staged validation gates, runtime contracts, feature controls, reproducible configuration, no-code build specification |
| M6-C28 | [Measurement, experimentation, and economics](measurement-experimentation-and-economics/index.md) | [Establishing end-to-end benefit and regression boundaries](measurement-experimentation-and-economics/m6-c28-establishing-end-to-end-benefit-and-regression-boundaries.md) | Correctness and quality gates, first-token and inter-token latency, tail distributions, goodput, capacity, CPU and GPU overhead, actual memory, compilation and loading amortization, fairness, cost, uncertainty, helps-versus-hurts results |

## How chapters will be developed

Use the relevant [Module 9 support guidance](module-9.md#support-for-modules-1-7) throughout this module for reference behavior, correctness, measurement, and validation. Create detailed chapters using the [chapter authoring order](chapter-authoring-order.md).

Every chapter follows **Concepts → Experiments → Verification**, applying all [six dimensions and eight engineering principles](learning-approach.md). Connect optimization choices to systems engineering and High-Frequency Trading concerns such as cache locality, workload skew, predictable work, resource ownership, warm-path overhead, fair service, and tail latency. Explain each analogy's limits.

## Planned build and validation sequence

1. Establish an uncached reference and define model, tokenizer, adapter, precision, and workload identities.
2. Add prefix caching and validate lookup, insertion, sharing, eviction, cancellation, and cached-versus-uncached behavior before measuring speed.
3. Measure prefix caching alone across warm and cold workloads, reuse levels, context lengths, arrival patterns, and skew.
4. Select one additional optimization: weight quantization, KV-cache quantization, speculative decoding, structured decoding, or multi-LoRA serving. Define its correctness contract and baseline before enabling it.
5. Evaluate the selected optimization independently and combined with prefix caching. Use capability checks and safe fallback only when fallback preserves the declared request contract; otherwise return an explicit error.
6. Report end-to-end benefits and regressions under fixed resource budgets, with correctness, quality, fairness, memory, latency, and useful-throughput evidence.

Quality changes must not be mislabeled as equivalent computation. Structured decoding intentionally changes allowed outputs; validate against the same constrained contract rather than treating unconstrained outputs as its correctness baseline. Adapter-specific outputs must be compared with the correct adapter reference. Simulated estimates and proposed benchmarks must be labeled separately from measured results.

This module contains outlines only; no optimization has been implemented and no benchmark results have been measured.

## Sources

- [SGLang](https://arxiv.org/abs/2312.07104): RadixAttention and structured generation.
- [Accelerating Large Language Model Decoding with Speculative Sampling](https://arxiv.org/abs/2302.01318): modified rejection sampling and target-distribution preservation.
- [GPTQ](https://arxiv.org/abs/2210.17323): post-training weight quantization.
- [KIVI](https://arxiv.org/abs/2402.02750): KV-cache quantization and key/value precision considerations.
- [XGrammar](https://arxiv.org/abs/2411.15100): grammar-constrained generation and execution overhead.
- [LoRA](https://arxiv.org/abs/2106.09685): low-rank adapter computation.
- [S-LoRA](https://arxiv.org/abs/2311.03285): concurrent adapter residency, batching, and serving.

Record source, implementation, model, toolchain, and hardware versions when the chapters are authored.
