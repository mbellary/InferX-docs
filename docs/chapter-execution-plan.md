# Create and track the detailed InferX chapters


This ExecPlan is a living execution plan: a document that states what to create, how to validate it, and what has actually been completed. Maintain it in accordance with the repository-root `PLANS.md`, copied from the user's uploaded planning reference. The user's explicit instructions control scope: produce educational chapters without implementation code; author one chapter at a time; use Module 9 to support Modules 1–7; exclude Module 8. Generic implementation and prototyping examples in `PLANS.md` are reference examples, not authorization to build an engine, introduce code, publish, or change this scope. Keep Progress, Surprises & Discoveries, Decision Log, and Outcomes & Retrospective current at every stopping point.


## Purpose / Big Picture


Turn 201 outlines into a coherent collection of detailed chapters that helps a reader with basic programming knowledge move from textbook understanding toward the reasoning needed for production-ready, low-latency systems. Each chapter explains concepts from foundations to advanced ideas, proposes experiments without implementation code, and specifies measurements, benchmarks, and profiling that could verify the ideas. A benchmark is a controlled comparison; profiling attributes elapsed time or resource use to stages of the work. Production readiness here means understanding contracts, evidence, ownership, and failure behavior; completing this documentation does not certify an implemented system.

The reader should be able to open any completed chapter, understand every introduced term, follow a worked numerical example and diagram, describe a reproducible experiment, and explain its pass/fail conditions and limits. High-Frequency Trading (HFT), meaning systems that process market events and make trading decisions under tight timing constraints, provides a lens for critical paths, bounded queues, stale information, and tail latency. A tail is the slower end of a latency distribution. Explain what transfers to inference and what does not; do not present trading advice, assert trading results, or equate inference semantics with exchange behavior.

The observable deliverable is the existing InferX documentation site with detailed chapters replacing outlines, an accurate per-chapter progress record here, valid navigation, readable mathematics and diagrams, and reproducible descriptions rather than invented measurements. The execution plan is established. The user authorized sequential detailed chapter authorship on 2026-10-24; M1-C01–M1-C06 are now complete and the next chapter is M1-C07.


## Progress


Last updated: 2026-10-24 21:35 IST. Detailed chapter totals: **6 complete, 0 active, 195 not started, 0 blocked**. Next chapter: **M1-C07**, authoring position 7. Check a chapter only after its full acceptance gate passes.

- [x] (2026-10-24 17:21 IST) Read the uploaded PLANS.md, the learning requirements, the chapter inventory, and the dependency schedule; confirm Modules 1–7 plus supporting Module 9 and no Module 8.
- [x] (2026-10-24 17:21 IST) Preserve the planning reference as repository-root PLANS.md and create this living execution plan with all 201 ordered chapter records and their target concepts and direct prerequisites.
- [x] (2026-10-24 17:23 IST) Validate all 201 chapter records, 535 direct prerequisites, source paths and target concepts; confirm the strict documentation build succeeds without warnings and inspect the rendered plan, Home navigation, progress summary, and ledger.

- [x] (2026-10-24 18:41 IST) Reproduce the GitHub failure with committed navigation (exit 1, the same two warning groups) and verify the corrected working-tree mkdocs.yml (exit 0, no warnings). At that stopping point the root configuration was still uncommitted. It is now included in user commit 3beea89 (verified during M1-C04 startup); no remote rerun is claimed. Chapter totals remain 3 complete and 198 not started.

### Per-chapter progress ledger


Each record contains the authoring position, chapter ID, target concepts, source path, direct prerequisites, and phase. Its stage record is the place to record progress through Concepts, Experiments, Verification, and Review. Replace Not started with Active, Blocked, or Complete as appropriate; stages are Not started, In progress, Done, or Needs revision. An outline is not a completed Concepts stage. Updated and evidence fields must contain actual timestamps and observations when work occurs. Keep new progress checkboxes inside this Progress section only.

- [x] 001 — **M1-C01: From a prompt to the next token** — Complete.
  File: [From a prompt to the next token](model-computation-and-semantics/m1-c01-from-a-prompt-to-the-next-token.md). Category: Model computation and semantics. Phase: 1. Model and numerical foundations.
  Direct prerequisites: None; this is the starting chapter. Target concepts: LLMs, inference, decoder-only models, model weights, token-by-token generation, stages of a single request.
  Stages: Concepts — Done; Experiments — Done; Verification — Done; Review and documentation build — Done.
  Module 9 application: M9-C01 reference contract; M9-C02 timing boundaries; M9-C11 controlled comparisons; M9-C19 token identity and stopping. These supporting chapters remain outlines; introduce the needed checks locally. Updated: 2026-10-24 17:39 IST. Evidence: All six target concepts mapped to explanations and checks; E1–E3 have required fields and matched verification, six-dimension/eight-principle applications, HFT limits, hardware assumptions, and no implementation. Checked original papers, Transformers v4.57.1 documentation, Qwen snapshot eaa56b503cc0a8a4d15de1dd8bd2a7e95a716be2, and NVIDIA specifications. Strict build passed without warnings (3.91 seconds); browser review at /InferX-docs/model-computation-and-semantics/m1-c01-from-a-prompt-to-the-next-token/ confirmed formulas, both diagrams, captions, tables, headings and navigation. Final diagram revision reviewed after refreshing preview. No hardware experiments executed. Next action: Start M1-C02 only after this completion record; no second chapter has been started.

- [x] 002 — **M1-C02: Representing text as tokens** — Complete.
  File: [Representing text as tokens](interfaces-protocols-and-streaming/m1-c02-representing-text-as-tokens.md). Category: Interfaces, protocols, and streaming. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C01. Target concepts: Vocabulary, token IDs, tokenization, encoding and decoding, special tokens, chat templates, preserving token identity.
  Stages: Concepts — Done; Experiments — Done; Verification — Done; Review and documentation build — Done.
  Module 9 application: M9-C01 exact reference contract; M9-C02 preparation timing boundaries; M9-C11 reproducibility and controlled comparisons; M9-C19 tokenizer/template identity and final-output decoding. These remain outlines; explain the required checks locally. Updated: 2026-10-24 18:16 IST. Evidence: Seven target concepts mapped to explanation and checks; E1–E4 required fields and matched verification reviewed; six dimensions, eight principles, HFT limits, CPU requirements and no-code scope covered. Checked RFC 3629, UAX #15 revision 57, the original subword paper, versioned tokenizer/template documentation and Qwen snapshot eaa56b503cc0a8a4d15de1dd8bd2a7e95a716be2. Independent byte/count calculations and local links passed. Strict build passed with zero warnings (4.05 seconds). Browser reviewed /InferX-docs/interfaces-protocols-and-streaming/m1-c02-representing-text-as-tokens/, including both SVG diagrams, captions, formulas, context-budget example, verification table and chapter navigation. No tokenizer or model benchmark executed. Next action: Start M1-C03; all later chapters remain unstarted.

- [x] 003 — **M1-C03: Numbers, vectors, matrices, and tensors** — Complete.
  File: [Numbers, vectors, matrices, and tensors](model-computation-and-semantics/m1-c03-numbers-vectors-matrices-and-tensors.md). Category: Model computation and semantics. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C01. Target concepts: Scalars, vectors, matrices, tensors, axes, dimensions, shapes, indexing, basic Rust representations.
  Stages: Concepts — Done; Experiments — Done; Verification — Done; Review and documentation build — Done.
  Module 9 application: M9-C01 reference invariants and exact shape/index checks; M9-C02 timing boundaries; M9-C11 controlled comparisons; M9-C15 payload versus allocation accounting. These remain outlines; introduce the required checks locally. Updated: 2026-10-24 18:36 IST. Evidence: All nine target concepts mapped to explanations and checks; E1–E3 required fields, matched verification, HFT limits, six dimensions and eight principles reviewed. Checked NumPy 2.3, ONNX tensor conventions, Rust numeric/array/vector/slice specifications, ndarray 0.16.1 and the primary Array Programming with NumPy article. Independent checks passed for counts, indexing, padding, 65,536 unique larger-fixture labels and their exact binary32 representation. Strict build passed without warnings (3.98 seconds). Browser reviewed the chapter at /InferX-docs/model-computation-and-semantics/m1-c03-numbers-vectors-matrices-and-tensors/, its formulas/tables/navigation, and both SVG assets in full. No tensor runtime or inference benchmark executed. Next action: Start M1-C04; all later chapters remain unstarted.

- [x] 004 — **M1-C04: Dot products and matrix multiplication** — Complete.
  File: [Dot products and matrix multiplication](model-computation-and-semantics/m1-c04-dot-products-and-matrix-multiplication.md). Category: Model computation and semantics. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C03. Target concepts: Weighted sums, dot products, matrix multiplication, dimension compatibility, batched multiplication, model projections.
  Stages: Concepts — Done; Experiments — Done; Verification — Done; Review and documentation build — Done.
  Module 9 application: M9-C01 mathematical reference and exact small-fixture invariants; M9-C02 completion/timing boundaries; M9-C11 controlled workload comparisons. These remain outlines; required checks are introduced locally, with general floating-point tolerances deferred to M1-C07/M9-C17. Updated: 2026-10-24 19:04 IST. Evidence: All six target concepts mapped to explanations and checks; E1–E4 required fields, matched verification, six dimensions, eight principles, HFT limits and CPU requirements reviewed. Checked primary operation specifications and projection orientation. Independent arithmetic checks passed for dot/matrix/bias/order/shared/distinct-weight results, byte/work counts and bounded exact binary32 benchmark fixtures. Strict build passed without warnings after completion tracking (4.06 seconds). Browser reviewed chapter formulas and verification tables plus all three SVG diagrams in full at /InferX-docs/model-computation-and-semantics/m1-c04-dot-products-and-matrix-multiplication/. No runtime benchmark executed. Next action: M1-C05; all later chapters remain unstarted.

- [x] 005 — **M1-C05: How tensors occupy memory** — Complete.
  File: [How tensors occupy memory](state-memory-and-caching/m1-c05-how-tensors-occupy-memory.md). Category: State, memory, and caching. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C03. Target concepts: Bytes, contiguous storage, strides, row-major and column-major layouts, reshaping, transposing, views versus copies, broadcasting.
  Stages: Concepts — Done; Experiments — Done; Verification — Done; Review and documentation build — Done.
  Module 9 application: M9-C01 coordinate references; M9-C02 completion/timing boundaries; M9-C11 paired comparisons; M9-C15 unique retained storage; M9-C22 alias/lifetime safety. Supporting chapters remain outlines; required introductory checks are supplied locally. Updated: 2026-10-24 21:21 IST. Evidence: All eight target concepts mapped to explanations and E1–E4 verification; required experiment fields, HFT limits, six dimensions, eight principles, primary sources and CPU requirements reviewed. Checked NumPy 2.3, PyTorch 2.14, ndarray 0.16.1, Rust borrowing documentation and the original NumPy article. Independent checks passed for byte positions, row/column orders, transpose enumeration, broadcast outputs, retained bytes, packing budgets and crossover arithmetic; every E4 fixture output was checked for exact FP32 representation. Final strict build passed with no warnings after completion tracking (2.51 seconds). Browser reviewed the chapter at /InferX-docs/state-memory-and-caching/m1-c05-how-tensors-occupy-memory/, layout formulas, verification table and all three SVG diagrams. Rechecked simplified formula notation and corrected diagram arrows after visual review. No tensor runtime benchmark or hardware experiment executed. Next action: M1-C06; all later chapters remain unstarted.

- [x] 006 — **M1-C06: Reductions, probabilities, and stable softmax** — Complete.
  File: [Reductions, probabilities, and stable softmax](numerics-and-correctness/m1-c06-reductions-probabilities-and-stable-softmax.md). Category: Numerics and correctness. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C03. Target concepts: Sums, means, maxima, reduction axes, probability distributions, exponentials, softmax, overflow, underflow, subtracting the maximum.
  Stages: Concepts — Done; Experiments — Done; Verification — Done; Review and documentation build — Done.
  Module 9 application: M9-C01 coordinate references and invariants; M9-C02 completed timing boundaries; M9-C11 controlled comparisons; M9-C17 independent precision, absolute/relative errors and near-zero handling. Supporting chapters remain outlines; necessary introductory checks are supplied locally. Updated: 2026-10-24 21:35 IST. Evidence: All ten target concepts covered; E1–E4 required fields and matched verification, six dimensions, eight principles, HFT limits, hardware requirements and no-code scope reviewed. Checked primary NumPy 2.3, SciPy 1.16.2, ONNX Softmax-13, PyTorch 2.14, decimal documentation and original shifted-softmax paper. Independent reduction/byte/time calculations and every benchmark coordinate reference passed; 80/120-digit shifted probabilities agree beyond the stated gate, including offsets and tiny tails. Final strict build passed without warnings after completion tracking (2.54 seconds). Browser reviewed /InferX-docs/numerics-and-correctness/m1-c06-reductions-probabilities-and-stable-softmax/, its shift formulas, matched verification table, navigation, and both SVG diagrams in full. No runtime performance experiment executed. Next action: M1-C07; all later chapters remain unstarted.

- [ ] 007 — **M1-C07: Floating-point arithmetic and numerical correctness** — Not started.
  File: [Floating-point arithmetic and numerical correctness](numerics-and-correctness/m1-c07-floating-point-arithmetic-and-numerical-correctness.md). Category: Numerics and correctness. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C06. Target concepts: Floating-point representation, FP32, FP16, BF16, representable range, precision, rounding error, accumulation precision, comparison tolerances.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 008 — **M1-C08: Operation counts and actual execution cost** — Not started.
  File: [Operation counts and actual execution cost](measurement-experimentation-and-economics/m1-c08-operation-counts-and-actual-execution-cost.md). Category: Measurement, experimentation, and economics. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C04, M1-C05, M1-C07. Target concepts: Computational complexity, matrix multiplication costs, memory capacity, data movement, bandwidth, throughput, latency, allocation overhead, bottleneck predictions.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 009 — **M1-C09: Token embeddings and learned projections** — Not started.
  File: [Token embeddings and learned projections](model-computation-and-semantics/m1-c09-token-embeddings-and-learned-projections.md). Category: Model computation and semantics. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C02, M1-C04, M1-C05. Target concepts: Embedding lookup, embedding dimensions, learned weights, linear transformations, intermediate activations, tensor shape tracing.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 010 — **M1-C10: Attention, one dimension at a time** — Not started.
  File: [Attention, one dimension at a time](model-computation-and-semantics/m1-c10-attention-one-dimension-at-a-time.md). Category: Model computation and semantics. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C09, M1-C06. Target concepts: Queries, keys, values, batch and sequence axes, heads, head dimensions, QKᵀ, scaling by √dₖ, softmax axes, weighted value aggregation.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 011 — **M1-C11: Causal masking and positional information** — Not started.
  File: [Causal masking and positional information](model-computation-and-semantics/m1-c11-causal-masking-and-positional-information.md). Category: Model computation and semantics. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C10. Target concepts: Autoregressive dependencies, causal masks, position indices, positional encoding, RoPE, position handling during generation.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 012 — **M1-C12: Multi-head attention and its variants** — Not started.
  File: [Multi-head attention and its variants](model-computation-and-semantics/m1-c12-multi-head-attention-and-its-variants.md). Category: Model computation and semantics. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C11. Target concepts: Splitting and combining heads, attention output projection, multi-head attention, multi-query attention, grouped-query attention, query-head versus KV-head counts.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 013 — **M1-C13: Building a complete Transformer block** — Not started.
  File: [Building a complete Transformer block](model-computation-and-semantics/m1-c13-building-a-complete-transformer-block.md). Category: Model computation and semantics. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C12, M1-C07. Target concepts: Residual connections, normalization, LayerNorm and RMSNorm, MLPs, activation functions, gated MLPs, operation ordering.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 014 — **M1-C14: Assembling a small decoder-only Transformer** — Not started.
  File: [Assembling a small decoder-only Transformer](model-computation-and-semantics/m1-c14-assembling-a-small-decoder-only-transformer.md). Category: Model computation and semantics. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C13. Target concepts: Model configuration, stacked blocks, final normalization, vocabulary projection, logits, fixed weights, loading weights, inference versus training.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 015 — **M9-C01: Defining reference behavior and evidence before optimizing** — Not started.
  File: [Defining reference behavior and evidence before optimizing](numerics-and-correctness/m9-c01-defining-reference-behavior-and-evidence-before-optimizing.md). Category: Numerics and correctness. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M1-C14, M1-C07. Target concepts: Correctness contracts, mathematical and numerical references, invariants, approximations, intentional constraints, falsifiable hypotheses, acceptance criteria, limits of generated-text matching.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 016 — **M9-C17: Comparing logits with justified numerical tolerances** — Not started.
  File: [Comparing logits with justified numerical tolerances](numerics-and-correctness/m9-c17-comparing-logits-with-justified-numerical-tolerances.md). Category: Numerics and correctness. Phase: 1. Model and numerical foundations.
  Direct prerequisites: M9-C01, M1-C14. Target concepts: Reference precision, absolute and relative error, near-zero behavior, per-position and aggregate errors, dtype and reduction effects, extreme values, tolerance justification, locating first divergence.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 017 — **M1-C15: Turning logits into the next token** — Not started.
  File: [Turning logits into the next token](model-computation-and-semantics/m1-c15-turning-logits-into-the-next-token.md). Category: Model computation and semantics. Phase: 2. Single-request generation and timing.
  Direct prerequisites: M1-C14, M9-C01, M9-C17. Target concepts: Greedy decoding, temperature, top-k and top-p filtering, probability renormalization, random sampling, seeds, tie handling.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 018 — **M9-C07: Latency distributions and statistical uncertainty** — Not started.
  File: [Latency distributions and statistical uncertainty](measurement-experimentation-and-economics/m9-c07-latency-distributions-and-statistical-uncertainty.md). Category: Measurement, experimentation, and economics. Phase: 2. Single-request generation and timing.
  Direct prerequisites: M1-C06. Target concepts: Means, medians and tail percentiles, empirical distributions, histogram precision, sample counts, correlated token observations, repeated runs, confidence intervals, censoring, aggregation without averaging percentiles.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 019 — **M1-C16: Building the single-request generation loop** — Not started.
  File: [Building the single-request generation loop](interfaces-protocols-and-streaming/m1-c16-building-the-single-request-generation-loop.md). Category: Interfaces, protocols, and streaming. Phase: 2. Single-request generation and timing.
  Direct prerequisites: M1-C15, M1-C02. Target concepts: Prompt preparation, repeated forward passes, appending tokens, end-of-sequence tokens, output limits, stop sequences, incremental detokenization, partial text handling.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 020 — **M9-C19: Validating tokenization, stopping, and final output** — Not started.
  File: [Validating tokenization, stopping, and final output](interfaces-protocols-and-streaming/m9-c19-validating-tokenization-stopping-and-final-output.md). Category: Interfaces, protocols, and streaming. Phase: 2. Single-request generation and timing.
  Direct prerequisites: M1-C16, M9-C01. Target concepts: Tokenizer and template identity, control tokens, EOS, length caps, multi-token stop sequences, boundary-spanning text, incremental detokenization, terminal reasons, no-token and truncated outputs.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 021 — **M1-C17: Reusing attention state with a KV cache** — Not started.
  File: [Reusing attention state with a KV cache](state-memory-and-caching/m1-c17-reusing-attention-state-with-a-kv-cache.md). Category: State, memory, and caching. Phase: 2. Single-request generation and timing.
  Direct prerequisites: M1-C16, M1-C12, M1-C05. Target concepts: Repeated computation without caching, per-layer keys and values, cache shapes, appending state, cache growth, position offsets, cached causal masking.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 022 — **M1-C18: Understanding prefill and decode** — Not started.
  File: [Understanding prefill and decode](runtime-and-concurrency/m1-c18-understanding-prefill-and-decode.md). Category: Runtime and concurrency. Phase: 2. Single-request generation and timing.
  Direct prerequisites: M1-C17. Target concepts: Prompt processing, first-token selection, subsequent decode steps, phase-specific tensor shapes, cache reads and writes, context-length and batch-size effects.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 023 — **M1-C19: Validating cached and uncached generation** — Not started.
  File: [Validating cached and uncached generation](numerics-and-correctness/m1-c19-validating-cached-and-uncached-generation.md). Category: Numerics and correctness. Phase: 2. Single-request generation and timing.
  Direct prerequisites: M1-C18, M9-C17, M9-C19. Target concepts: Full-prefix reference execution, matching next-token logits, numerical tolerances, greedy output comparison, cache lengths, position and masking errors, edge cases.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 024 — **M9-C02: Request events, clocks, and measurement boundaries** — Not started.
  File: [Request events, clocks, and measurement boundaries](measurement-experimentation-and-economics/m9-c02-request-events-clocks-and-measurement-boundaries.md). Category: Measurement, experimentation, and economics. Phase: 2. Single-request generation and timing.
  Direct prerequisites: M1-C18, M9-C19. Target concepts: Request IDs, arrival and admission, execution and streaming events, monotonic clocks, client versus server boundaries, cross-device clock correlation, timing overhead, missing events.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 025 — **M9-C03: Measuring time to first token including queueing** — Not started.
  File: [Measuring time to first token including queueing](measurement-experimentation-and-economics/m9-c03-measuring-time-to-first-token-including-queueing.md). Category: Measurement, experimentation, and economics. Phase: 2. Single-request generation and timing.
  Direct prerequisites: M9-C02. Target concepts: Arrival-to-first-token definition, queueing, preprocessing and prefill, output delivery, first byte versus first token, client and server TTFT, rejected and no-token requests.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 026 — **M9-C04: Measuring inter-token latency in a streamed protocol** — Not started.
  File: [Measuring inter-token latency in a streamed protocol](interfaces-protocols-and-streaming/m9-c04-measuring-inter-token-latency-in-a-streamed-protocol.md). Category: Interfaces, protocols, and streaming. Phase: 2. Single-request generation and timing.
  Direct prerequisites: M9-C03, M1-C16. Target concepts: Token generation versus delivery, token timestamps, chunk coalescing, buffering, network and client delays, per-request gaps, first-token exclusion, limits of inferring tokens from chunks.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 027 — **M9-C05: Measuring end-to-end latency and throughput** — Not started.
  File: [Measuring end-to-end latency and throughput](measurement-experimentation-and-economics/m9-c05-measuring-end-to-end-latency-and-throughput.md). Category: Measurement, experimentation, and economics. Phase: 2. Single-request generation and timing.
  Direct prerequisites: M9-C04. Target concepts: Arrival-to-completion boundaries, final token versus terminal event, request and output-token rates, prompt versus output work, useful versus draft tokens, success and failure populations, observation windows.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 028 — **M1-C20: Measuring and explaining generation latency** — Not started.
  File: [Measuring and explaining generation latency](measurement-experimentation-and-economics/m1-c20-measuring-and-explaining-generation-latency.md). Category: Measurement, experimentation, and economics. Phase: 2. Single-request generation and timing.
  Direct prerequisites: M1-C19, M1-C08, M9-C03, M9-C04, M9-C05, M9-C07. Target concepts: Input-length and output-length sweeps, prefill time, time to first token, per-token decode latency, total latency, warmup, repeated measurements, correctness checks, predicted versus observed bottlenecks.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 029 — **M2-C01: What the KV cache retains and why** — Not started.
  File: [What the KV cache retains and why](state-memory-and-caching/m2-c01-what-the-kv-cache-retains-and-why.md). Category: State, memory, and caching. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M1-C19. Target concepts: Cached keys and values, model weights versus request state, reuse versus recomputation, prefill and decode cache access, logical token positions.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 030 — **M2-C02: Attention head sharing: MHA, GQA, and MQA** — Not started.
  File: [Attention head sharing: MHA, GQA, and MQA](model-computation-and-semantics/m2-c02-attention-head-sharing-mha-gqa-and-mqa.md). Category: Model computation and semantics. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C01, M1-C12. Target concepts: Query heads versus KV heads, multi-head attention, grouped-query attention, multi-query attention, cache shapes, architecture-dependent memory requirements.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 031 — **M2-C03: Calculating KV memory and request capacity** — Not started.
  File: [Calculating KV memory and request capacity](state-memory-and-caching/m2-c03-calculating-kv-memory-and-request-capacity.md). Category: State, memory, and caching. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C02, M1-C05, M1-C07. Target concepts: Uniform full-attention KV formula, bytes per element, KiB and GiB, cached token counts, 128 KiB per token example, concurrency and context budgets, payload versus overhead.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 032 — **M2-C04: Memory ownership, handles, and lifetimes from first principles** — Not started.
  File: [Memory ownership, handles, and lifetimes from first principles](state-memory-and-caching/m2-c04-memory-ownership-handles-and-lifetimes-from-first-principles.md). Category: State, memory, and caching. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C01, M1-C05. Target concepts: Allocation and reclamation, addresses versus handles, Rust ownership and borrowing concepts, request identity, stale handles, use-after-free, double-free.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 033 — **M2-C05: Contiguous KV storage and its limits** — Not started.
  File: [Contiguous KV storage and its limits](state-memory-and-caching/m2-c05-contiguous-kv-storage-and-its-limits.md). Category: State, memory, and caching. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C03, M2-C04. Target concepts: Contiguous allocation, reserved versus used capacity, growth and copying, external fragmentation, allocation failure despite free space, contiguous baseline.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 034 — **M2-C06: Paged KV storage and logical-to-physical mapping** — Not started.
  File: [Paged KV storage and logical-to-physical mapping](state-memory-and-caching/m2-c06-paged-kv-storage-and-logical-to-physical-mapping.md). Category: State, memory, and caching. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C05. Target concepts: Operating-system paging analogy and limits, fixed-size token blocks, block tables, block offsets, noncontiguous physical storage, PagedAttention, mapping metadata.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 035 — **M2-C07: How attention reads a paged KV layout** — Not started.
  File: [How attention reads a paged KV layout](kernels-compilers-and-execution/m2-c07-how-attention-reads-a-paged-kv-layout.md). Category: Kernels, compilers, and execution. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C06, M1-C10. Target concepts: Block-table lookup, KV tensor strides and layouts, valid token counts, partial tail blocks, gather access, kernel-layout compatibility, metadata and data movement.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 036 — **M2-C08: Designing a fixed-size KV block allocator** — Not started.
  File: [Designing a fixed-size KV block allocator](state-memory-and-caching/m2-c08-designing-a-fixed-size-kv-block-allocator.md). Category: State, memory, and caching. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C06, M2-C04. Target concepts: Preallocated block pools, block IDs, free lists, allocation and release contracts, capacity accounting, all-or-nothing multi-block allocation, rollback.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 037 — **M2-C09: Choosing block size and measuring fragmentation** — Not started.
  File: [Choosing block size and measuring fragmentation](state-memory-and-caching/m2-c09-choosing-block-size-and-measuring-fragmentation.md). Category: State, memory, and caching. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C08, M2-C03. Target concepts: Tokens per block, ceiling-based block counts, internal versus external fragmentation, tail waste, metadata overhead, allocation granularity, block-size tradeoffs.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 038 — **M2-C10: Request state transitions and safe block reuse** — Not started.
  File: [Request state transitions and safe block reuse](runtime-and-concurrency/m2-c10-request-state-transitions-and-safe-block-reuse.md). Category: Runtime and concurrency. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C08, M2-C04. Target concepts: Allocate-write-read-release lifecycle, exclusive mutation, host and device readers, in-flight work, completion versus submission, pinning, deferred reclamation.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 039 — **M2-C11: Reference counting and shared block ownership** — Not started.
  File: [Reference counting and shared block ownership](state-memory-and-caching/m2-c11-reference-counting-and-shared-block-ownership.md). Category: State, memory, and caching. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C10. Target concepts: Multiple owners, request references versus cache references, retain and release rules, reference-count invariants, zero-reference eligibility, in-flight pins.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 040 — **M2-C12: Copy-on-write for branching requests** — Not started.
  File: [Copy-on-write for branching requests](state-memory-and-caching/m2-c12-copy-on-write-for-branching-requests.md). Category: State, memory, and caching. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C11, M2-C07. Target concepts: Immutable shared blocks, divergent continuations, partially filled blocks, private writable tails, copying costs, ownership transfer, failure-safe copy-on-write.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 041 — **M2-C13: Prefix reuse and cache identity** — Not started.
  File: [Prefix reuse and cache identity](state-memory-and-caching/m2-c13-prefix-reuse-and-cache-identity.md). Category: State, memory, and caching. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C12, M1-C02, M1-C11. Target concepts: Exact token-prefix matching, block-granular reuse, prefix indexes, model and adapter identity, position and mask compatibility, dtype and layout compatibility, collision checks, isolation boundaries.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 042 — **M2-C14: Eviction, retention, and reconstruction** — Not started.
  File: [Eviction, retention, and reconstruction](state-memory-and-caching/m2-c14-eviction-retention-and-reconstruction.md). Category: State, memory, and caching. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C13, M2-C11. Target concepts: Active versus retained blocks, eviction eligibility, recency and reuse, policy metadata, reference-safe eviction, recomputation cost, exact reconstruction versus lossy state removal.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 043 — **M2-C15: Admission and growth under a finite KV budget** — Not started.
  File: [Admission and growth under a finite KV budget](scheduling-and-queueing/m2-c15-admission-and-growth-under-a-finite-kv-budget.md). Category: Scheduling and queueing. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C14, M2-C09. Target concepts: Free-block budgets, growth reservations, headroom, admit-wait-reject decisions, backpressure, mixed request lengths, fairness, capacity versus latency.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 044 — **M2-C16: Completion, cancellation, and allocation failure** — Not started.
  File: [Completion, cancellation, and allocation failure](reliability-and-capacity-control/m2-c16-completion-cancellation-and-allocation-failure.md). Category: Reliability and capacity control. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C15, M2-C10. Target concepts: Terminal request states, idempotent cleanup, cancellation during growth or sharing, partial-allocation rollback, draining in-flight work, worker loss and volatile-state recovery.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 045 — **M2-C17: Sliding-window attention and bounded cache state** — Not started.
  File: [Sliding-window attention and bounded cache state](model-computation-and-semantics/m2-c17-sliding-window-attention-and-bounded-cache-state.md). Category: Model computation and semantics. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C07, M1-C11. Target concepts: Model-defined attention windows, retained token ranges, logical versus physical positions, ring-buffer mapping, per-layer windows, hybrid attention, limits of dropping old state.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 046 — **M2-C18: Architecture-specific state: Multi-head Latent Attention** — Not started.
  File: [Architecture-specific state: Multi-head Latent Attention](model-computation-and-semantics/m2-c18-architecture-specific-state-multi-head-latent-attention.md). Category: Model computation and semantics. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C02, M1-C04, M1-C11. Target concepts: MLA compressed latent state, positional components, architecture-specific cache representations, storage versus reconstruction work, limits of the conventional KV formula.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 047 — **M2-C19: Connecting block allocation to the request generator** — Not started.
  File: [Connecting block allocation to the request generator](runtime-and-concurrency/m2-c19-connecting-block-allocation-to-the-request-generator.md). Category: Runtime and concurrency. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C16, M2-C17, M2-C18, M1-C16. Target concepts: Request-owned block tables, prefill writes, decode appends, block-boundary growth, full attention versus retained windows, cache-reader interface, completion and cancellation integration.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 048 — **M2-C20: Validating allocator and cache safety** — Not started.
  File: [Validating allocator and cache safety](numerics-and-correctness/m2-c20-validating-allocator-and-cache-safety.md). Category: Numerics and correctness. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C19, M1-C19, M9-C01. Target concepts: Reference state model, free-live-retained-pinned accounting, live-reference validity, shared-data immutability, randomized lifecycle traces, stale-handle detection, fault injection, cached-logit equivalence.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 049 — **M9-C15: Accounting for weights, KV state, workspace, and fragmentation** — Not started.
  File: [Accounting for weights, KV state, workspace, and fragmentation](state-memory-and-caching/m9-c15-accounting-for-weights-kv-state-workspace-and-fragmentation.md). Category: State, memory, and caching. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C20, M1-C14. Target concepts: Logical versus physical memory, weights, live KV, retained prefixes, unique shared blocks, workspace and communication buffers, allocated versus reserved bytes, peaks, internal and external fragmentation.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 050 — **M2-C21: Benchmarking KV management end to end** — Not started.
  File: [Benchmarking KV management end to end](measurement-experimentation-and-economics/m2-c21-benchmarking-kv-management-end-to-end.md). Category: Measurement, experimentation, and economics. Phase: 3. KV ownership, paging, and capacity.
  Direct prerequisites: M2-C20, M9-C15, M1-C20, M9-C07. Target concepts: Contiguous versus paged baselines, context and concurrency sweeps, reuse skew, cancellation churn, allocation and reclamation latency, tail distributions, fragmentation, useful throughput, full-request latency, reproducible profiling.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 051 — **M3-C01: Following a tensor from CPU to GPU** — Not started.
  File: [Following a tensor from CPU to GPU](hardware-architecture-and-topology/m3-c01-following-a-tensor-from-cpu-to-gpu.md). Category: Hardware architecture and topology. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M1-C14, M1-C18, M2-C04. Target concepts: Host versus device, CPU and GPU roles, host RAM and device memory, kernels, weights, activations, KV state, input and output movement.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 052 — **M3-C02: Reading GPU specifications and capability limits** — Not started.
  File: [Reading GPU specifications and capability limits](hardware-architecture-and-topology/m3-c02-reading-gpu-specifications-and-capability-limits.md). Category: Hardware architecture and topology. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C01, M1-C07, M1-C08. Target concepts: GPU model and compute capability, SM count, memory capacity and bandwidth, cache sizes, precision-specific dense versus sparse throughput, power and clock limits, software versions.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 053 — **M3-C03: Threads, warps, blocks, grids, and streaming multiprocessors** — Not started.
  File: [Threads, warps, blocks, grids, and streaming multiprocessors](hardware-architecture-and-topology/m3-c03-threads-warps-blocks-grids-and-streaming-multiprocessors.md). Category: Hardware architecture and topology. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C02. Target concepts: SIMT execution, thread indexing, warps, thread blocks, grids, SM assignment, warp scheduling, divergence, block independence.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 054 — **M3-C05: Device memory, HBM, and the cache hierarchy** — Not started.
  File: [Device memory, HBM, and the cache hierarchy](hardware-architecture-and-topology/m3-c05-device-memory-hbm-and-the-cache-hierarchy.md). Category: Hardware architecture and topology. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C01, M1-C05. Target concepts: Global memory, HBM versus GDDR, L2 and L1 caches, cache lines and transactions, bandwidth versus access latency, capacity, working sets, cache hits and misses.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 055 — **M3-C06: Registers, shared memory, and local resource pressure** — Not started.
  File: [Registers, shared memory, and local resource pressure](hardware-architecture-and-topology/m3-c06-registers-shared-memory-and-local-resource-pressure.md). Category: Hardware architecture and topology. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C03, M3-C05. Target concepts: Per-thread registers, per-block shared memory, storage scope and lifetime, register spills and local memory, bank conflicts, synchronization, architecture-specific resource limits.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 056 — **M3-C04: Occupancy, latency hiding, and hardware utilization** — Not started.
  File: [Occupancy, latency hiding, and hardware utilization](hardware-architecture-and-topology/m3-c04-occupancy-latency-hiding-and-hardware-utilization.md). Category: Hardware architecture and topology. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C03, M3-C06. Target concepts: Resident versus active and eligible warps, occupancy limits, registers and shared-memory budgets, available parallel work, latency hiding, utilization versus occupancy.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 057 — **M3-C07: Memory coalescing, alignment, and tensor layouts** — Not started.
  File: [Memory coalescing, alignment, and tensor layouts](kernels-compilers-and-execution/m3-c07-memory-coalescing-alignment-and-tensor-layouts.md). Category: Kernels, compilers, and execution. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C03, M3-C05, M1-C05. Target concepts: Warp memory accesses, contiguous versus strided access, alignment, memory transactions, useful versus transferred bytes, tensor strides, layout conversion costs.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 058 — **M3-C08: Tiling and reuse through the memory hierarchy** — Not started.
  File: [Tiling and reuse through the memory hierarchy](kernels-compilers-and-execution/m3-c08-tiling-and-reuse-through-the-memory-hierarchy.md). Category: Kernels, compilers, and execution. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C07, M3-C06, M1-C04. Target concepts: Matrix tiles, global-to-shared-to-register movement, reuse, synchronization, tile-size tradeoffs, edge tiles, shared-memory capacity, data movement versus redundant work.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 059 — **M3-C09: Tensor cores and supported matrix operations** — Not started.
  File: [Tensor cores and supported matrix operations](kernels-compilers-and-execution/m3-c09-tensor-cores-and-supported-matrix-operations.md). Category: Kernels, compilers, and execution. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C08, M3-C02, M1-C07. Target concepts: Matrix multiply-accumulate, tensor-core versus scalar execution paths, operand and accumulator formats, shape and alignment requirements, dense versus sparse paths, architecture-dependent capabilities.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 060 — **M3-C10: Host and device buffer placement and lifetime** — Not started.
  File: [Host and device buffer placement and lifetime](state-memory-and-caching/m3-c10-host-and-device-buffer-placement-and-lifetime.md). Category: State, memory, and caching. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C05, M2-C04. Target concepts: Pageable versus pinned host memory, device allocations, unified addressing versus unified memory, migration and residency, buffer reuse, ownership across transfers, allocation outside timed regions.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 061 — **M3-C11: Streams, events, and dependency ordering** — Not started.
  File: [Streams, events, and dependency ordering](runtime-and-concurrency/m3-c11-streams-events-and-dependency-ordering.md). Category: Runtime and concurrency. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C03, M3-C10, M2-C10. Target concepts: Asynchronous submission versus completion, stream ordering, cross-stream events, default-stream semantics, synchronization scope, producer-consumer dependencies, safe buffer reuse.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 062 — **M3-C12: Asynchronous copies and useful overlap** — Not started.
  File: [Asynchronous copies and useful overlap](runtime-and-concurrency/m3-c12-asynchronous-copies-and-useful-overlap.md). Category: Runtime and concurrency. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C11. Target concepts: Copy engines, pinned-memory requirements, double buffering, copy-compute overlap, independence and resource constraints, backpressure, cancellation with in-flight work, asynchronous error observation.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 063 — **M3-C13: PCIe, NVLink, NUMA, and device topology** — Not started.
  File: [PCIe, NVLink, NUMA, and device topology](hardware-architecture-and-topology/m3-c13-pcie-nvlink-numa-and-device-topology.md). Category: Hardware architecture and topology. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C02, M3-C10. Target concepts: Link bandwidth and latency, PCIe generation and width, NVLink availability, peer-access support, CPU socket and NUMA placement, switch paths, NIC placement, topology inspection.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 064 — **M3-C14: Moving tensors between devices and hosts** — Not started.
  File: [Moving tensors between devices and hosts](networking-and-communication/m3-c14-moving-tensors-between-devices-and-hosts.md). Category: Networking and communication. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C13, M3-C12. Target concepts: Host-device, device-device, peer-to-peer and staged transfers, network fabrics, RDMA and GPUDirect concepts, transfer completion, shared-link contention, communication scope and limits.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 065 — **M9-C16: Recording hardware conditions that change measurements** — Not started.
  File: [Recording hardware conditions that change measurements](hardware-architecture-and-topology/m9-c16-recording-hardware-conditions-that-change-measurements.md). Category: Hardware architecture and topology. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C14, M9-C02. Target concepts: CPU and GPU models, memory capacity and bandwidth, NUMA and interconnect topology, clocks, power and thermal limits, co-tenancy and partitions, driver and runtime versions, telemetry sampling.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 066 — **M3-C15: Counting FLOPs and bytes at a defined boundary** — Not started.
  File: [Counting FLOPs and bytes at a defined boundary](measurement-experimentation-and-economics/m3-c15-counting-flops-and-bytes-at-a-defined-boundary.md). Category: Measurement, experimentation, and economics. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C09, M3-C07, M1-C08. Target concepts: GEMV and GEMM dimensions, multiply-add counting, theoretical versus observed traffic, memory-level boundaries, cache reuse, reads and writes, units, achieved throughput and bandwidth.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 067 — **M3-C16: Using the roofline model to predict bottlenecks** — Not started.
  File: [Using the roofline model to predict bottlenecks](measurement-experimentation-and-economics/m3-c16-using-the-roofline-model-to-predict-bottlenecks.md). Category: Measurement, experimentation, and economics. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C15, M3-C02, M3-C04. Target concepts: Arithmetic intensity, compute and bandwidth roofs, ridge point, idealized kernel-time estimates, effective versus peak rates, hierarchical rooflines, launch and dependency limits.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 068 — **M3-C17: Batching, weight reuse, and shifting bottlenecks** — Not started.
  File: [Batching, weight reuse, and shifting bottlenecks](scheduling-and-queueing/m3-c17-batching-weight-reuse-and-shifting-bottlenecks.md). Category: Scheduling and queueing. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C16, M1-C18. Target concepts: Batch size and matrix shapes, weight reuse, arithmetic intensity changes, prefill versus decode tendencies, working-set limits, saturation, batching delay versus service time.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 069 — **M3-C18: Validating GPU computation and memory movement** — Not started.
  File: [Validating GPU computation and memory movement](numerics-and-correctness/m3-c18-validating-gpu-computation-and-memory-movement.md). Category: Numerics and correctness. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C14, M3-C09, M9-C17. Target concepts: Reference GEMV and GEMM outputs, accumulation precision, absolute and relative tolerances, reduction-order differences, transfer integrity, shape and stride checks, race and lifetime faults.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 070 — **M9-C12: Reading CPU-GPU timelines and scheduling gaps** — Not started.
  File: [Reading CPU-GPU timelines and scheduling gaps](measurement-experimentation-and-economics/m9-c12-reading-cpu-gpu-timelines-and-scheduling-gaps.md). Category: Measurement, experimentation, and economics. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C18, M9-C02. Target concepts: Host threads and queues, executor iterations, launch submission, GPU idle periods, synchronization, device completion, critical-path attribution, NVTX-style ranges, tracing overhead.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 071 — **M9-C13: Using kernel profilers to explain hardware bottlenecks** — Not started.
  File: [Using kernel profilers to explain hardware bottlenecks](measurement-experimentation-and-economics/m9-c13-using-kernel-profilers-to-explain-hardware-bottlenecks.md). Category: Measurement, experimentation, and economics. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M9-C12, M3-C16, M3-C06. Target concepts: Memory traffic, bandwidth, compute throughput, occupancy, stalls, spills, cache behavior, roofline reasoning, profiler replay and perturbation, isolated versus serving measurements.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 072 — **M3-C19: Designing trustworthy asynchronous GPU benchmarks** — Not started.
  File: [Designing trustworthy asynchronous GPU benchmarks](measurement-experimentation-and-economics/m3-c19-designing-trustworthy-asynchronous-gpu-benchmarks.md). Category: Measurement, experimentation, and economics. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C18, M3-C11, M9-C02, M9-C07, M9-C16. Target concepts: Device-event versus host-wall timing, timing boundaries, completion waits, launch overhead, warmup, repeated trials, cache state, clocks and thermals, interference, distributions, profiler overhead.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 073 — **M3-C20: Benchmarking memory copies across sizes and paths** — Not started.
  File: [Benchmarking memory copies across sizes and paths](measurement-experimentation-and-economics/m3-c20-benchmarking-memory-copies-across-sizes-and-paths.md). Category: Measurement, experimentation, and economics. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C19, M3-C14. Target concepts: Host-to-device, device-to-host and device-to-device copies, pageable versus pinned buffers, size sweeps, setup versus transfer costs, payload versus read-plus-write bandwidth, overlap and contention.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 074 — **M3-C21: Benchmarking matrix-vector multiplication across shapes** — Not started.
  File: [Benchmarking matrix-vector multiplication across shapes](measurement-experimentation-and-economics/m3-c21-benchmarking-matrix-vector-multiplication-across-shapes.md). Category: Measurement, experimentation, and economics. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C20, M3-C16. Target concepts: GEMV shape sweeps, weight and vector traffic, output writes, cache-resident versus device-memory working sets, bandwidth utilization, small-workload overhead, correctness checks.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 075 — **M3-C22: Benchmarking matrix-matrix multiplication across shapes** — Not started.
  File: [Benchmarking matrix-matrix multiplication across shapes](measurement-experimentation-and-economics/m3-c22-benchmarking-matrix-matrix-multiplication-across-shapes.md). Category: Measurement, experimentation, and economics. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C21, M3-C17. Target concepts: GEMM shape and batch sweeps, operand reuse, tensor-core eligibility, tile utilization, alignment and edge effects, precision controls, achieved compute throughput, GEMV comparison.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 076 — **M3-C23: Explaining GPU profiles and end-to-end serving effects** — Not started.
  File: [Explaining GPU profiles and end-to-end serving effects](measurement-experimentation-and-economics/m3-c23-explaining-gpu-profiles-and-end-to-end-serving-effects.md). Category: Measurement, experimentation, and economics. Phase: 4. GPU execution, movement, and profiling.
  Direct prerequisites: M3-C22, M9-C12, M9-C13, M1-C20. Target concepts: Nsight Systems timelines, Nsight Compute counters, kernel versus request critical paths, memory traffic, occupancy and stalls, roofline reconciliation, controlled comparisons, tail latency, reproducible evidence.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 077 — **M4-C01: Defining a GPU kernel and its contract** — Not started.
  File: [Defining a GPU kernel and its contract](kernels-compilers-and-execution/m4-c01-defining-a-gpu-kernel-and-its-contract.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M3-C23, M9-C01. Target concepts: Kernel inputs and outputs, shapes, strides, dtypes, devices, aliasing, valid memory ranges, mathematical reference behavior, launch configuration.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 078 — **M4-C02: Mapping an operation onto CUDA threads and blocks** — Not started.
  File: [Mapping an operation onto CUDA threads and blocks](kernels-compilers-and-execution/m4-c02-mapping-an-operation-onto-cuda-threads-and-blocks.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C01, M3-C03. Target concepts: CUDA execution model, thread and block indexing, SIMT execution, memory access, masked boundaries, warp and block cooperation, synchronization scope.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 079 — **M4-C03: Understanding the Triton programming model** — Not started.
  File: [Understanding the Triton programming model](kernels-compilers-and-execution/m4-c03-understanding-the-triton-programming-model.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C02, M3-C08. Target concepts: Triton programs and launch grids, block-oriented operations, masks, loads and stores, reductions, compile-time parameters, comparison with CUDA, Rust host integration boundaries.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 080 — **M4-C04: Compilation, specialization, and the warm execution path** — Not started.
  File: [Compilation, specialization, and the warm execution path](kernels-compilers-and-execution/m4-c04-compilation-specialization-and-the-warm-execution-path.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C03, M3-C02. Target concepts: Ahead-of-time and just-in-time compilation, device targets, generated artifacts, specialization keys, compilation caches, first-use overhead, cold versus warm execution, version compatibility.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 081 — **M4-C05: Tiling an operation for data reuse** — Not started.
  File: [Tiling an operation for data reuse](kernels-compilers-and-execution/m4-c05-tiling-an-operation-for-data-reuse.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C04, M3-C08. Target concepts: Tile selection, register and shared-memory reuse, coalesced accesses, edge tiles, redundant work, data-movement accounting, synchronization costs.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 082 — **M4-C06: Parallel reductions and synchronization** — Not started.
  File: [Parallel reductions and synchronization](kernels-compilers-and-execution/m4-c06-parallel-reductions-and-synchronization.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C05, M1-C06, M1-C07. Target concepts: Tree reductions, warp and block reductions, cross-block decomposition, neutral elements, masked lanes, synchronization, reduction order, accumulation precision.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 083 — **M4-C07: Online softmax and stable incremental reductions** — Not started.
  File: [Online softmax and stable incremental reductions](numerics-and-correctness/m4-c07-online-softmax-and-stable-incremental-reductions.md). Category: Numerics and correctness. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C06, M1-C10. Target concepts: Running maximum, rescaled exponential sums, mergeable reduction state, chunked processing, online weighted sums, masking, numerical stability, equivalence within tolerance.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 084 — **M4-C08: Kernel fusion and its tradeoffs** — Not started.
  File: [Kernel fusion and its tradeoffs](kernels-compilers-and-execution/m4-c08-kernel-fusion-and-its-tradeoffs.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C05, M4-C06. Target concepts: Producer-consumer fusion, intermediate tensors, eliminated reads and writes, reduced launches, dependency boundaries, resource growth, fusion versus recomputation.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 085 — **M4-C09: Register pressure, occupancy, and spills in kernel design** — Not started.
  File: [Register pressure, occupancy, and spills in kernel design](kernels-compilers-and-execution/m4-c09-register-pressure-occupancy-and-spills-in-kernel-design.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C08, M3-C04, M3-C06. Target concepts: Live values, register allocation, tile and fusion choices, occupancy limits, local-memory spills, instruction parallelism, measured utilization versus occupancy.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 086 — **M4-C10: Shape specialization, padding, and dispatch** — Not started.
  File: [Shape specialization, padding, and dispatch](kernels-compilers-and-execution/m4-c10-shape-specialization-padding-and-dispatch.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C09, M4-C04. Target concepts: Shape families, strides and alignment, padding overhead, masked lanes, padded reduction identities, specialization count, dispatch guards, generic fallbacks.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 087 — **M4-C11: FlashAttention as an IO-aware attention algorithm** — Not started.
  File: [FlashAttention as an IO-aware attention algorithm](kernels-compilers-and-execution/m4-c11-flashattention-as-an-io-aware-attention-algorithm.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C07, M4-C10, M1-C11. Target concepts: Tiled QK and value aggregation, online softmax, HBM versus on-chip storage, avoiding full attention-matrix materialization, mathematical exactness versus floating-point differences, quadratic full-attention arithmetic.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 088 — **M4-C12: Distinguishing FlashAttention, PagedAttention, and prefix caching** — Not started.
  File: [Distinguishing FlashAttention, PagedAttention, and prefix caching](kernels-compilers-and-execution/m4-c12-distinguishing-flashattention-pagedattention-and-prefix-caching.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C11, M2-C07, M2-C13. Target concepts: Intermediate-data movement, dynamic KV layout, exact-prefix reuse, complementary techniques, applicability and compatibility, correctness boundaries, choosing the constrained stage.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 089 — **M4-C13: Tracing CPU-to-GPU launch overhead** — Not started.
  File: [Tracing CPU-to-GPU launch overhead](runtime-and-concurrency/m4-c13-tracing-cpu-to-gpu-launch-overhead.md). Category: Runtime and concurrency. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C01, M9-C12. Target concepts: Host dispatch, language and runtime boundaries, driver submission, launch latency, device scheduling, small-kernel overhead, kernel execution versus request time.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 090 — **M4-C14: CPU-GPU synchronization and hidden serialization** — Not started.
  File: [CPU-GPU synchronization and hidden serialization](runtime-and-concurrency/m4-c14-cpu-gpu-synchronization-and-hidden-serialization.md). Category: Runtime and concurrency. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C13, M3-C11. Target concepts: Host waits, stream and event dependencies, device-to-host results, implicit synchronization, critical paths, unnecessary barriers, safe asynchronous buffer ownership.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 091 — **M4-C15: CUDA Graph capture, instantiation, and replay** — Not started.
  File: [CUDA Graph capture, instantiation, and replay](kernels-compilers-and-execution/m4-c15-cuda-graph-capture-instantiation-and-replay.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C14, M4-C04. Target concepts: Graph nodes and dependencies, explicit construction versus stream capture, instantiation, repeated submission, setup amortization, capture restrictions, graph versus kernel fusion.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 092 — **M4-C16: Replay constraints, graph variants, and buffer lifetimes** — Not started.
  File: [Replay constraints, graph variants, and buffer lifetimes](runtime-and-concurrency/m4-c16-replay-constraints-graph-variants-and-buffer-lifetimes.md). Category: Runtime and concurrency. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C15, M4-C10, M2-C10. Target concepts: Captured parameters and addresses, buffer stability, supported graph updates, changing shapes and batch sizes, graph variants, warmup, memory-pool ownership, invalidation, cancellation and safe fallback.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 093 — **M9-C11: Controlled comparisons, warmup, and reproducibility** — Not started.
  File: [Controlled comparisons, warmup, and reproducibility](measurement-experimentation-and-economics/m9-c11-controlled-comparisons-warmup-and-reproducibility.md). Category: Measurement, experimentation, and economics. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C16, M9-C07, M2-C13. Target concepts: Fixed models and workloads, seeds, cold versus warm state, prefix-cache controls, compilation and graph setup, allocator state, paired comparisons, ablations, repeated trials, configuration records.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 094 — **M4-C17: Designing a fused normalization kernel** — Not started.
  File: [Designing a fused normalization kernel](kernels-compilers-and-execution/m4-c17-designing-a-fused-normalization-kernel.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C08, M4-C10, M1-C13. Target concepts: LayerNorm versus RMSNorm, row-wise reductions, epsilon placement, affine parameters, residual fusion options, accumulation precision, output dtype, traffic and launch savings.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 095 — **M4-C19: Randomness, reproducibility, and sampling equivalence** — Not started.
  File: [Randomness, reproducibility, and sampling equivalence](numerics-and-correctness/m4-c19-randomness-reproducibility-and-sampling-equivalence.md). Category: Numerics and correctness. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M1-C15, M9-C07. Target concepts: Seed and random-stream ownership, per-request RNG state, draw ordering, counter mapping, deterministic replay conditions, distributional versus token-wise equivalence, statistical uncertainty.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 096 — **M4-C18: Designing a fused sampling kernel** — Not started.
  File: [Designing a fused sampling kernel](kernels-compilers-and-execution/m4-c18-designing-a-fused-sampling-kernel.md). Category: Kernels, compilers, and execution. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C19, M4-C06, M4-C10, M1-C15. Target concepts: Logit transforms, temperature, greedy selection, top-k and top-p boundaries, normalization, random draws, tie rules, vocabulary padding, exact versus approximate sampling contracts.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 097 — **M4-C20: Validating fused kernels and graph replay** — Not started.
  File: [Validating fused kernels and graph replay](numerics-and-correctness/m4-c20-validating-fused-kernels-and-graph-replay.md). Category: Numerics and correctness. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C16, M4-C17, M4-C18, M9-C17, M9-C11. Target concepts: Reference comparisons, tolerances, extreme inputs, awkward shapes, strides, masks, aliasing, uninitialized reads, races, stale buffers, graph-versus-eager equivalence, supported input contracts.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 098 — **M9-C27: Designing regression experiments and validation gates** — Not started.
  File: [Designing regression experiments and validation gates](measurement-experimentation-and-economics/m9-c27-designing-regression-experiments-and-validation-gates.md). Category: Measurement, experimentation, and economics. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C20, M9-C11, M9-C01. Target concepts: Hypothesis-driven changes, baseline preservation, correctness-before-speed gates, matched traces, ablation controls, workload-specific regressions, distribution shifts, minimum evidence, reproducible pass and fail criteria.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 099 — **M4-C21: Tuning kernels with controlled experiments** — Not started.
  File: [Tuning kernels with controlled experiments](measurement-experimentation-and-economics/m4-c21-tuning-kernels-with-controlled-experiments.md). Category: Measurement, experimentation, and economics. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C20, M4-C09, M9-C13, M9-C27. Target concepts: Tile sizes, warps and stages, register and shared-memory limits, profiling hypotheses, tuning cost, separate tuning and evaluation workloads, specialization regressions, cold-start cost.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 100 — **M4-C22: Benchmarking realistic shapes and execution modes** — Not started.
  File: [Benchmarking realistic shapes and execution modes](measurement-experimentation-and-economics/m4-c22-benchmarking-realistic-shapes-and-execution-modes.md). Category: Measurement, experimentation, and economics. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C21, M9-C03, M9-C04, M9-C05. Target concepts: Hidden and vocabulary dimensions, batch sizes, dtypes and layouts, fused versus unfused baselines, eager versus graph replay, launch counts, memory traffic, warmup, timing boundaries, latency distributions.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 101 — **M4-C23: Integrating a fused kernel into the generator** — Not started.
  File: [Integrating a fused kernel into the generator](runtime-and-concurrency/m4-c23-integrating-a-fused-kernel-into-the-generator.md). Category: Runtime and concurrency. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C22, M1-C16, M2-C19. Target concepts: Rust host boundary, backend capability checks, kernel dispatch contracts, stream compatibility, buffer lifetimes, RNG ownership, graph integration, correct fallback and failure propagation.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 102 — **M4-C24: Verifying end-to-end generator improvements** — Not started.
  File: [Verifying end-to-end generator improvements](measurement-experimentation-and-economics/m4-c24-verifying-end-to-end-generator-improvements.md). Category: Measurement, experimentation, and economics. Phase: 5. Kernels, graph execution, and controlled optimization.
  Direct prerequisites: M4-C23, M1-C20, M9-C27. Target concepts: Critical-path attribution, Amdahl-style speedup limits, prefill and decode separation, time to first token, inter-token and total latency, useful throughput, correctness gates, amortization, tail regressions.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 103 — **M5-C01: Separating the model executor from the serving scheduler** — Not started.
  File: [Separating the model executor from the serving scheduler](scheduling-and-queueing/m5-c01-separating-the-model-executor-from-the-serving-scheduler.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M4-C24, M2-C19, M1-C18. Target concepts: Execution versus scheduling, request queues, iteration boundaries, batch membership, compute and memory budgets, policy versus mechanism, service objectives.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 104 — **M5-C02: Processes, threads, and operating-system scheduling** — Not started.
  File: [Processes, threads, and operating-system scheduling](runtime-and-concurrency/m5-c02-processes-threads-and-operating-system-scheduling.md). Category: Runtime and concurrency. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C01, M2-C04. Target concepts: Address spaces, stacks and heaps, process isolation, threads, context switches, concurrency versus parallelism, CPU scheduling versus request scheduling, Rust execution contexts.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 105 — **M5-C05: Synchronization, ownership, and resource lifetimes** — Not started.
  File: [Synchronization, ownership, and resource lifetimes](runtime-and-concurrency/m5-c05-synchronization-ownership-and-resource-lifetimes.md). Category: Runtime and concurrency. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C02, M2-C11. Target concepts: Exclusive and shared access, mutexes, atomics and condition variables, Rust ownership and borrowing, contention, deadlock, lost wakeups, request and buffer lifetimes.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 106 — **M5-C03: IPC and shared-memory communication** — Not started.
  File: [IPC and shared-memory communication](runtime-and-concurrency/m5-c03-ipc-and-shared-memory-communication.md). Category: Runtime and concurrency. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C02, M5-C05. Target concepts: Inter-process communication, pipes, sockets and channels, serialization and copying, shared-memory regions, visibility, synchronization, ownership across process boundaries, worker failure.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 107 — **M5-C04: Producer-consumer queues and bounded work** — Not started.
  File: [Producer-consumer queues and bounded work](runtime-and-concurrency/m5-c04-producer-consumer-queues-and-bounded-work.md). Category: Runtime and concurrency. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C02, M5-C05. Target concepts: Producers and consumers, bounded versus unbounded queues, enqueue and dequeue contracts, FIFO ordering, ownership transfer, blocking and nonblocking behavior, queue capacity.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 108 — **M5-C06: Asynchronous execution and completion-driven progress** — Not started.
  File: [Asynchronous execution and completion-driven progress](runtime-and-concurrency/m5-c06-asynchronous-execution-and-completion-driven-progress.md). Category: Runtime and concurrency. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C03, M5-C04, M3-C11. Target concepts: Tasks and futures, event loops, blocking versus asynchronous work, completion notifications, host-device dependencies, in-flight batches, single-owner scheduler state, safe reclamation.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 109 — **M9-C22: Verifying ownership and memory safety under concurrency** — Not started.
  File: [Verifying ownership and memory safety under concurrency](runtime-and-concurrency/m9-c22-verifying-ownership-and-memory-safety-under-concurrency.md). Category: Runtime and concurrency. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C06, M2-C20, M3-C18. Target concepts: Ownership transfer, shared references, stale handles, use-after-free, double release, races, uninitialized accesses, asynchronous buffer lifetimes, sanitizer scope, allocation conservation, randomized lifecycle traces.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 110 — **M5-C07: Describing mixed serving workloads and arrival traces** — Not started.
  File: [Describing mixed serving workloads and arrival traces](measurement-experimentation-and-economics/m5-c07-describing-mixed-serving-workloads-and-arrival-traces.md). Category: Measurement, experimentation, and economics. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C01, M9-C02. Target concepts: Prompt and output lengths, declared output caps versus realized lengths, arrival timestamps, bursts, skew and correlations, reuse, seeds, offered versus admitted load, open-loop versus closed-loop traffic.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 111 — **M5-C08: Queueing delay, service time, and request latency** — Not started.
  File: [Queueing delay, service time, and request latency](scheduling-and-queueing/m5-c08-queueing-delay-service-time-and-request-latency.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C07, M5-C04, M9-C03, M9-C05. Target concepts: Arrival, admission, first service, first token and completion timestamps, queue versus system boundaries, waiting versus service time, head-of-line blocking, iteration-level interference.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 112 — **M5-C09: Applying Little’s law with consistent boundaries** — Not started.
  File: [Applying Little’s law with consistent boundaries](scheduling-and-queueing/m5-c09-applying-little-s-law-with-consistent-boundaries.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C08, M9-C07. Target concepts: Mean requests in system, effective arrival rate, mean residence time, L = lambda times W, queue-only accounting, stable measurement regimes, matched populations, finite-window effects, means versus percentiles.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 113 — **M5-C10: Utilization, variability, and tail latency** — Not started.
  File: [Utilization, variability, and tail latency](scheduling-and-queueing/m5-c10-utilization-variability-and-tail-latency.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C09, M3-C16. Target concepts: Service demand, bottleneck utilization, saturation, burstiness, service-time variance, latency distributions, queue growth, simple queueing-model assumptions, limits of fixed-rate models for dynamic batches.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 114 — **M9-C08: Designing representative serving workloads** — Not started.
  File: [Designing representative serving workloads](measurement-experimentation-and-economics/m9-c08-designing-representative-serving-workloads.md). Category: Measurement, experimentation, and economics. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C07, M2-C13. Target concepts: Context and output lengths, arrival patterns, bursts, correlations, prefix reuse and skew, adapter and precision settings, real versus synthetic traces, stratified workload reporting.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 115 — **M9-C09: Open-loop load generation and coordinated omission** — Not started.
  File: [Open-loop load generation and coordinated omission](measurement-experimentation-and-economics/m9-c09-open-loop-load-generation-and-coordinated-omission.md). Category: Measurement, experimentation, and economics. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M9-C08, M5-C08. Target concepts: Scheduled arrivals independent of completions, open-loop versus closed-loop traffic, offered-load preservation, generator scheduling lag, intended versus actual send times, server slowdown, overload visibility.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 116 — **M9-C10: Validating the load generator and request accounting** — Not started.
  File: [Validating the load generator and request accounting](measurement-experimentation-and-economics/m9-c10-validating-the-load-generator-and-request-accounting.md). Category: Measurement, experimentation, and economics. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M9-C09, M5-C06. Target concepts: Client CPU and network limits, connection and concurrency caps, actual offered rate, lost or duplicate requests, timeout and cancellation populations, incomplete work, drain periods, generator-induced bottlenecks.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 117 — **M9-C06: Defining SLOs, goodput, and useful capacity** — Not started.
  File: [Defining SLOs, goodput, and useful capacity](measurement-experimentation-and-economics/m9-c06-defining-slos-goodput-and-useful-capacity.md). Category: Measurement, experimentation, and economics. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M9-C03, M9-C04, M9-C05, M9-C07, M9-C10, M5-C10. Target concepts: Latency objectives, per-request acceptance predicates, TTFT and token-gap targets, request versus token goodput, offered and admitted work, rejection accounting, capacity under quality and latency constraints.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 118 — **M5-C11: Defining a static batching baseline** — Not started.
  File: [Defining a static batching baseline](scheduling-and-queueing/m5-c11-defining-a-static-batching-baseline.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C06, M5-C10, M3-C17. Target concepts: Fixed request cohorts, batch formation delay, length mismatch, completion masking, inactive slots, no mid-cohort admission, baseline policy definition, capacity and latency tradeoffs.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 119 — **M5-C12: Continuous batching at execution boundaries** — Not started.
  File: [Continuous batching at execution boundaries](scheduling-and-queueing/m5-c12-continuous-batching-at-execution-boundaries.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C11, M2-C10. Target concepts: Iteration-level scheduling, removing completed requests, admitting new work, active-set updates, request identity across reordered batches, decode progress, execution-boundary safety.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 120 — **M5-C13: Budgeting work for each execution iteration** — Not started.
  File: [Budgeting work for each execution iteration](scheduling-and-queueing/m5-c13-budgeting-work-for-each-execution-iteration.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C12, M4-C10, M4-C16. Target concepts: Request limits, token budgets, prefill versus decode work, context-dependent costs, sequence limits, kernel and graph shape constraints, batch packing, per-iteration memory checks.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 121 — **M5-C14: Planning for future KV-cache growth** — Not started.
  File: [Planning for future KV-cache growth](scheduling-and-queueing/m5-c14-planning-for-future-kv-cache-growth.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C13, M2-C15, M9-C15. Target concepts: Current versus future cached tokens, declared output limits, conservative reservation, incremental growth, bounded overcommit, headroom, shared physical blocks, unknown future demand, exhaustion policy.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 122 — **M5-C15: Admission control and backpressure** — Not started.
  File: [Admission control and backpressure](scheduling-and-queueing/m5-c15-admission-control-and-backpressure.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C14, M5-C04, M9-C06. Target concepts: Admit-wait-reject decisions, bounded queues, memory-aware admission, upstream backpressure, rejection accounting, capacity reservations, overload thresholds, avoiding admission-growth deadlock.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 123 — **M5-C16: Fairness, priorities, and starvation prevention** — Not started.
  File: [Fairness, priorities, and starvation prevention](scheduling-and-queueing/m5-c16-fairness-priorities-and-starvation-prevention.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C15, M5-C10. Target concepts: FIFO and age-based policies, priority classes, request versus token fairness, weighted budgets, starvation, priority inversion, unknown job sizes, avoiding clairvoyant policies.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 124 — **M5-C17: Chunked prefill and resumable prompt processing** — Not started.
  File: [Chunked prefill and resumable prompt processing](scheduling-and-queueing/m5-c17-chunked-prefill-and-resumable-prompt-processing.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C13, M1-C18, M2-C19. Target concepts: Splitting prompts into token chunks, partial-prefill state, cache positions, causal dependencies, mixing prefill and decode, semantic equivalence, checkpointing progress within a request.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 125 — **M5-C18: Choosing chunk sizes and balancing prefill with decode** — Not started.
  File: [Choosing chunk sizes and balancing prefill with decode](scheduling-and-queueing/m5-c18-choosing-chunk-sizes-and-balancing-prefill-with-decode.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C17, M5-C16, M9-C03, M9-C04. Target concepts: Chunk-size budgets, decode interference, time-to-first-token versus inter-token latency, scheduling overhead, throughput tradeoffs, measured cost estimates, workload-dependent tuning.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 126 — **M5-C19: Preemption, resumption, and the cost of lost progress** — Not started.
  File: [Preemption, resumption, and the cost of lost progress](scheduling-and-queueing/m5-c19-preemption-resumption-and-the-cost-of-lost-progress.md). Category: Scheduling and queueing. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C18, M2-C14. Target concepts: Iteration-boundary preemption, victim selection, retained state versus recomputation, optional swap costs, resume semantics, KV reclamation, anti-thrashing rules, bounded starvation.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 127 — **M5-C20: Cancellation, deadlines, and worker failure** — Not started.
  File: [Cancellation, deadlines, and worker failure](reliability-and-capacity-control/m5-c20-cancellation-deadlines-and-worker-failure.md). Category: Reliability and capacity control. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C19, M2-C16, M5-C06. Target concepts: Queued versus in-flight cancellation, deadline expiry, idempotent terminal transitions, deferred block release, worker error propagation, safe retry boundaries, draining, shutdown, capacity recovery.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 128 — **M5-C21: Streaming results without unbounded buffering** — Not started.
  File: [Streaming results without unbounded buffering](interfaces-protocols-and-streaming/m5-c21-streaming-results-without-unbounded-buffering.md). Category: Interfaces, protocols, and streaming. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C20, M5-C04, M1-C16, M9-C04. Target concepts: Per-request token ordering, result routing, bounded output queues, slow consumers, output backpressure, disconnect handling, completion delivery, generation versus client-visible timing.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 129 — **M5-C22: Designing the scheduler state machine and executor contract** — Not started.
  File: [Designing the scheduler state machine and executor contract](runtime-and-concurrency/m5-c22-designing-the-scheduler-state-machine-and-executor-contract.md). Category: Runtime and concurrency. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C21, M5-C14, M5-C16, M5-C17. Target concepts: Queued, admitted, prefill, decode, preempted and terminal states, event ordering, batch descriptors, completion messages, cache allocator integration, Rust ownership boundaries, failure transitions.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 130 — **M5-C23: Validating scheduling and memory invariants** — Not started.
  File: [Validating scheduling and memory invariants](numerics-and-correctness/m5-c23-validating-scheduling-and-memory-invariants.md). Category: Numerics and correctness. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C22, M2-C20, M4-C19, M9-C22. Target concepts: No lost or duplicate work, legal state transitions, request-token identity, future-growth budget invariants, live KV references, cancellation safety, fairness checks, per-request RNG state, batch-dependent numerical tolerances.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 131 — **M9-C21: Testing cancellation, deadlines, and terminal states** — Not started.
  File: [Testing cancellation, deadlines, and terminal states](reliability-and-capacity-control/m9-c21-testing-cancellation-deadlines-and-terminal-states.md). Category: Reliability and capacity control. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C23, M9-C19. Target concepts: Queued and in-flight cancellation, deadline expiry, disconnects, idempotent cleanup, no post-terminal delivery, bounded cancellation latency, worker errors, reclamation after completion.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 132 — **M9-C23: Testing batch, schedule, and graph invariance** — Not started.
  File: [Testing batch, schedule, and graph invariance](numerics-and-correctness/m9-c23-testing-batch-schedule-and-graph-invariance.md). Category: Numerics and correctness. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C23, M4-C20, M4-C19. Target concepts: Request isolation, batch permutation, varying concurrency, chunked prefill, preemption and resumption, graph versus eager execution, state reset, justified floating-point differences, RNG independence.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 133 — **M9-C26: Load-testing overload, backpressure, and failure recovery** — Not started.
  File: [Load-testing overload, backpressure, and failure recovery](reliability-and-capacity-control/m9-c26-load-testing-overload-backpressure-and-failure-recovery.md). Category: Reliability and capacity control. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C23, M9-C21, M9-C10, M9-C06. Target concepts: Offered-load sweeps, bounded queues, rejection and retry effects, slow consumers, memory exhaustion, worker loss, draining, recovery time, resource leaks, latency and goodput during failures.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 134 — **M5-C24: Comparing scheduling policies on the same arrival trace** — Not started.
  File: [Comparing scheduling policies on the same arrival trace](measurement-experimentation-and-economics/m5-c24-comparing-scheduling-policies-on-the-same-arrival-trace.md). Category: Measurement, experimentation, and economics. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C23, M9-C08, M9-C10, M9-C21, M9-C23, M9-C26, M9-C27. Target concepts: Static, continuous and chunked-prefill configurations, fixed arrivals and request contents, identical resource caps, controlled output demand, causal information boundaries, event tracing, warmup and drain, rejection and unfinished-request accounting.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 135 — **M5-C25: Measuring sustainable capacity, fairness, and tail behavior** — Not started.
  File: [Measuring sustainable capacity, fairness, and tail behavior](measurement-experimentation-and-economics/m5-c25-measuring-sustainable-capacity-fairness-and-tail-behavior.md). Category: Measurement, experimentation, and economics. Phase: 6. Serving, queueing, and load methodology.
  Direct prerequisites: M5-C24, M9-C06, M9-C07, M9-C12. Target concepts: Time to first token, inter-token and total latency distributions, SLO definitions, goodput, completed tokens per second, queue depth, KV occupancy, CPU and GPU profiling, offered-load sweeps, coordinated omission, uncertainty, per-class fairness.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 136 — **M6-C01: Defining an optimization’s correctness and cost contract** — Not started.
  File: [Defining an optimization’s correctness and cost contract](numerics-and-correctness/m6-c01-defining-an-optimization-s-correctness-and-cost-contract.md). Category: Numerics and correctness. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M5-C25, M9-C01, M9-C27. Target concepts: Mechanism, semantic equivalence, numerical approximation, intentional output constraints, reference behavior, resource savings, added overhead, failure cases, workload-dependent benefit.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 137 — **M6-C02: Defining prefix identity through equivalent computation** — Not started.
  File: [Defining prefix identity through equivalent computation](state-memory-and-caching/m6-c02-defining-prefix-identity-through-equivalent-computation.md). Category: State, memory, and caching. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C01, M2-C13. Target concepts: Token prefixes, model and weight versions, adapters, positions, attention masks, cache precision and layout, isolation namespaces, compatibility checks.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 138 — **M6-C03: Tries, radix trees, and longest-prefix matching** — Not started.
  File: [Tries, radix trees, and longest-prefix matching](state-memory-and-caching/m6-c03-tries-radix-trees-and-longest-prefix-matching.md). Category: State, memory, and caching. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C02. Target concepts: Tree nodes and edges, token paths, path compression, longest-prefix lookup, insertion, edge splitting, lookup cost, metadata overhead, RadixAttention concepts.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 139 — **M6-C04: Connecting a radix index to paged KV blocks** — Not started.
  File: [Connecting a radix index to paged KV blocks](state-memory-and-caching/m6-c04-connecting-a-radix-index-to-paged-kv-blocks.md). Category: State, memory, and caching. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C03, M2-C12, M2-C08. Target concepts: Logical prefix ranges, block-granular reuse, partial-block boundaries, tree-to-block mappings, immutable shared prefixes, copy-on-write tails, index and allocator consistency.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 140 — **M6-C05: Reference-safe retention, eviction, and cancellation** — Not started.
  File: [Reference-safe retention, eviction, and cancellation](state-memory-and-caching/m6-c05-reference-safe-retention-eviction-and-cancellation.md). Category: State, memory, and caching. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C04, M2-C14, M5-C20. Target concepts: Request and cache ownership, reference counts, pinning, eviction eligibility, recency policies, memory pressure, cancellation, deferred reclamation, recomputation costs.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 141 — **M6-C06: Balancing cache locality, fairness, and load** — Not started.
  File: [Balancing cache locality, fairness, and load](scheduling-and-queueing/m6-c06-balancing-cache-locality-fairness-and-load.md). Category: Scheduling and queueing. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C05, M5-C16, M5-C07. Target concepts: Prefix-aware ordering, shared-prefix workloads, reuse skew, starvation prevention, cache affinity, queueing versus saved work, worker-load tradeoffs, limits of local policies.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 142 — **M6-C07: Integrating prefix caching into prefill and decode** — Not started.
  File: [Integrating prefix caching into prefill and decode](runtime-and-concurrency/m6-c07-integrating-prefix-caching-into-prefill-and-decode.md). Category: Runtime and concurrency. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C06, M5-C17, M5-C22. Target concepts: Lookup and admission, uncached suffix execution, full-prefix hits and next-token logits, last-token boundary handling, publishing reusable state, concurrent lifetime rules, cancellation, correct uncached fallback.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 143 — **M9-C20: Validating KV reuse and prefix-cache identity** — Not started.
  File: [Validating KV reuse and prefix-cache identity](numerics-and-correctness/m9-c20-validating-kv-reuse-and-prefix-cache-identity.md). Category: Numerics and correctness. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C07, M2-C20, M9-C17. Target concepts: Cached versus uncached references, model and adapter identity, positions and masks, partial and full-prefix hits, copy-on-write, eviction, cache-format changes.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 144 — **M6-C08: Quantization fundamentals: scales, zero points, and rounding** — Not started.
  File: [Quantization fundamentals: scales, zero points, and rounding](numerics-and-correctness/m6-c08-quantization-fundamentals-scales-zero-points-and-rounding.md). Category: Numerics and correctness. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C01, M1-C07, M1-C06. Target concepts: Representable ranges, integer and floating low-bit formats, scale factors, zero points, symmetric and asymmetric schemes, clipping, rounding, dequantization, approximation error.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 145 — **M6-C09: Weight quantization and grouping granularity** — Not started.
  File: [Weight quantization and grouping granularity](numerics-and-correctness/m6-c09-weight-quantization-and-grouping-granularity.md). Category: Numerics and correctness. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C08, M1-C04. Target concepts: Weight-only versus weight-and-activation quantization, per-tensor and per-channel scales, groups, outliers, group-size tradeoffs, metadata bytes, accumulation precision, model-format compatibility.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 146 — **M6-C10: Calibration and representative data selection** — Not started.
  File: [Calibration and representative data selection](numerics-and-correctness/m6-c10-calibration-and-representative-data-selection.md). Category: Numerics and correctness. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C09, M9-C08. Target concepts: Calibration objectives, activation statistics, clipping and scale selection, distribution shift, representative prompts, held-out evaluation, calibration leakage, reproducibility.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 147 — **M6-C11: Packing, dequantization, and quantized kernel execution** — Not started.
  File: [Packing, dequantization, and quantized kernel execution](kernels-compilers-and-execution/m6-c11-packing-dequantization-and-quantized-kernel-execution.md). Category: Kernels, compilers, and execution. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C10, M4-C10, M3-C09. Target concepts: Bit packing, alignment and padding, group metadata, fused versus separate dequantization, compute paths, hardware support, kernel eligibility, conversion overhead, effective memory savings.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 148 — **M6-C12: KV-cache quantization and attention numerics** — Not started.
  File: [KV-cache quantization and attention numerics](numerics-and-correctness/m6-c12-kv-cache-quantization-and-attention-numerics.md). Category: Numerics and correctness. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C11, M2-C03, M1-C10. Target concepts: Key versus value distributions, per-token and per-channel scales, cache writes and reads, residual high-precision regions, long-context error, metadata and conversion costs, cache identity.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 149 — **M6-C13: Validating quantization quality and memory savings** — Not started.
  File: [Validating quantization quality and memory savings](numerics-and-correctness/m6-c13-validating-quantization-quality-and-memory-savings.md). Category: Numerics and correctness. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C12, M9-C17, M9-C15, M9-C11. Target concepts: Floating-reference comparisons, layer and logit errors, perplexity and task quality, long-context evaluation, quality thresholds, held-out workloads, actual allocation accounting, failure cases.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 150 — **M6-C14: Draft proposals and parallel target verification** — Not started.
  File: [Draft proposals and parallel target verification](model-computation-and-semantics/m6-c14-draft-proposals-and-parallel-target-verification.md). Category: Model computation and semantics. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C01, M1-C15, M1-C18. Target concepts: Draft and target models, proposal length, autoregressive draft generation, causal target scoring, conditional distributions, accepted prefixes, bonus or correction tokens, stopping rules.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 151 — **M6-C15: Distribution-preserving speculative acceptance** — Not started.
  File: [Distribution-preserving speculative acceptance](numerics-and-correctness/m6-c15-distribution-preserving-speculative-acceptance.md). Category: Numerics and correctness. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C14, M1-C06, M4-C19. Target concepts: Target and proposal probabilities, acceptance ratios, sequential acceptance, first rejection, positive-part residual distribution, all-accepted bonus sampling, support edge cases, greedy versus stochastic contracts.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 152 — **M6-C16: Managing draft and target state during speculation** — Not started.
  File: [Managing draft and target state during speculation](runtime-and-concurrency/m6-c16-managing-draft-and-target-state-during-speculation.md). Category: Runtime and concurrency. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C15, M2-C12, M5-C20. Target concepts: Separate KV states, tentative versus committed tokens, accepted-prefix commits, rejected-tail rollback, token positions, RNG ownership, EOS and stop boundaries, cancellation, memory budgets.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 153 — **M9-C18: Testing sampling distributions and random-state behavior** — Not started.
  File: [Testing sampling distributions and random-state behavior](numerics-and-correctness/m9-c18-testing-sampling-distributions-and-random-state-behavior.md). Category: Numerics and correctness. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C16, M4-C19, M9-C07. Target concepts: Greedy versus stochastic contracts, seeds and per-request RNG ownership, empirical probabilities, support checks, goodness-of-fit and uncertainty, distribution versus token-sequence equivalence, speculative acceptance.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 154 — **M6-C17: When speculative decoding helps or hurts** — Not started.
  File: [When speculative decoding helps or hurts](measurement-experimentation-and-economics/m6-c17-when-speculative-decoding-helps-or-hurts.md). Category: Measurement, experimentation, and economics. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C16, M9-C18, M9-C05, M9-C11. Target concepts: Draft cost, target verification cost, acceptance rate and accepted length, useful output tokens, proposal length, batch and context effects, shared-resource contention, extra memory, break-even workloads.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 155 — **M6-C18: Grammar-constrained decoding from tokens to parser state** — Not started.
  File: [Grammar-constrained decoding from tokens to parser state](interfaces-protocols-and-streaming/m6-c18-grammar-constrained-decoding-from-tokens-to-parser-state.md). Category: Interfaces, protocols, and streaming. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C01, M1-C02, M1-C15. Target concepts: Regular versus context-free languages, finite-state machines and parser stacks, token-to-byte transitions, grammar state, valid continuations, accepting states, tokenizer compatibility.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 156 — **M6-C19: Grammar compilation and vocabulary-mask execution** — Not started.
  File: [Grammar compilation and vocabulary-mask execution](interfaces-protocols-and-streaming/m6-c19-grammar-compilation-and-vocabulary-mask-execution.md). Category: Interfaces, protocols, and streaming. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C18, M4-C10. Target concepts: Grammar and schema compilation, mask generation, token filtering, mask caching, state advancement, CPU-GPU coordination, preprocessing versus per-token overhead, constraint and sampling order.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 157 — **M6-C20: Structured-output validity, termination, and failure** — Not started.
  File: [Structured-output validity, termination, and failure](interfaces-protocols-and-streaming/m6-c20-structured-output-validity-termination-and-failure.md). Category: Interfaces, protocols, and streaming. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C19, M9-C19. Target concepts: Syntactic validity versus semantic correctness, incomplete outputs, empty allowed-token sets, EOS legality, unsupported schema features, compilation failures, length limits, cancellation, explicit failure contracts.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 158 — **M6-C21: LoRA foundations and adapter-specific computation** — Not started.
  File: [LoRA foundations and adapter-specific computation](model-computation-and-semantics/m6-c21-lora-foundations-and-adapter-specific-computation.md). Category: Model computation and semantics. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C01, M1-C04, M1-C14. Target concepts: Low-rank updates, base weights, adapter matrices, rank and scaling, target layers, merged versus unmerged computation, adapter identity, reference outputs, heterogeneous adapter requests.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 159 — **M6-C22: Adapter residency, lifetime, and cache compatibility** — Not started.
  File: [Adapter residency, lifetime, and cache compatibility](state-memory-and-caching/m6-c22-adapter-residency-lifetime-and-cache-compatibility.md). Category: State, memory, and caching. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C21, M6-C02, M2-C11, M5-C20. Target concepts: Adapter loading and residency, host versus device storage, versioned identities, in-flight references, eviction, load failures, adapter-aware KV reuse, memory competition with KV state.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 160 — **M6-C23: Batching requests across multiple LoRA adapters** — Not started.
  File: [Batching requests across multiple LoRA adapters](scheduling-and-queueing/m6-c23-batching-requests-across-multiple-lora-adapters.md). Category: Scheduling and queueing. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C22, M5-C12, M5-C13. Target concepts: Adapter selection, heterogeneous ranks, low-rank batched operations, grouping versus mixing, dispatch and padding costs, locality versus fairness, rare adapters, memory-aware admission.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 161 — **M6-C24: Composing optimizations without breaking contracts** — Not started.
  File: [Composing optimizations without breaking contracts](runtime-and-concurrency/m6-c24-composing-optimizations-without-breaking-contracts.md). Category: Runtime and concurrency. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C07, M6-C13, M6-C17, M6-C20, M6-C23. Target concepts: Prefix caching with adapters and quantized state, constrained speculative distributions, graph and shape compatibility, conversion boundaries, RNG and grammar ownership, interaction tests, incremental feature enablement.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 162 — **M6-C25: Handling unsupported cases and optimization failures** — Not started.
  File: [Handling unsupported cases and optimization failures](reliability-and-capacity-control/m6-c25-handling-unsupported-cases-and-optimization-failures.md). Category: Reliability and capacity control. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C24, M5-C20. Target concepts: Capability checks, invalidated cache identities, missing adapters, grammar errors, allocation failures, safe fallback versus explicit rejection, cancellation, cleanup, bounded recovery costs.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 163 — **M9-C24: Validating approximate and constrained optimization paths** — Not started.
  File: [Validating approximate and constrained optimization paths](numerics-and-correctness/m9-c24-validating-approximate-and-constrained-optimization-paths.md). Category: Numerics and correctness. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C25, M9-C18, M9-C20. Target concepts: Weight and KV quantization quality, held-out evaluation, long-context effects, speculative target distributions, grammar validity, adapter-specific references, capability guards, equivalent fallback versus explicit error.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 164 — **M6-C26: Designing the optimization workload and comparison matrix** — Not started.
  File: [Designing the optimization workload and comparison matrix](measurement-experimentation-and-economics/m6-c26-designing-the-optimization-workload-and-comparison-matrix.md). Category: Measurement, experimentation, and economics. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C25, M9-C08, M9-C11, M9-C24. Target concepts: Prefix reuse and skew, context and output lengths, arrivals and concurrency, precision settings, draft agreement, grammar complexity, adapter mix, fixed resource budgets, cold and warm runs, ablations.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 165 — **M6-C27: Building prefix caching and one additional optimization** — Not started.
  File: [Building prefix caching and one additional optimization](runtime-and-concurrency/m6-c27-building-prefix-caching-and-one-additional-optimization.md). Category: Runtime and concurrency. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C26, M9-C20, M5-C23. Target concepts: Prefix-cache baseline integration, choosing weight or KV quantization, speculation, structured decoding or multi-LoRA, staged validation gates, runtime contracts, feature controls, reproducible configuration, no-code build specification.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 166 — **M6-C28: Establishing end-to-end benefit and regression boundaries** — Not started.
  File: [Establishing end-to-end benefit and regression boundaries](measurement-experimentation-and-economics/m6-c28-establishing-end-to-end-benefit-and-regression-boundaries.md). Category: Measurement, experimentation, and economics. Phase: 7. Cache reuse and advanced optimizations.
  Direct prerequisites: M6-C27, M9-C06, M9-C27. Target concepts: Correctness and quality gates, first-token and inter-token latency, tail distributions, goodput, capacity, CPU and GPU overhead, actual memory, compilation and loading amortization, fairness, cost, uncertainty, helps-versus-hurts results.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 167 — **M7-C01: Why distribute inference across GPUs?** — Not started.
  File: [Why distribute inference across GPUs?](parallelism-and-decomposition/m7-c01-why-distribute-inference-across-gpus.md). Category: Parallelism and decomposition. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M6-C28, M3-C23, M5-C25. Target concepts: Model fit, aggregate capacity, single-request latency, replicas versus sharding, strong versus weak scaling, communication overhead, two-GPU versus single-GPU goals.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 168 — **M7-C02: Mapping GPU and network topology before partitioning** — Not started.
  File: [Mapping GPU and network topology before partitioning](hardware-architecture-and-topology/m7-c02-mapping-gpu-and-network-topology-before-partitioning.md). Category: Hardware architecture and topology. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C01, M3-C13, M9-C16. Target concepts: GPU memory and capability, PCIe and NVLink paths, switches, NUMA placement, NIC affinity, intra-node versus inter-node links, peer access, measured versus advertised bandwidth.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 169 — **M7-C03: Workers, ranks, process groups, and communicators** — Not started.
  File: [Workers, ranks, process groups, and communicators](runtime-and-concurrency/m7-c03-workers-ranks-process-groups-and-communicators.md). Category: Runtime and concurrency. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C02, M5-C03, M5-C06. Target concepts: Worker processes, global and local ranks, device assignment, process groups, communicator membership, initialization and rendezvous, stream ownership, Rust and backend integration boundaries.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 170 — **M7-C04: Point-to-point transfers and communication contracts** — Not started.
  File: [Point-to-point transfers and communication contracts](networking-and-communication/m7-c04-point-to-point-transfers-and-communication-contracts.md). Category: Networking and communication. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C03, M3-C14, M3-C11. Target concepts: Send and receive matching, tensor shapes and dtypes, buffer ownership, asynchronous submission and completion, peer access versus host staging, ordering, backpressure.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 171 — **M7-C05: Reductions and AllReduce from first principles** — Not started.
  File: [Reductions and AllReduce from first principles](networking-and-communication/m7-c05-reductions-and-allreduce-from-first-principles.md). Category: Networking and communication. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C04, M1-C06, M1-C07. Target concepts: Elementwise reductions across ranks, sum and maximum, replicated results, collective participation and ordering, shape compatibility, floating-point reduction order.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 172 — **M7-C06: AllGather and ReduceScatter as layout transformations** — Not started.
  File: [AllGather and ReduceScatter as layout transformations](networking-and-communication/m7-c06-allgather-and-reducescatter-as-layout-transformations.md). Category: Networking and communication. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C05, M1-C05. Target concepts: Sharded and replicated tensors, rank-ordered concatenation, reduce-and-partition semantics, buffer sizes, AllReduce decomposition, divisibility and padding, ownership of output shards.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 173 — **M7-C07: AllToAll and variable-size token exchange** — Not started.
  File: [AllToAll and variable-size token exchange](networking-and-communication/m7-c07-alltoall-and-variable-size-token-exchange.md). Category: Networking and communication. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C06. Target concepts: Per-destination partitions, dispatch and combine patterns, send and receive counts, variable-size exchanges, packing and unpacking, permutation metadata, imbalance, backend capability limits.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 174 — **M7-C08: Modeling communication latency and bandwidth costs** — Not started.
  File: [Modeling communication latency and bandwidth costs](networking-and-communication/m7-c08-modeling-communication-latency-and-bandwidth-costs.md). Category: Networking and communication. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C07, M3-C16. Target concepts: Message size, startup latency, effective bandwidth, alpha-beta models, rank count, algorithm-dependent traffic and steps, rings and trees, small versus large messages, topology and contention.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 175 — **M7-C09: Overlapping compute and communication safely** — Not started.
  File: [Overlapping compute and communication safely](runtime-and-concurrency/m7-c09-overlapping-compute-and-communication-safely.md). Category: Runtime and concurrency. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C08, M3-C12. Target concepts: Dependency graphs, independent work, streams and completion events, buffer lifetimes, shared compute and memory resources, exposed versus hidden communication, stragglers, limits of overlap.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 176 — **M9-C14: Measuring transfer and collective completion** — Not started.
  File: [Measuring transfer and collective completion](networking-and-communication/m9-c14-measuring-transfer-and-collective-completion.md). Category: Networking and communication. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C09, M9-C02, M9-C16. Target concepts: Payload and transport bytes, message sizes, link utilization, communication latency, rank waiting, asynchronous completion, compute overlap, exposed communication, cross-worker trace correlation.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 177 — **M7-C10: Tensor parallelism for linear layers** — Not started.
  File: [Tensor parallelism for linear layers](parallelism-and-decomposition/m7-c10-tensor-parallelism-for-linear-layers.md). Category: Parallelism and decomposition. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C06, M1-C04, M9-C14. Target concepts: Row and column partitioning, weight and activation shards, partial outputs, collective placement, replication, layer boundaries, frequent communication, shape compatibility.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 178 — **M7-C11: Tensor-parallel attention and KV ownership** — Not started.
  File: [Tensor-parallel attention and KV ownership](parallelism-and-decomposition/m7-c11-tensor-parallel-attention-and-kv-ownership.md). Category: Parallelism and decomposition. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C10, M2-C02, M2-C03. Target concepts: Query and KV head partitioning, MHA and GQA constraints, replicated versus sharded KV state, head-count divisibility, output projection, position and mask consistency, rank-local cache budgets.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 179 — **M7-C12: Pipeline parallelism for inference** — Not started.
  File: [Pipeline parallelism for inference](parallelism-and-decomposition/m7-c12-pipeline-parallelism-for-inference.md). Category: Parallelism and decomposition. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C04, M1-C14, M1-C18. Target concepts: Layer partitions, stage interfaces, activation transfers, per-stage KV state, forward-only execution, microbatches, request-token identity, autoregressive feedback dependencies.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 180 — **M7-C13: Pipeline bubbles, stage balance, and scheduling** — Not started.
  File: [Pipeline bubbles, stage balance, and scheduling](scheduling-and-queueing/m7-c13-pipeline-bubbles-stage-balance-and-scheduling.md). Category: Scheduling and queueing. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C12, M5-C10, M5-C13. Target concepts: Fill and drain, idle slots, stage imbalance, microbatch count and size, decode dependencies, queueing between stages, throughput versus single-request latency, tail effects.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 181 — **M7-C14: Data parallelism across serving replicas** — Not started.
  File: [Data parallelism across serving replicas](parallelism-and-decomposition/m7-c14-data-parallelism-across-serving-replicas.md). Category: Parallelism and decomposition. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C03, M5-C22. Target concepts: Request partitioning, replicated model weights, independent worker queues, replica-local KV caches, capacity scaling, single-request limits, shared resource contention.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 182 — **M7-C15: Routing requests with load and cache locality** — Not started.
  File: [Routing requests with load and cache locality](distributed-coordination-and-routing/m7-c15-routing-requests-with-load-and-cache-locality.md). Category: Distributed coordination and routing. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C14, M6-C06, M5-C15. Target concepts: Discovery and membership, replica selection, outstanding work versus request counts, prefix affinity, stale telemetry, reservations, locality versus fairness, overload and retry routing.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 183 — **M7-C16: Mixture-of-experts computation and storage** — Not started.
  File: [Mixture-of-experts computation and storage](model-computation-and-semantics/m7-c16-mixture-of-experts-computation-and-storage.md). Category: Model computation and semantics. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M1-C13, M1-C15, M7-C01. Target concepts: Routers and expert selection, top-k expert activation, shared versus routed experts, total parameters, active computation, stored weights, routing weights, sparse-compute limits.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 184 — **M7-C17: Expert parallelism and dispatch-combine execution** — Not started.
  File: [Expert parallelism and dispatch-combine execution](parallelism-and-decomposition/m7-c17-expert-parallelism-and-dispatch-combine-execution.md). Category: Parallelism and decomposition. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C16, M7-C07. Target concepts: Expert placement, token routing, AllToAll dispatch, grouped expert computation, weighted combine, token permutation, expert replication choices, communication and storage costs.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 185 — **M7-C18: Expert imbalance, capacity, and token correctness** — Not started.
  File: [Expert imbalance, capacity, and token correctness](scheduling-and-queueing/m7-c18-expert-imbalance-capacity-and-token-correctness.md). Category: Scheduling and queueing. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C17, M5-C16. Target concepts: Hot experts, skewed token routing, variable expert batches, straggler ranks, capacity limits, padding, load redistribution costs, token dropping versus model-preserving handling.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 186 — **M7-C19: Context parallelism and distributed attention state** — Not started.
  File: [Context parallelism and distributed attention state](parallelism-and-decomposition/m7-c19-context-parallelism-and-distributed-attention-state.md). Category: Parallelism and decomposition. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C11, M7-C09, M4-C07, M1-C11. Target concepts: Sequence partitions, query versus KV partitioning, attention communication, ring exchange or partial-output reductions, online-softmax merging, causal masks, positions, prefill versus decode differences.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 187 — **M7-C20: Combining parallelism strategies and placement** — Not started.
  File: [Combining parallelism strategies and placement](parallelism-and-decomposition/m7-c20-combining-parallelism-strategies-and-placement.md). Category: Parallelism and decomposition. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C13, M7-C15, M7-C18, M7-C19. Target concepts: TP, PP, DP, EP and CP groups, rank mapping, nested partitioning, topology-aware placement, compatible dimensions, replicated versus sharded state, communication domains.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 188 — **M7-C21: Distributed weights, KV caches, and memory accounting** — Not started.
  File: [Distributed weights, KV caches, and memory accounting](state-memory-and-caching/m7-c21-distributed-weights-kv-caches-and-memory-accounting.md). Category: State, memory, and caching. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C20, M9-C15, M6-C22. Target concepts: Shard loading, model and adapter identity, rank-local weights, KV partitions, replicated metadata, communication buffers, workspace peaks, transfer staging, headroom, ownership and reclamation.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 189 — **M7-C22: Coordinating requests and execution across workers** — Not started.
  File: [Coordinating requests and execution across workers](distributed-coordination-and-routing/m7-c22-coordinating-requests-and-execution-across-workers.md). Category: Distributed coordination and routing. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C21, M5-C22. Target concepts: Request and iteration IDs, agreed batch membership, control-plane versus data-plane messages, metadata consistency, stale events, epochs, completion aggregation, cancellation propagation.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 190 — **M7-C23: Collective failures, timeouts, and recovery boundaries** — Not started.
  File: [Collective failures, timeouts, and recovery boundaries](reliability-and-capacity-control/m7-c23-collective-failures-timeouts-and-recovery-boundaries.md). Category: Reliability and capacity control. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C22, M7-C05, M5-C20. Target concepts: Rank mismatch, divergent collective ordering, hung or failed workers, stragglers, asynchronous errors, timeout scopes, coordinated abort, retry boundaries, lost volatile state, safe cleanup.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 191 — **M7-C24: Prefill-decode disaggregation and its tradeoffs** — Not started.
  File: [Prefill-decode disaggregation and its tradeoffs](parallelism-and-decomposition/m7-c24-prefill-decode-disaggregation-and-its-tradeoffs.md). Category: Parallelism and decomposition. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C23, M1-C18, M7-C08. Target concepts: Separate phase workers, compute and memory specialization, interference reduction, extra queues, KV transfer volume, resource split, latency objectives, workload-dependent benefit.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 192 — **M7-C25: Transferring KV state with a safe handoff** — Not started.
  File: [Transferring KV state with a safe handoff](networking-and-communication/m7-c25-transferring-kv-state-with-a-safe-handoff.md). Category: Networking and communication. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C24, M2-C10, M7-C21. Target concepts: Source and destination identities, cache format and shard compatibility, block mapping, receiver reservations, bulk transfer and metadata, completion versus submission, ownership commit, cancellation and partial failures.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 193 — **M7-C26: Balancing disaggregated stages and transfer capacity** — Not started.
  File: [Balancing disaggregated stages and transfer capacity](distributed-coordination-and-routing/m7-c26-balancing-disaggregated-stages-and-transfer-capacity.md). Category: Distributed coordination and routing. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C25, M7-C15, M9-C06. Target concepts: Prefill and decode pool sizing, phase-aware routing, KV availability, receiving capacity, bandwidth bottlenecks, reservations, stale telemetry, backpressure, admission and tail-latency objectives.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 194 — **M7-C27: Validating distributed computation and state** — Not started.
  File: [Validating distributed computation and state](numerics-and-correctness/m7-c27-validating-distributed-computation-and-state.md). Category: Numerics and correctness. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C26, M9-C17, M9-C18, M9-C22, M9-C23. Target concepts: Single-device reference outputs, reduction tolerances, rank and shard reconstruction, token and expert routing identity, causal masks, KV consistency, cancellation and fault tests, RNG ownership.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 195 — **M7-C28: Running a model across two GPUs** — Not started.
  File: [Running a model across two GPUs](runtime-and-concurrency/m7-c28-running-a-model-across-two-gpus.md). Category: Runtime and concurrency. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C27, M7-C10, M7-C12. Target concepts: Supported backend selection, device and rank setup, model and shard compatibility, two-way tensor or pipeline partitioning, weight loading, collective readiness, correctness gates, startup and shutdown contracts.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 196 — **M7-C29: Profiling compute, communication, and waiting** — Not started.
  File: [Profiling compute, communication, and waiting](measurement-experimentation-and-economics/m7-c29-profiling-compute-communication-and-waiting.md). Category: Measurement, experimentation, and economics. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C28, M9-C14, M9-C12. Target concepts: Per-rank timelines, kernel and collective durations, host waits, overlap, exposed communication, critical-path attribution, timestamp correlation, profiler overhead, avoiding double-counted elapsed time.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 197 — **M7-C30: When adding a GPU reduces latency and when it does not** — Not started.
  File: [When adding a GPU reduces latency and when it does not](measurement-experimentation-and-economics/m7-c30-when-adding-a-gpu-reduces-latency-and-when-it-does-not.md). Category: Measurement, experimentation, and economics. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C29, M9-C06, M9-C11, M9-C07. Target concepts: Matched single-GPU and two-GPU workloads, message-size sweeps, prefill and decode timing, strong and weak scaling, latency distributions, useful throughput, memory capacity, cost, topology, load balance, uncertainty.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 198 — **M9-C28: Evaluating cost and energy per useful result** — Not started.
  File: [Evaluating cost and energy per useful result](measurement-experimentation-and-economics/m9-c28-evaluating-cost-and-energy-per-useful-result.md). Category: Measurement, experimentation, and economics. Phase: 8. Distributed inference and economics.
  Direct prerequisites: M7-C30, M9-C06, M9-C15, M9-C16. Target concepts: Resource-time accounting, cost per completed and SLO-compliant request, output-token normalization, idle and reserved capacity, measured energy and telemetry limits, quality-adjusted comparisons, uncertainty.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 199 — **M9-C25: Validating the text-generation serving pipeline end to end** — Not started.
  File: [Validating the text-generation serving pipeline end to end](numerics-and-correctness/m9-c25-validating-the-text-generation-serving-pipeline-end-to-end.md). Category: Numerics and correctness. Phase: 9. Integrated serving validation and final synthesis.
  Direct prerequisites: M6-C24, M9-C19, M9-C20, M9-C24, M5-C21, M7-C27, M9-C21, M9-C26. Target concepts: Tokenizer and template identity, prompt preparation, prefill and decode, cache and scheduler integration, request-token identity, streamed output and stopping, single-GPU and multi-GPU reference comparisons, invalid inputs, terminal-state and resource-cleanup checks.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 200 — **M9-C29: Validating the nine integrated build milestones** — Not started.
  File: [Validating the nine integrated build milestones](measurement-experimentation-and-economics/m9-c29-validating-the-nine-integrated-build-milestones.md). Category: Measurement, experimentation, and economics. Phase: 9. Integrated serving validation and final synthesis.
  Direct prerequisites: M9-C25, M7-C30, M6-C28, M9-C26, M9-C23. Target concepts: Single-request reference, KV and static batching, cancellation, paging, prefix reuse and chunking, kernel and graph changes, quantization or speculation, multi-GPU execution, text-generation serving API acceptance gates.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.

- [ ] 201 — **M9-C30: Publishing a reproducible correctness and performance report** — Not started.
  File: [Publishing a reproducible correctness and performance report](measurement-experimentation-and-economics/m9-c30-publishing-a-reproducible-correctness-and-performance-report.md). Category: Measurement, experimentation, and economics. Phase: 9. Integrated serving validation and final synthesis.
  Direct prerequisites: M9-C29, M9-C28, M9-C27, M9-C13. Target concepts: Experiment manifests, hardware and software identities, workload traces, metric definitions, outcome populations, distributions and uncertainty, memory breakdowns, profiling evidence, quality results, limitations, helps-versus-hurts conclusions.
  Stages: Concepts — Not started; Experiments — Not started; Verification — Not started; Review and documentation build — Not started.
  Module 9 application: Not selected; choose the chapter-relevant guidance from the support policy below before drafting. Updated: Not started. Evidence: None. Next action: Confirm prerequisites and research sources when this becomes the first incomplete chapter.


## Surprises & Discoveries

Observation (2026-10-24 21:35 IST): primary specifications have different default normalization groups: SciPy 1.16.2 softmax uses the whole array by default, while ONNX Softmax-13 defaults to the last axis. M1-C06 therefore declares every axis. The [0, −1000] fixture also demonstrates that a zero output tail can pass absolute-probability gates while losing all of its relative value; the chapter records both rather than claiming maximum shifting removes all underflow.

Observation (2026-10-24 21:21 IST): a transpose need not be non-contiguous in every order: this chapter's dense C-order (2, 3) array becomes F-contiguous after transposition. C-order flattening of that transpose still needs a copy because its original byte-position differences alternate 12 and −8. Browser review also exposed cramped product limits and arrow/label overlap; both were corrected and visually rechecked. The interrupted preview was restarted before final review.

Observation (2026-10-24 19:04 IST): shape compatibility alone does not establish projection equivalence. M1-C04 uses an explicitly transposed stored-weight example and a shape-compatible wrong-orientation negative control. Its E4 fixtures bound every partial sum to 512, allowing exact binary32 checks without prematurely teaching general numerical tolerances.


Observation (2026-10-24 18:41 IST): the reported GitHub failure exactly matches HEAD:mkdocs.yml, which omits the inventory, authoring order and execution-plan pages and still references the removed multimodal M9-C25 path. The working-tree mkdocs.yml already contains all four navigation corrections but is not committed. Evidence: committed-config reproduction exits 1 with the same two warning groups; the working-tree strict build exits 0 without warnings (4.02 seconds). Earlier local validation used the working tree, so it did not establish that the committed configuration would pass CI.

Observation (2026-10-24 18:36 IST): coordinate labels must be checked against the entire fixture range. In the longer (8, 128, 64) fixture, 10000b + 100s + j would give the same label to (1, 0, 0) and (0, 100, 0). The final 100000b + 100s + j labels were independently checked for all 65,536 coordinates: unique, maximum 712763, and exactly representable in binary32. This validates the teaching fixture, not runtime performance. The local preview required a restart; full SVG asset screenshots completed the diagram review after page scrolling proved unreliable.

Observation (2026-10-24 18:16 IST): the pinned Qwen tokenizer metadata lists 131072 maximum length while model configuration lists 32768 maximum positions. Its template also supplies a default system message when absent. Evidence: snapshot tokenizer_config.json and config.json. M1-C02 therefore checks full prepared length against a declared model/runtime budget rather than trusting tokenizer metadata or content-only counts. Direct template-to-IDs does not by itself prove that internal text rendering or copying is absent.

Observation (2026-10-24 17:39 IST): the pinned example checkpoint enables sampling in its generation defaults and lists two EOS IDs, while model configuration lists one. The chapter therefore declares effective greedy settings and a compatible explicit EOS list. Evidence: the Qwen snapshot generation_config.json and config.json in commit eaa56b503cc0a8a4d15de1dd8bd2a7e95a716be2. The preview process also ended during review; restarting it and refreshing confirmed the final diagram and caption rather than a cached draft.

Observation (2026-10-24 17:21 IST): all 201 existing chapter files are still labelled Outline. Evidence: the inventory and ordered schedule each contain 201 chapter IDs, and the source files read during plan preparation contain the outline status banner. Consequently this plan starts at zero completed chapters; the inventory and dependency work completed earlier do not count as detailed chapter completion.

Observation (2026-10-24 17:21 IST): Module 9 numbering does not make it a final isolated module. Its foundational chapters occur throughout the schedule; later validation treatments depend on mechanisms introduced in Modules 1–7. The final M9-C25 outline now concerns text-generation serving, and M9-C29 retains nine integration milestones with text-generation API validation as the ninth. There is no pending Module 8 prerequisite.


Observation (2026-10-24 17:23 IST): the documentation preview retains the /InferX-docs/ path from the configured site URL. Evidence: the unprefixed plan address rendered a 404 page; following Home and its Chapter execution plan and progress link rendered the plan at the prefixed address. Updated Concrete Steps with the verified URL. The current Markdown setup displays task markers as text, so progress changes are made in the source plan.


## Decision Log

Decision (2026-10-24 21:35 IST, Codex): use explicit FP64 synthetic fixtures and 80/120-digit references for M1-C06, with declared per-coordinate, total-mass and near-zero error budgets. Reject empty/non-finite groups as an exercise policy and defer masking and general floating-point analysis to their assigned chapters. Rationale: this keeps stability, axis semantics and evidence understandable without silently introducing approximations or treating arbitrary library defaults as the serving contract.

Decision (2026-10-24 21:21 IST, Codex): use explicit C logical enumeration, byte strides and independent numeric output as M1-C05's contract. Separate logical element bytes, unique backing allocations and allocator reserves; benchmark packing through completed consumption and temporary release. Rationale: these distinctions prevent shape equality, metadata timing and view sizes from being mistaken for semantic equivalence, full latency or capacity evidence. Keep unsafe lifetime failures as rejected traces or supported runtime fault cases.

Decision (2026-10-24 19:04 IST, Codex): distinguish shared projections, distinct per-batch weights and affine bias explicitly. Compare only already-ready rows in E4; treat batch-formation waiting separately. Rationale: algebraic batching equivalence does not establish safe request identity, absence of copies, or caller-latency improvement.


Decision (2026-10-24 18:41 IST, Codex): retain strict navigation validation and the existing corrected root configuration; no workflow or chapter changes are needed for the reported failure. Rationale: publishing the missing mkdocs.yml changes resolves the observed discrepancy. Future handoffs must identify required uncommitted configuration changes and distinguish local build evidence from committed/remote CI evidence. Do not commit or push automatically.

Decision (2026-10-24 18:36 IST, Codex): teach logical shape/axis/index contracts and basic Rust ownership representations before physical layouts and matrix arithmetic. Rationale: M1-C05 owns strides and views, while M1-C04 owns multiplication. Use a logical enumeration ordinal without claiming a general memory-address formula. Keep Rust names and representation descriptions as prose, with three experiment designs and no implementation. Supplement shape checks with exact coordinate labels and preserve scalar, zero-extent and unknown-shape distinctions.

Decision (2026-10-24 18:16 IST, Codex): use constructed ID and byte examples plus four existing-tool experiment designs for M1-C02. Rationale: exact identity, template equivalence, incremental display and preparation performance need distinct checks, without supplying implementation or inventing ordinary-text checkpoint IDs. Choose explicit exercise policies for invalid inputs and reserved-marker user content, and keep these separate from raw library behavior. Preserve fixed documentation versions as explanatory references without asserting package compatibility.

Decision (2026-10-24 17:39 IST, Codex): use one hand-traced experiment plus two inspectable-tool experiment designs for the introductory chapter. Rationale: these exercise every target concept without requiring an implementation or claiming later Module 9 chapters are detailed. Pin a small concrete checkpoint, keep hardware requirements illustrative, and separate initialization-inclusive caller timing from service latency. Preserve existing user changes; no commits or publication are part of chapter completion.

Decision: preserve all 201 chapter IDs and their existing category locations, and use the exact authoring positions recorded in this plan. Rationale: the existing dependency-aware schedule has already resolved ordering and interleaved Module 9; renumbering would break traceability. Date/Author: 2026-10-24 17:21 IST, Codex, following the user's established curriculum scope.

Decision: maintain one authoritative progress ledger here and at most one active chapter. Rationale: the user explicitly requires one chapter at a time and requires the execution plan to track each chapter. Do not delegate chapter drafting or begin research/drafting for another chapter while one is active. Date/Author: 2026-10-24 17:21 IST, Codex.

Decision: interpret completion as reviewed educational content and validated documentation, not successful execution of an implemented inference engine. Rationale: the user explicitly prohibits implementation code. Experiments describe how evidence would be collected; results can be labelled observed only if actually supplied or measured. Date/Author: 2026-10-24 17:21 IST, Codex.

Decision: use the uploaded PLANS.md as the plan-format and maintenance reference, while applying the user's chapter-specific instructions over its generic software implementation examples. Rationale: copying a reference document does not authorize unrelated prototypes, parallel implementation, automatic commits, or publication. Date/Author: 2026-10-24 17:21 IST, Codex.

Decision: create and validate the plan now with all chapter stages unstarted. Rationale: the current request is to create the execution plan; recording a chapter as active or complete would misrepresent progress. A subsequent request to execute the plan starts at the recorded next chapter and proceeds sequentially within the authorized scope. Date/Author: 2026-10-24 17:21 IST, Codex.


## Outcomes & Retrospective

Chapter outcome (2026-10-24 21:35 IST): M1-C06 is Complete with all ten target concepts, worked reduction/probability/range/shift examples, two diagrams, four experiment designs and matched verification, six dimensions, eight principles, primary references and hardware requirements. Independent arithmetic/high-precision checks, strict build and rendered-page review passed. Totals: 6/201 complete, 195 not started, no active chapter; M1-C07 is next. Runtime benchmark and production-tail claims remain unmade.

Chapter outcome (2026-10-24 21:21 IST): M1-C05 is Complete, including all eight target concepts, addressing/layout/reshape/broadcast/lifetime examples, three diagrams, four experiment designs and matched verification, six dimensions, eight principles and primary references/hardware requirements. Arithmetic/content checks, strict build and rendered chapter/diagram review passed. Totals: 5/201 complete, 196 not started, no active chapter. M1-C06 is next. Runtime performance studies remain proposed.

Chapter outcome (2026-10-24 19:04 IST): M1-C04 is Complete with six target concepts, worked formulas, three diagrams, four experiment designs and matched verification, all six dimensions and eight principles, primary references and hardware requirements. Arithmetic, strict build and rendered-page/diagram review passed. Current totals: 4/201 complete, 197 not started, no active chapter. M1-C05 is next. All runtime performance experiments remain proposed.


Build-maintenance outcome (2026-10-24 18:41 IST): diagnosed and reproduced the reported failure from committed navigation. The complete correction is the existing mkdocs.yml diff: three Home entries plus the renamed text-generation M9-C25 entry. The working-tree strict build passes; the root configuration must be included in the next commit and push before GitHub can use that correction. No GitHub rerun or deployment result is asserted. Chapter progress remains 3/201 complete, with M1-C04 next.

Chapter outcome (2026-10-24 18:36 IST): M1-C03 is Complete. It supplies all nine target concepts, worked scalar/count/index/padding/byte/latency examples, two diagrams, basic Rust representation contracts, three experiments with matched verification, all six dimensions and eight principles, primary references and CPU requirements. Content review, independent numerical checks, strict build and browser/diagram review passed. Current totals are 3/201 complete, 198 not started and no active chapter; M1-C04 is next. Remaining chapters are untouched; all runtime performance studies remain proposed.

Chapter outcome (2026-10-24 18:16 IST): M1-C02 is Complete. It explains all seven target concepts with worked byte/ID, template-overhead, context-budget, storage and latency calculations, two diagrams, four experiment designs, matched verification and introductory Module 9 support. Strict build and rendered-page review passed. Current totals are 2/201 complete, 199 not started, and no active chapter; M1-C03 is next. Exact identity is the acceptance boundary; displayed-text equality and faster preparation alone cannot establish preserved inference behavior or an end-to-end improvement. All performance experiments remain proposed.

Chapter outcome (2026-10-24 17:39 IST): M1-C01 is Complete, with foundational explanations, worked probability/storage/timing calculations, two SVG diagrams, three experiment designs and corresponding verification, six dimensions, eight principles, primary references, hardware requirements, and introductory Module 9 support. Content, strict build, and rendered-page gates passed. Current totals are 1/201 complete and 200 not started; M1-C02 is next, with no active chapter. No inference runtime, experiment results, or performance gains are claimed.

Planning outcome (2026-10-24 17:23 IST): the execution plan is complete and validated. It embeds all 201 chapter records and 535 direct prerequisite relationships, source paths, and target concepts, together with the no-code content contract, six dimensions, eight principles, Module 9 support, and per-chapter acceptance process. The strict documentation build succeeds without warnings, and the rendered plan and navigation have been inspected. Detailed chapter authorship remains at 0/201; no chapter is active. M1-C01 is next. A useful discovery was that the local preview retains the configured /InferX-docs/ URL prefix; the corrected exact preview address is recorded below.

At each phase completion, add a dated retrospective identifying the positions completed, the evidence reviewed, remaining gaps, changes to assumptions, and effects on later chapters. At final completion, reconcile all 201 ledger records with chapter statuses and the published-page preview; never replace this section with an unsupported claim of measured system performance.


## Context and Orientation


The repository is `/home/mbellary/work/projects/InferX-docs`. It is an educational documentation project, not an implemented engine. Markdown files under `docs/` become web pages through MkDocs, a documentation builder. `mkdocs.yml` controls navigation and enables the Material theme, tables, mathematics-independent text, and the existing Markdown extensions. Do not assume a math or diagram renderer exists just because a chapter contains notation: use readable notation and an actual image or a supported rendered diagram, and verify the built page.

The repository-root `PLANS.md` is the uploaded execution-plan guidance. This file, `docs/chapter-execution-plan.md`, is the living progress record. `docs/chapter-outline-inventory.md` contains the all-chapter scope inventory. `docs/chapter-authoring-order.md` contains the rationale and direct prerequisite relationships. A direct prerequisite is an earlier chapter whose concepts must already be explained; the earlier chapter may itself have prerequisites. The full per-chapter ledger above embeds those relationships, scope, and source locations so work can resume from this plan without conversation history.

`docs/learning-approach.md` defines the shared learning contract. `templates/chapter.md` is the authoring scaffold. `docs/module-1.md` through `docs/module-7.md`, plus `docs/module-9.md`, provide module reading orders. The 14 category directories organize subjects; their `index.md` pages list member chapters. A chapter ID such as M2-C04 identifies Module 2, Chapter 4; authoring position is separate and controls creation order. Do not create Module 8 or infer chapters for the empty Storage and persistence category.

The chapter files already exist and contain target-concept paragraphs. M1-C01–M1-C06 are Complete; the remaining 195 chapters retain Outline banners. Replace their placeholders in place while preserving the target scope, ID, category, and module navigation. Keep existing local modifications; do not reset the worktree or rebuild outlines from scratch. No particular CPU, GPU, network adapter, model, or benchmark results have been supplied. Hardware-dependent experiments must specify requirements and assumptions rather than claim a real machine was used.


## Plan of Work


### The single-chapter execution loop


At the start of an execution session, read this plan and the repository's applicable instructions. Reconcile the ledger summary against its records. Select the lowest incomplete authoring position, confirm all listed direct prerequisites are Complete, and inspect the chapter's existing source. If another chapter is Active, resume it. If a prerequisite is incomplete, finish the earliest unfinished prerequisite in schedule order; record any ordering correction in this plan and the authoring-order document before proceeding. Never have two Active chapters and never skip a blocked chapter without resolving or explicitly revising its dependency and schedule with a recorded reason.

Before writing content, mark only the selected chapter Active, set Updated to the actual local timestamp in IST, record its next action, and update the summary. Select relevant Module 9 guidance using the support policy below and record the IDs and application in that chapter's ledger. Read the actual available guidance; where it remains an outline or the advanced chapter occurs later, define the basic verification contract locally without claiming the future detailed chapter exists. Any source research at this stage concerns only the active chapter.

Develop Concepts first. Research relevant primary sources such as original research papers, official specifications, vendor documentation, or project-maintainer documentation; verify the actual source and date or version before relying on it. Define every unfamiliar term, symbol, axis, unit, and assumption. Progress from concrete examples through formal explanation to advanced tradeoffs. Include explained formulas with worked numerical examples and illustrative diagrams with captions and discussion. State reference behavior, meaning the expected result of an agreed baseline, and the boundaries within which it applies. Use Rust only as a language context when helpful; do not write Rust, Python, C++, pseudocode, kernel bodies, or any other implementation in chapters.

Develop Experiments second. Each named experiment must state its description, purpose/objective, target concepts, exit criteria, and a step-by-step procedure in prose. Also state its hypothesis and prediction, baseline, independent variable (the condition deliberately changed), controlled variables (conditions held constant), workload, reference, hardware and software requirements, and expected failure cases. Choose the number of experiments based on coverage of the actual target concepts; do not use a fixed count as a substitute for coverage. Connect the experiment explicitly to the learning module, systems engineering, and a specific HFT concern, and state the analogy's limit. Procedures teach what to investigate and observe; no code or runnable engine implementation is provided.

Develop Verification third, with a matching verification treatment for every experiment. Define correctness checks before speed claims. Specify measurement boundaries, clocks, units, populations, warmup, trials, sample-size reasoning, completion and drain conditions, outcome accounting, benchmark comparisons, profiling approach, and instrumentation overhead. Warmup means preparatory runs excluded from steady-state measurement; drain means allowing admitted work to finish before closing outcome accounting. A clock boundary must say exactly which start and end events are timed. For latency percentiles such as p99, which is a value at or below which approximately 99 percent of observations lie, state what is sampled and why the sample size supports the claim. Explain limitations rather than inventing a universal repetition count. Each experiment's exit criteria must resolve to observable checks; proposed speed thresholds require a justification and must not be reported as achieved.

Complete the chapter's six-dimension and eight-principle application, specifications and articles, hardware requirements, and takeaways. Review the active chapter against every acceptance condition below. Fix gaps in this same chapter. Change its source banner to `Status: Complete — detailed chapter authored and documentation validated; experimental procedures are proposed unless explicitly labelled observed` only after review and the strict build succeed. Update the matching ledger checkbox, all stage states, evidence, timestamp, summary totals, and next chapter in the same logical completion step. If interrupted before validation, leave the banner Draft and the ledger Active or Blocked, with the exact unfinished work recorded. Do not mark complete because the outline has headings or because the page builds.

### Required six-dimension application in every chapter


For Semantics and invariants, explain what the output means, what must remain true, and what evidence establishes correctness. An invariant is a condition that must stay true during permitted operations. Connect at least one experiment and its verification to these conditions.

For Workload and variability, explain how input and output lengths, arrivals, reuse, skew, and correlations change behavior. The user's general dimension also names modalities; this curriculum covers text generation, so explain that non-text modalities are out of scope rather than introducing a Module 8 dependency. An arrival is the time a request enters a defined boundary; skew means work or reuse is unevenly distributed.

For Resources and bottlenecks, account for compute, bytes moved, memory capacity, CPU time, and relevant transfer or storage resources. A bottleneck is the resource limiting progress at the stated operating point. Identify the boundary of any byte or operation count, including what is deliberately omitted.

For Time and distributions, identify the critical path, meaning the dependency chain that determines completion time, as well as queueing, synchronization, and slower outcomes. Explain the difference between an average and a distribution. A foundational paper experiment can use a worked timeline; hardware latency claims require actual hardware evidence.

For Ownership and coordination, identify who owns each piece of state, who can read or change it, and when it can be moved, shared, or reclaimed. Completion must be distinguished from submitting work. Explain how this affects the chapter's model or procedure rather than simply naming ownership.

For Failure and adaptation, address the relevant cancellation, stale information, overload, allocation failure, worker loss, or invalid-input case. When a failure class lies outside the chapter's runnable scope, explain the boundary conceptually and state what evidence a later experiment would require; do not omit the dimension.

### Required eight-principle application in every chapter


Principle 1: correctness defines the optimization boundary. State whether a change preserves mathematical behavior, introduces numerical approximation, or intentionally restricts output, and choose the matching reference and checks.

Principle 2: performance depends on workload and operating point. Specify where a proposed change may help and where it may hurt, including relevant shape, length, concurrency, or load changes. Do not extrapolate one example into a universal performance claim.

Principle 3: data movement is part of the algorithm. Explain reads, writes, layout changes, transfers, or copies alongside operation counts. Relate unnecessary movement to latency and resource pressure.

Principle 4: state has ownership, lifetime, and recovery cost. Identify state creation, sharing, reuse, release, and reconstruction, together with their correctness and performance consequences.

Principle 5: dependencies determine latency; bottlenecks determine capacity. Separate an individual request's critical path from the maximum sustainable rate of work. Asynchronous execution can hide work only when dependencies and available resources permit overlap.

Principle 6: variability and synchronization shape the tail. Examine burstiness, heterogeneous work, barriers, or contention, and explain why average efficiency cannot establish p99 behavior.

Principle 7: local improvements must be evaluated end to end. Define an individual operation's boundary and the complete request boundary. A faster operation, greater reuse, or better balance is useful only through its effect on correct useful service.

Principle 8: claims require reproducible evidence. State model and software identities, hardware assumptions, representative workloads, reference behavior, fault cases, measurements, and uncertainty. Reproduction means another reader can repeat the defined procedure under the recorded conditions; it does not mean the procedure has already been run.

These are practical engineering principles rather than mathematical axioms. Apply them to the chapter's explanations, experiments, and verification, not only to a generic closing list. State conceptual boundaries when a principle is not directly measurable at the current stage.

### Module 9 support policy


Module 1 uses the relevant parts of M9-C01–C05, M9-C07, M9-C17, and M9-C19 for reference behavior, numerical comparison, output contracts, and timing. Module 2 uses M9-C01, M9-C07, M9-C15, M9-C17, M9-C20, and M9-C22 for memory accounting and cache and allocator safety. Module 3 uses M9-C02, M9-C07, and M9-C12–C17 for hardware records, completion measurement, numerical validation, and profiles.

Module 4 uses M9-C07, M9-C11–C13, M9-C17–C18, M9-C22–C23, and M9-C27 for controlled comparisons, random-state contracts, kernel safety, graph replay, and regression gates. Random state means the per-request state controlling random draws; a graph is a captured dependency structure for repeated device submission. Module 5 uses M9-C02–C12, M9-C15, M9-C19, M9-C21–C23, and M9-C26–C28 for arrivals, load generation, service objectives, lifecycle behavior, overload, and capacity. A service-level objective is a declared acceptance target, such as a latency limit for an eligible request population; goodput counts useful work meeting that target.

Module 6 uses M9-C01, M9-C08, M9-C11, M9-C15, M9-C17–C20, M9-C24, and M9-C27–C28 for reuse identity, distributions, approximation, constrained decoding, memory, and benefit comparisons. Module 7 uses M9-C02, M9-C06–C07, M9-C11–C18, M9-C21–C23, and M9-C26–C28 for ranks, transfers, collective completion, distributed state, failures, scaling, and cost. A rank identifies a cooperating worker; a collective is an operation requiring specified workers to participate with compatible data and ordering. M9-C25 and M9-C29–C30 consolidate integrated text-generation validation and reporting across Modules 1–7.

These are candidates for chapter-specific application, not a requirement that every listed Module 9 chapter precede every supported chapter. The explicit direct prerequisites in the ledger govern order. Each active chapter records the relevant subset and explains its application. Module 9 chapters themselves explain their methodology from first principles and use worked applications from already introduced capabilities, while documenting advanced applications as later extensions.

### Milestone 1: Establish the execution record


Create this plan, preserve PLANS.md, expose the plan in Home navigation, and link it from the learning guidance, inventory, authoring order, and authoring template. Validate that the ledger contains each of the 201 inventory IDs exactly once in the same sequence as the authoring order, with the correct source path and target concepts. Confirm every direct prerequisite occurs earlier, all source files remain outlines, and all chapter stages start uncompleted. Run the strict build from the repository root. Acceptance is a user-visible plan page with a complete ledger and a build that reports success with no warnings. Record the observed evidence in this plan before closing this milestone.

### Milestone 2: Author model foundations and single-request generation, positions 1–28


Follow positions 1–16 through model and numerical foundations, then positions 17–28 through sampling, stopping, KV reuse, and generation timing. KV means the keys and values retained for attention so earlier token state can be reused. Each active chapter follows the full loop above. Include numerical examples and diagrams appropriate to token identities, tensor dimensions, model computation, generation steps, and timing events. Early Module 9 content establishes reference and measurement contracts before performance interpretation. After each chapter run the strict build and inspect its rendered page. Acceptance is 28 individually reviewed completed chapters, not a single batch completion claim, with ledger evidence for every experiment design and verification treatment. Record retrospectives at positions 16 and 28.

### Milestone 3: Author KV ownership, paging, and capacity, positions 29–50


Develop request state, memory budgets, ownership, paged allocation, sharing, failure handling, and accounting. Paging divides logical state into fixed-size blocks that can occupy separate physical locations; explain it without assuming operating-system expertise. Each experiment must show the accounting and references that prevent losing, duplicating, or prematurely freeing state, with hand-traceable boundary cases before proposed hardware studies. Benchmark designs compare full-request effects rather than allocator speed alone. Continue one chapter at a time, run the strict build after each, and inspect memory diagrams and formulas. Acceptance is 22 more completed chapter records and a consistent explanation of logical versus physical memory, with no claim that an allocator has been implemented.

### Milestone 4: Author GPU movement, execution, and profiling, positions 51–76


Introduce the graphics processing unit (GPU), its memory and execution organization, asynchronous submission, transfers, hardware records, and performance models before benchmark interpretation. Asynchronous means submission can return before work completes. Explain compute and bandwidth limits, what each profile measures, and how timing mistakes or instrumentation can alter results. Hardware requirements must distinguish a machine needed to run a procedure from an illustrative configuration used only in a worked calculation. Run the strict build and inspect each chapter's diagrams, notation, and source citations. Acceptance is 26 additional reviewed chapters whose procedures distinguish predicted traffic and bottlenecks from observed measurements.

### Milestone 5: Author kernels, graphs, and controlled optimization, positions 77–102


A kernel is a device operation submitted for execution; explain its contract and resource use before discussing fusion, which combines operations to avoid intermediate work. Cover numerical reductions, memory movement, graph lifetime, random-state behavior, correctness, and reproducible comparisons. Describe kernel design and experimental procedures without writing kernels or any implementation. Establish regression gates, meaning checks that prevent a change from worsening an agreed outcome, before tuning claims. After every chapter run the strict build and inspect formulas, diagrams, numerical examples, and experiment-to-verification mapping. Acceptance is 26 additional completed records with correctness-before-speed reasoning and no implementation snippets.

### Milestone 6: Author serving, queueing, and load methodology, positions 103–135


Explain processes, synchronization, queues, workload traces, service boundaries, valid load generation, batching, fairness, cancellation, streaming, and capacity. Synchronization coordinates access or ordering; batching groups requests into shared execution work. For each applicable experiment preserve intended and actual arrivals and count rejected, failed, cancelled, timed-out, completed, and unfinished work. Use HFT comparisons to explain bounded queues, stale events, critical paths, and slower outcomes while retaining the actual inference contract. Continue single-chapter review, strict builds, and rendered-page inspection. Acceptance is 33 additional completed records with explicit request identity, terminal-state rules, and defensible latency and capacity accounting.

### Milestone 7: Author cache reuse and advanced optimizations, positions 136–166


Explain prefix reuse, quantization, speculative decoding, constrained output, adapters, fallback behavior, and their interactions. Quantization represents values with fewer levels; speculative decoding proposes tokens then verifies them against a target model; an adapter changes selected computation for a request. Define all such terms before relying on them. Preserve the difference between equivalent computation, numerical quality loss, distributional behavior, and intentional output constraints. A distribution describes probabilities across possible outcomes rather than a single sampled token sequence. Continue the one-chapter loop with strict builds and visual review. Acceptance is 31 additional completed records whose experiment designs identify where each mechanism may help or hurt and how the corresponding correctness contract is checked.

### Milestone 8: Author distributed inference and economics, positions 167–198


Develop worker identities, communication semantics, completion, partitioning, routing, distributed state, failures, scaling, and useful-result cost. Partitioning divides work or state across workers; topology describes how their devices and links are connected. Treat single-device and multiple-device comparisons separately from increasing capacity by running independent replicas. Required hardware depends on each procedure; never label a simulation as a two-GPU measurement. Continue strict builds and visual inspection after each completed chapter, checking rank, shard, transfer, and time diagrams for consistent ownership and ordering. Acceptance is 32 additional completed records with compatible references and explicit memory, latency, quality, and cost boundaries.

### Milestone 9: Author integrated validation and final synthesis, positions 199–201


M9-C25 defines complete text-generation pipeline validation using Modules 1–7. M9-C29 consolidates nine planned integration milestones: single-request inference; KV and static batching; continuous batching with cancellation; paged allocation; prefix reuse and chunked prefill; kernel and graph optimization; quantization or speculation; multi-GPU execution; and integrated text-generation API load testing. An API is the defined interface through which clients submit requests and receive results. These are validation-design milestones, not assertions that an engine or experiments exist. M9-C30 defines a reproducible report including successful, failed, and inconclusive outcomes and the limits of each claim. Complete each chapter separately, run its strict build and rendered review, then reconcile all 201 source statuses and ledger entries. Acceptance is all 201 reviewed chapters, no Module 8 dependency, and an accurate retrospective distinguishing documentation completion from any independently observed experimental evidence.


## Concrete Steps


Work from `/home/mbellary/work/projects/InferX-docs`. To inspect the current change state, run the following operational command; it is not chapter implementation code:

    git status --short

Read this plan's summary and first incomplete ledger record. Open the linked source file and confirm the target concepts and prerequisites. Edit only the active chapter's detailed content, necessary supporting assets under its existing category or an explicitly referenced asset directory, and tracking/navigation files required by that chapter. Use the existing template's Concepts, Experiments, Verification, Engineering dimensions and principles, Specifications/articles/hardware, and Key takeaways structure; the plan's acceptance contract supplies the detailed requirements.

Use the existing Python environment to build the documentation:

    .venv/bin/python -m mkdocs build --strict

A successful run exits with status zero and includes a line of the form:

    INFO    -  Documentation built in <elapsed time> seconds

Any warning, missing page, missing anchor, or error must be fixed for the active chapter before completion. Build duration varies and is not an experiment result. Do not run inference-engine tests or claim test counts; this repository currently contains documentation rather than such an implementation.

To preview a completed or draft page, start the local documentation preview from the same directory:

    .venv/bin/python -m mkdocs serve --dev-addr 127.0.0.1:8000

Open `http://127.0.0.1:8000/InferX-docs/` and navigate to the active chapter. The configured site URL retains the `/InferX-docs/` prefix in local preview. For this plan, `http://127.0.0.1:8000/InferX-docs/chapter-execution-plan/` must show its ledger; the unprefixed address returns a 404 page. A foreground preview runs until stopped; stop it when finished. If port 8000 is occupied by another service, use an available local port and record the actual address. These commands validate and preview documentation, not an implementation of the proposed experiments.

If `.venv/bin/python` is unavailable, create a local Python 3.12-or-newer environment and install the pinned `requirements.txt` dependencies using the repository's documented setup and applicable environment permissions. Do not silently replace versions or install hardware runtimes. A preview/build environment issue blocks the documentation validation stage rather than justifying a false completion record.

At every stopping point, update this plan's timestamp, counts, active/next chapter, stage record, evidence, outstanding work, and any discoveries or decisions. When a chapter completes, also update its module and category status prose if necessary so those pages distinguish completed chapters from remaining outlines. Preserve chapter names, concept inventory, IDs, and navigation unless the active chapter reveals a justified scope correction; record and reconcile any such correction across the inventory and schedule before proceeding.


## Validation and Acceptance


The planning milestone is accepted only when there are exactly 201 unique chapter ledger records, positions 1–201, matching the inventory and authoring order, with no missing or extra ID. Every dependency must resolve to an earlier entry; this also rules out a dependency cycle, a chain that loops back to itself. Each ledger path must resolve and its recorded target concepts must match the source outline. Initially every source must remain an outline and every chapter stage must be unstarted. Navigation must expose this plan, and the strict build must succeed with zero warnings. Record exact observed evidence rather than marking this gate on intent alone.

A detailed chapter is accepted only when every target concept is explained with defined terms, assumptions, relevant formulas and a worked numerical example, illustrative diagrams, specifications, primary articles or documentation, benchmark design, validation approaches, and hardware specifications or requirements. A conceptual chapter must still contain meaningful quantitative examples and diagrams; if a resource or measurement is irrelevant, state a concrete boundary and reason instead of inserting invented specifications. Where a claim depends on a version, architecture, model, or precision, identify it. Check the source directly; do not use an unverified search snippet as evidence.

Every experiment must have a name, description, purpose/objective, target concepts, exit criteria, controlled procedure, workload, baseline, prediction, and hardware/software assumptions. Every experiment must have a corresponding verification treatment containing correctness checks, appropriate reference or tolerance, measurement and timing boundaries, benchmarks, profiling or a reasoned profiling limit, outcome accounting, uncertainty, and reproducibility details. For every target concept, identify where it is taught and exercised or checked; avoid experiments that merely repeat the explanation without testing a falsifiable proposition. Numerical tolerances must be justified in context. Invalid inputs and relevant failure cases must have expected handling.

Every chapter must explicitly connect its experiments and verification to the target module, systems engineering, and HFT, with the analogy's limits stated. All six dimensions and eight principles must have chapter-specific treatment spanning concepts, experiments, and verification. Appropriate Module 9 guidance must be linked and its application recorded in the ledger. No chapter may contain an implementation, pseudocode standing in for one, or claims that proposed experiments were run. Formulas, diagrams, worked calculations, and prose procedures are allowed and required.

Perform a content review followed by the strict documentation build and a rendered-page review. Inspect heading hierarchy, tables, links, mathematical notation, diagram labels, units, and captions on the actual page or a browser-rendered preview. A build alone does not establish that a diagram renders or that the explanation is readable. Record which page or artifact was inspected and the result. If visual inspection is unavailable, keep the review stage incomplete and state the limitation. The plan page itself can be accepted after its rendered structure is verified; it does not require implementing any experiment.

In each completed chapter record, replace Evidence: None with a concise real record: review date, source/reference checks, experiment coverage, six-dimension and eight-principle coverage, Module 9 application, build outcome, visual-review outcome, and any remaining explicitly bounded limitation. Keep measured experimental results separate from documentation-validation evidence. Mark a chapter complete only when all required content and documentation gates pass.


## Idempotence and Recovery


Resume from the first incomplete record and its stage notes; do not recreate the plan, reset all statuses, or overwrite completed chapters with outlines. Re-running the documentation build regenerates the ignored `site/` output, not the Markdown source. Preserve the active chapter's draft if interrupted; its source banner must remain Draft and its ledger must identify exactly what is unfinished. If a build fails, fix the active chapter or its introduced references, rebuild, and record the actual successful result before completing it.

If a prerequisite or source contradicts the current plan, record the discovery, inspect the smallest affected scope, and revise the dependency order and ledger together with a dated reason. Maintain complete ID coverage and earlier-prerequisite ordering. Do not silently omit a target concept, fabricate a source, or skip a required review to keep progress moving. If a problem requires user information, record Blocked and the exact missing information; do not begin a different detailed chapter merely to keep one active. Resolve routine editorial and source choices within the agreed scope.

The working tree already contains curriculum and inventory changes from prior requests. Preserve them and report only changes actually made. Do not delete assets shared by completed chapters. Commits and publication are separate actions; this plan does not require or authorize deployment, repository-wide cleanup, or automatic history changes.


## Artifacts and Notes

Observed M1-C06 evidence (2026-10-24 21:35 IST): docs/numerics-and-correctness/m1-c06-reductions-probabilities-and-stable-softmax.md replaces its outline. Assets under docs/assets/diagrams/ are m1-c06-reduction-axes.svg and m1-c06-shifted-softmax.svg. Independent checks validated required fields, local links, SVG structure, reduction/shape references, shift and reversal cases, tiny-tail magnitude, every E4 coordinate/reference, exact fixture input representation, and byte/time arithmetic. Browser screenshots verified formulas, tables and both full diagrams. Calculator/reference checks are documentation evidence, not measured runtime performance.

Observed M1-C05 evidence (2026-10-24 21:21 IST): source docs/state-memory-and-caching/m1-c05-how-tensors-occupy-memory.md and assets m1-c05-layout-and-strides.svg, m1-c05-view-and-copy.svg, m1-c05-broadcast-storage.svg under docs/assets/diagrams/. Independent documentation checks covered all experiment fields/local links, every E4 coordinate/output and the worked arithmetic. Browser screenshots confirmed physical sequences, sharing/copy labels, zero-stride broadcast storage, formulas and matched verification. Local preview required restart after interruption. No runtime measurements, model results or CI rerun are asserted.


Observed chapter evidence (2026-10-24 18:36 IST): M1-C03 replaces its outline; its assets are docs/assets/diagrams/m1-c03-rank-and-shape.svg and docs/assets/diagrams/m1-c03-coordinate-contract.svg. Required experiment fields, local links, exact shape/count/index/padding calculations and large-fixture labels passed independent checks. The strict build succeeded without warnings (3.98 seconds). Browser screenshots inspected chapter notation, scalar/empty cases, Rust representation and verification tables; full SVG browser views confirmed all diagram cells, labels and the equal-axis negative control. One trailing whitespace issue found during review was removed before final checks. No engine, tensor benchmark, GPU or market experiment is claimed. Existing unrelated working-tree changes remain preserved.

Observed chapter evidence (2026-10-24 18:16 IST): M1-C02 now replaces its outline. Its assets are docs/assets/diagrams/m1-c02-text-to-token-contract.svg and docs/assets/diagrams/m1-c02-identity-and-display.svg. The strict build passed with zero warnings (4.05 seconds); required experiment fields, local links, byte/count examples and git diff --check passed. Browser screenshots confirmed the full preparation path, both identity/display examples, readable notation, context-budget/storage arithmetic and the experiment-verification table. This is documentation-validation evidence, not runtime tokenizer or hardware evidence. Existing unrelated user changes remain preserved.

Observed chapter evidence (2026-10-24 17:39 IST): M1-C01 and two assets, docs/assets/diagrams/m1-c01-request-lifecycle.svg and docs/assets/diagrams/m1-c01-request-timeline.svg, replace the starting outline with detailed educational content. Required experiment fields and local links were checked, git diff --check passed, and the strict MkDocs build succeeded without warnings. Browser screenshots reviewed the chain-rule notation and worked-example table, the request timeline with units, the experiment-verification table, and the final lifecycle branch including output finalization. A content review checked all six target concepts, dimensions, principles, and no-code/no-invented-measurement boundaries. Existing working-tree edits outside this chapter remain preserved.

The durable artifacts are repository-root `PLANS.md`, this execution plan, the ordered 201 chapter source files named in the ledger, and any chapter-specific diagrams or cited source notes required during authorship. Generated web pages live under `site/` and are not the progress source of truth. Do not add temporary authoring programs or an inference implementation to the deliverables.

Observed planning evidence (2026-10-24 17:23 IST): 201 unique ledger records appear in positions 1–201 and match the inventory and schedule. All 535 direct prerequisite relationships match the authoring order and point earlier, so there are no cycles. All 201 source paths and target-concept lists match the outlines; every chapter remains unstarted. The strict documentation build exited with status zero and no warnings. The in-app browser showed the plan at http://127.0.0.1:8000/InferX-docs/chapter-execution-plan/ with working Home navigation, a readable table of contents, the progress summary, and the chapter ledger; a screenshot was inspected for readability. Markdown task markers appear as readable [x] and [ ] text with the current extensions; editing the Markdown plan is the tracking action, not clicking a website checkbox. The local preview initially required permission because the sandbox prevents opening a local socket. No experimental performance evidence is claimed.


## Interfaces and Dependencies


The document interface is stable: every existing chapter retains its ID, source location, category, target concepts, and module previous/next navigation unless a recorded editorial decision updates all references. Status banners distinguish Outline, Draft, and Complete. This plan's ledger and summary must agree with the chapter banners at each completion boundary. The inventory defines scope, the authoring order explains dependencies, and this plan owns execution state.

The documentation tool dependencies are the pinned `mkdocs==1.6.1` and `mkdocs-material==9.6.23` in `requirements.txt`, with the existing `mkdocs.yml` extensions. Keep the 14 categories and add this plan under Home navigation. Diagram assets must be referenced with valid local paths; ensure the actual renderer can display them before marking review complete. No runtime functions, library interfaces, kernels, model executor, trading system, or inference-serving implementation is required by this documentation plan.

Primary-source research is required when writing each chapter, not as a claim that every source for all 201 chapters has already been selected. Hardware availability is not assumed; unsupported or unobserved configurations remain explicitly labelled requirements, examples, or proposed experiments.


## Revision Notes


2026-10-24 17:21 IST: Created this execution plan from the uploaded PLANS.md and the existing 201-chapter inventory and dependency schedule. Embedded the complete scope, creation order, stage tracking, learning contract, one-active-chapter rule, Module 9 support, no-code constraint, validation procedure, and recovery rules so future work can resume without conversation history. Planning verification remains to be recorded; no detailed chapter has been started.


2026-10-24 17:23 IST: Completed planning validation, reconciled 201 chapter records and 535 earlier prerequisites, recorded the successful strict build and rendered-page review, and corrected the local preview URL after observing the configured path prefix. Planning setup is complete; all detailed chapter work remains not started, with M1-C01 next.


2026-10-24 17:28 IST: Began authorized execution with M1-C01 as the sole active chapter. Selected introductory Module 9 support and preserved pre-existing working-tree changes in README.md, mkdocs.yml, templates/chapter.md, and PLANS.md.


2026-10-24 17:39 IST: Completed M1-C01 after content, strict-build and rendered-page review; reconciled chapter banner, ledger stages, curriculum summaries, current totals and next chapter. Recorded reference-policy discovery and timing-boundary decisions. All remaining 200 chapters remain unstarted.


2026-10-24 17:43 IST: Began M1-C02 as the only active chapter after confirming M1-C01 is Complete. Preserved the existing README.md, mkdocs.yml, templates/chapter.md and PLANS.md working-tree changes.


2026-10-24 18:16 IST: Completed M1-C02 after checking primary sources, all seven target concepts, four experiment/verification designs, diagrams, no-code scope, strict build and rendered-page presentation. Updated chapter/category/module status, inventory, summaries and the ledger to 2 complete and 199 unstarted, with M1-C03 next.


2026-10-24 18:20 IST: Began M1-C03 as the only active chapter, preserving the completed chapters and existing README.md, mkdocs.yml, templates/chapter.md and PLANS.md working-tree changes.


2026-10-24 18:36 IST: Completed M1-C03 after primary-source, content, numerical, strict-build and rendered-page/diagram review. Reconciled chapter/banner/ledger/module/category/inventory summaries to 3 complete, 198 unstarted and M1-C04 next. Recorded the larger-fixture label validation and separation of logical indexing from later physical-layout treatment.


2026-10-24 18:41 IST: Recorded the GitHub/local navigation mismatch, exact failure reproduction and successful working-tree build. Added an explicit handoff check for uncommitted configuration dependencies; chapter progress and scope are unchanged.


2026-10-24 18:48 IST: Began M1-C04 as the only active chapter after confirming M1-C03 completion. Verified the navigation fix in commit 3beea89; no configuration fix remains pending locally. Preserved existing README.md, templates/chapter.md and PLANS.md changes.


2026-10-24 19:04 IST: Completed M1-C04 after source, content, arithmetic, strict-build and browser review. Reconciled chapter, ledger, module, category, inventory and landing-page summaries to 4 complete and 197 unstarted. No later chapter started.


2026-10-24 19:12 IST: Began M1-C05 as the only active chapter after confirming M1-C03 prerequisite completion. Preserved existing README.md, templates/chapter.md and PLANS.md changes. No later chapter started.


2026-10-24 21:21 IST: Completed M1-C05 after content/source, numerical and browser review; reconciled chapter banner, ledger and curriculum summaries to 5 complete and 196 unstarted, with M1-C06 next. Clarified product notation and removed arrow/label overlap after rendered inspection. Preserved existing unrelated changes.


2026-10-24 21:26 IST: Began M1-C06 as the sole active chapter after confirming M1-C03 prerequisite completion. Preserved existing README.md, templates/chapter.md and PLANS.md changes.


2026-10-24 21:35 IST: Completed M1-C06 after primary-source, content, high-precision arithmetic and browser review. Reconciled chapter banner, ledger, module/category/inventory and landing-page summaries to 6 complete and 195 unstarted, with M1-C07 next. Preserved existing unrelated worktree changes and did not start a later chapter.
