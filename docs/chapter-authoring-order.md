# Detailed chapter authoring order

Prepared 24 October 2026 from the [chapter outline inventory](chapter-outline-inventory.md), the module prerequisite sections, and the [learning approach](learning-approach.md).

Execute this sequence using the [chapter execution plan and progress ledger](chapter-execution-plan.md). That plan records each chapter's active stage, review evidence, and completion state; this document records the dependency order.

## Recommendation

Use **Modules 1 → 2 → 3 → 4 → 5 → 6 → 7 as the backbone, with relevant Module 9 chapters inserted when their foundations become available**. A separate dependency order is useful because measurement and correctness are required throughout the detailed chapters. Writing every Module 9 chapter last would leave earlier experiments relying on foundations that have not yet been authored. The [Module 9 scope](module-9.md) explicitly calls for using its relevant chapters alongside the earliest builds.

There is no single uniquely necessary order. The sequence below is the recommended working schedule: complete chapters in ascending authoring position. The prerequisite column records the content relationships that justify the schedule. Chapters without a dependency on one another could be exchanged, but use this one sequence for the requested one-chapter-at-a-time workflow.

This plan includes **all 201 existing outlines exactly once**, and the full sequence is within scope. **Module 8 is excluded. Module 9 must support Modules 1–7 throughout**, through the interleaved foundations and validation chapters below. Positions **199–201** complete integrated text-generation serving validation, the nine milestones, and reporting; they have no external module dependency.

## How to interpret dependencies

- **Authoring position** is the recommended creation order, independent of chapter numbering. Preserve existing IDs, category assignments, and module reading-order links.
- **Direct prerequisites** are proposed editorial requirements inferred from target concepts, rather than prerequisite metadata already present in every outline. An earlier chapter should be detailed and reviewed before a dependent chapter is completed. Follow their prerequisites transitively; the table does not repeat every foundational chapter in every row. Some module-entry dependencies deliberately retain the broad prerequisites stated in the module overview rather than claiming a minimal mathematical dependency graph.
- A **chapter dependency** concerns concepts, experiment design, and verification procedures. It does not require running the proposed experiments or having hardware measurements: chapters contain no implementation code, and proposed results must remain labelled as proposed.
- Cross-cutting chapters should define terminology for later capabilities at a conceptual level and use worked examples from the capabilities already introduced. For example, early memory accounting can identify communication buffers without teaching collectives; later distributed chapters supply that application. All applications remain within the text-generation capabilities of Modules 1–7.
- Each chapter still needs its own correctness checks and experimental controls. Earlier benchmarking chapters introduce the basic warmup, workload, repetition, and comparison controls they need; M9-C11 later develops the complete treatment including compilation and graph setup. An advanced validation chapter consolidates checks; it does not postpone validation of earlier chapters.

## Deliberate changes to module order

| Change | Reason |
| --- | --- |
| Insert M9-C01 and M9-C17 after M1-C14 | The model now produces logits, so reference behavior and justified numerical comparisons have a concrete basis before generation and cache comparisons. |
| Insert M9-C07, M9-C19, and M9-C02–C05 during Module 1 | Explain uncertainty, final-output contracts, clocks, TTFT, streamed token gaps, and end-to-end timing before the generation-latency chapter. |
| Move M3-C05 and M3-C06 ahead of M3-C04 | Explain the memory hierarchy, registers, shared memory, and resource limits before deriving occupancy limits. |
| Insert memory, hardware, and profiling chapters from Module 9 around Modules 2 and 3 | Establish accounting, measurement conditions, timelines, and hardware interpretation before the associated comparisons. |
| Move M4-C19 before M4-C18 | Establish random-state ownership and sampling equivalence before designing a fused sampling operation. |
| Insert M9-C11 after graph lifetimes and M9-C27 after kernel validation | Cover graph-aware controlled comparisons and regression gates before tuning and integration conclusions. |
| Move M5-C05 before M5-C03 and M5-C04 | Establish synchronization and ownership before explaining shared-memory IPC and blocking/nonblocking queues. |
| Insert load, SLO, lifecycle, and invariance chapters during Module 5 | Establish load-generation validity, outcome accounting, and safety contracts before policy and sustainable-capacity comparisons. |
| Insert M9-C20 after prefix integration; M9-C18 after speculative state; M9-C24 after optimization failure handling | The advanced validation treatments now have the mechanisms they validate. Basic sampling correctness remains part of M1-C15 and M4-C19. |
| Insert M9-C14 after M7-C09 | Explain ranks, collective operations, communication cost, and overlap before measuring collective completion and applying the results to partitioning. |
| Finish with M9-C25, M9-C29, and M9-C30 | Validate integrated text-generation serving across Modules 1–7, consolidate all nine milestones, and establish reproducible reporting. These chapters require only earlier chapters in this schedule. |

## Phase summary

| Phase | Authoring positions | Existing outlines | Purpose |
| --- | --- | --- | --- |
| 1. Model and numerical foundations | 1–16 | 16 | Establish model computation, reference behavior, and numerical comparisons before generation experiments. |
| 2. Single-request generation and timing | 17–28 | 12 | Establish stopping, cache equivalence, timing boundaries, and uncertainty before interpreting generation latency. |
| 3. KV ownership, paging, and capacity | 29–50 | 22 | Complete allocator and cache safety, then memory accounting and end-to-end KV comparisons. |
| 4. GPU execution, movement, and profiling | 51–76 | 26 | Explain memory resources before occupancy; establish hardware records, validation, and profiling before GPU benchmark interpretation. |
| 5. Kernels, graph execution, and controlled optimization | 77–102 | 26 | Explain RNG contracts before fused sampling; establish reproducible graph comparisons and regression gates before tuning. |
| 6. Serving, queueing, and load methodology | 103–135 | 33 | Explain synchronization before IPC and queues; establish workload, load-generator, SLO, lifecycle, and invariance checks before policy and capacity comparisons. |
| 7. Cache reuse and advanced optimizations | 136–166 | 31 | Validate prefix identity, speculative distributions, approximate paths, and fallbacks before integrated optimization conclusions. |
| 8. Distributed inference and economics | 167–198 | 32 | Establish collective semantics and completion measurement before partitioning, distributed validation, scaling, and cost analysis. |
| 9. Integrated serving validation and final synthesis | 199–201 | 3 | Validate the integrated text-generation pipeline from Modules 1–7, consolidate all nine milestones, and establish the complete report methodology. |

## Complete authoring sequence

Direct prerequisite IDs link to their entries in this schedule. Chapter names link to their outlines. Every prerequisite belongs to the current Modules 1–7 and 9 curriculum.

### 1. Model and numerical foundations

Establish model computation, reference behavior, and numerical comparisons before generation experiments.

| Authoring position | Chapter ID | Category | Chapter name | Direct prerequisites |
| --- | --- | --- | --- | --- |
| 1 | <span id="m1-c01">M1-C01</span> | Model computation and semantics | [From a prompt to the next token](model-computation-and-semantics/m1-c01-from-a-prompt-to-the-next-token.md) | None; start here |
| 2 | <span id="m1-c02">M1-C02</span> | Interfaces, protocols, and streaming | [Representing text as tokens](interfaces-protocols-and-streaming/m1-c02-representing-text-as-tokens.md) | [M1-C01](#m1-c01) |
| 3 | <span id="m1-c03">M1-C03</span> | Model computation and semantics | [Numbers, vectors, matrices, and tensors](model-computation-and-semantics/m1-c03-numbers-vectors-matrices-and-tensors.md) | [M1-C01](#m1-c01) |
| 4 | <span id="m1-c04">M1-C04</span> | Model computation and semantics | [Dot products and matrix multiplication](model-computation-and-semantics/m1-c04-dot-products-and-matrix-multiplication.md) | [M1-C03](#m1-c03) |
| 5 | <span id="m1-c05">M1-C05</span> | State, memory, and caching | [How tensors occupy memory](state-memory-and-caching/m1-c05-how-tensors-occupy-memory.md) | [M1-C03](#m1-c03) |
| 6 | <span id="m1-c06">M1-C06</span> | Numerics and correctness | [Reductions, probabilities, and stable softmax](numerics-and-correctness/m1-c06-reductions-probabilities-and-stable-softmax.md) | [M1-C03](#m1-c03) |
| 7 | <span id="m1-c07">M1-C07</span> | Numerics and correctness | [Floating-point arithmetic and numerical correctness](numerics-and-correctness/m1-c07-floating-point-arithmetic-and-numerical-correctness.md) | [M1-C06](#m1-c06) |
| 8 | <span id="m1-c08">M1-C08</span> | Measurement, experimentation, and economics | [Operation counts and actual execution cost](measurement-experimentation-and-economics/m1-c08-operation-counts-and-actual-execution-cost.md) | [M1-C04](#m1-c04), [M1-C05](#m1-c05), [M1-C07](#m1-c07) |
| 9 | <span id="m1-c09">M1-C09</span> | Model computation and semantics | [Token embeddings and learned projections](model-computation-and-semantics/m1-c09-token-embeddings-and-learned-projections.md) | [M1-C02](#m1-c02), [M1-C04](#m1-c04), [M1-C05](#m1-c05) |
| 10 | <span id="m1-c10">M1-C10</span> | Model computation and semantics | [Attention, one dimension at a time](model-computation-and-semantics/m1-c10-attention-one-dimension-at-a-time.md) | [M1-C09](#m1-c09), [M1-C06](#m1-c06) |
| 11 | <span id="m1-c11">M1-C11</span> | Model computation and semantics | [Causal masking and positional information](model-computation-and-semantics/m1-c11-causal-masking-and-positional-information.md) | [M1-C10](#m1-c10) |
| 12 | <span id="m1-c12">M1-C12</span> | Model computation and semantics | [Multi-head attention and its variants](model-computation-and-semantics/m1-c12-multi-head-attention-and-its-variants.md) | [M1-C11](#m1-c11) |
| 13 | <span id="m1-c13">M1-C13</span> | Model computation and semantics | [Building a complete Transformer block](model-computation-and-semantics/m1-c13-building-a-complete-transformer-block.md) | [M1-C12](#m1-c12), [M1-C07](#m1-c07) |
| 14 | <span id="m1-c14">M1-C14</span> | Model computation and semantics | [Assembling a small decoder-only Transformer](model-computation-and-semantics/m1-c14-assembling-a-small-decoder-only-transformer.md) | [M1-C13](#m1-c13) |
| 15 | <span id="m9-c01">M9-C01</span> | Numerics and correctness | [Defining reference behavior and evidence before optimizing](numerics-and-correctness/m9-c01-defining-reference-behavior-and-evidence-before-optimizing.md) | [M1-C14](#m1-c14), [M1-C07](#m1-c07) |
| 16 | <span id="m9-c17">M9-C17</span> | Numerics and correctness | [Comparing logits with justified numerical tolerances](numerics-and-correctness/m9-c17-comparing-logits-with-justified-numerical-tolerances.md) | [M9-C01](#m9-c01), [M1-C14](#m1-c14) |

### 2. Single-request generation and timing

Establish stopping, cache equivalence, timing boundaries, and uncertainty before interpreting generation latency.

| Authoring position | Chapter ID | Category | Chapter name | Direct prerequisites |
| --- | --- | --- | --- | --- |
| 17 | <span id="m1-c15">M1-C15</span> | Model computation and semantics | [Turning logits into the next token](model-computation-and-semantics/m1-c15-turning-logits-into-the-next-token.md) | [M1-C14](#m1-c14), [M9-C01](#m9-c01), [M9-C17](#m9-c17) |
| 18 | <span id="m9-c07">M9-C07</span> | Measurement, experimentation, and economics | [Latency distributions and statistical uncertainty](measurement-experimentation-and-economics/m9-c07-latency-distributions-and-statistical-uncertainty.md) | [M1-C06](#m1-c06) |
| 19 | <span id="m1-c16">M1-C16</span> | Interfaces, protocols, and streaming | [Building the single-request generation loop](interfaces-protocols-and-streaming/m1-c16-building-the-single-request-generation-loop.md) | [M1-C15](#m1-c15), [M1-C02](#m1-c02) |
| 20 | <span id="m9-c19">M9-C19</span> | Interfaces, protocols, and streaming | [Validating tokenization, stopping, and final output](interfaces-protocols-and-streaming/m9-c19-validating-tokenization-stopping-and-final-output.md) | [M1-C16](#m1-c16), [M9-C01](#m9-c01) |
| 21 | <span id="m1-c17">M1-C17</span> | State, memory, and caching | [Reusing attention state with a KV cache](state-memory-and-caching/m1-c17-reusing-attention-state-with-a-kv-cache.md) | [M1-C16](#m1-c16), [M1-C12](#m1-c12), [M1-C05](#m1-c05) |
| 22 | <span id="m1-c18">M1-C18</span> | Runtime and concurrency | [Understanding prefill and decode](runtime-and-concurrency/m1-c18-understanding-prefill-and-decode.md) | [M1-C17](#m1-c17) |
| 23 | <span id="m1-c19">M1-C19</span> | Numerics and correctness | [Validating cached and uncached generation](numerics-and-correctness/m1-c19-validating-cached-and-uncached-generation.md) | [M1-C18](#m1-c18), [M9-C17](#m9-c17), [M9-C19](#m9-c19) |
| 24 | <span id="m9-c02">M9-C02</span> | Measurement, experimentation, and economics | [Request events, clocks, and measurement boundaries](measurement-experimentation-and-economics/m9-c02-request-events-clocks-and-measurement-boundaries.md) | [M1-C18](#m1-c18), [M9-C19](#m9-c19) |
| 25 | <span id="m9-c03">M9-C03</span> | Measurement, experimentation, and economics | [Measuring time to first token including queueing](measurement-experimentation-and-economics/m9-c03-measuring-time-to-first-token-including-queueing.md) | [M9-C02](#m9-c02) |
| 26 | <span id="m9-c04">M9-C04</span> | Interfaces, protocols, and streaming | [Measuring inter-token latency in a streamed protocol](interfaces-protocols-and-streaming/m9-c04-measuring-inter-token-latency-in-a-streamed-protocol.md) | [M9-C03](#m9-c03), [M1-C16](#m1-c16) |
| 27 | <span id="m9-c05">M9-C05</span> | Measurement, experimentation, and economics | [Measuring end-to-end latency and throughput](measurement-experimentation-and-economics/m9-c05-measuring-end-to-end-latency-and-throughput.md) | [M9-C04](#m9-c04) |
| 28 | <span id="m1-c20">M1-C20</span> | Measurement, experimentation, and economics | [Measuring and explaining generation latency](measurement-experimentation-and-economics/m1-c20-measuring-and-explaining-generation-latency.md) | [M1-C19](#m1-c19), [M1-C08](#m1-c08), [M9-C03](#m9-c03), [M9-C04](#m9-c04), [M9-C05](#m9-c05), [M9-C07](#m9-c07) |

### 3. KV ownership, paging, and capacity

Complete allocator and cache safety, then memory accounting and end-to-end KV comparisons.

| Authoring position | Chapter ID | Category | Chapter name | Direct prerequisites |
| --- | --- | --- | --- | --- |
| 29 | <span id="m2-c01">M2-C01</span> | State, memory, and caching | [What the KV cache retains and why](state-memory-and-caching/m2-c01-what-the-kv-cache-retains-and-why.md) | [M1-C19](#m1-c19) |
| 30 | <span id="m2-c02">M2-C02</span> | Model computation and semantics | [Attention head sharing: MHA, GQA, and MQA](model-computation-and-semantics/m2-c02-attention-head-sharing-mha-gqa-and-mqa.md) | [M2-C01](#m2-c01), [M1-C12](#m1-c12) |
| 31 | <span id="m2-c03">M2-C03</span> | State, memory, and caching | [Calculating KV memory and request capacity](state-memory-and-caching/m2-c03-calculating-kv-memory-and-request-capacity.md) | [M2-C02](#m2-c02), [M1-C05](#m1-c05), [M1-C07](#m1-c07) |
| 32 | <span id="m2-c04">M2-C04</span> | State, memory, and caching | [Memory ownership, handles, and lifetimes from first principles](state-memory-and-caching/m2-c04-memory-ownership-handles-and-lifetimes-from-first-principles.md) | [M2-C01](#m2-c01), [M1-C05](#m1-c05) |
| 33 | <span id="m2-c05">M2-C05</span> | State, memory, and caching | [Contiguous KV storage and its limits](state-memory-and-caching/m2-c05-contiguous-kv-storage-and-its-limits.md) | [M2-C03](#m2-c03), [M2-C04](#m2-c04) |
| 34 | <span id="m2-c06">M2-C06</span> | State, memory, and caching | [Paged KV storage and logical-to-physical mapping](state-memory-and-caching/m2-c06-paged-kv-storage-and-logical-to-physical-mapping.md) | [M2-C05](#m2-c05) |
| 35 | <span id="m2-c07">M2-C07</span> | Kernels, compilers, and execution | [How attention reads a paged KV layout](kernels-compilers-and-execution/m2-c07-how-attention-reads-a-paged-kv-layout.md) | [M2-C06](#m2-c06), [M1-C10](#m1-c10) |
| 36 | <span id="m2-c08">M2-C08</span> | State, memory, and caching | [Designing a fixed-size KV block allocator](state-memory-and-caching/m2-c08-designing-a-fixed-size-kv-block-allocator.md) | [M2-C06](#m2-c06), [M2-C04](#m2-c04) |
| 37 | <span id="m2-c09">M2-C09</span> | State, memory, and caching | [Choosing block size and measuring fragmentation](state-memory-and-caching/m2-c09-choosing-block-size-and-measuring-fragmentation.md) | [M2-C08](#m2-c08), [M2-C03](#m2-c03) |
| 38 | <span id="m2-c10">M2-C10</span> | Runtime and concurrency | [Request state transitions and safe block reuse](runtime-and-concurrency/m2-c10-request-state-transitions-and-safe-block-reuse.md) | [M2-C08](#m2-c08), [M2-C04](#m2-c04) |
| 39 | <span id="m2-c11">M2-C11</span> | State, memory, and caching | [Reference counting and shared block ownership](state-memory-and-caching/m2-c11-reference-counting-and-shared-block-ownership.md) | [M2-C10](#m2-c10) |
| 40 | <span id="m2-c12">M2-C12</span> | State, memory, and caching | [Copy-on-write for branching requests](state-memory-and-caching/m2-c12-copy-on-write-for-branching-requests.md) | [M2-C11](#m2-c11), [M2-C07](#m2-c07) |
| 41 | <span id="m2-c13">M2-C13</span> | State, memory, and caching | [Prefix reuse and cache identity](state-memory-and-caching/m2-c13-prefix-reuse-and-cache-identity.md) | [M2-C12](#m2-c12), [M1-C02](#m1-c02), [M1-C11](#m1-c11) |
| 42 | <span id="m2-c14">M2-C14</span> | State, memory, and caching | [Eviction, retention, and reconstruction](state-memory-and-caching/m2-c14-eviction-retention-and-reconstruction.md) | [M2-C13](#m2-c13), [M2-C11](#m2-c11) |
| 43 | <span id="m2-c15">M2-C15</span> | Scheduling and queueing | [Admission and growth under a finite KV budget](scheduling-and-queueing/m2-c15-admission-and-growth-under-a-finite-kv-budget.md) | [M2-C14](#m2-c14), [M2-C09](#m2-c09) |
| 44 | <span id="m2-c16">M2-C16</span> | Reliability and capacity control | [Completion, cancellation, and allocation failure](reliability-and-capacity-control/m2-c16-completion-cancellation-and-allocation-failure.md) | [M2-C15](#m2-c15), [M2-C10](#m2-c10) |
| 45 | <span id="m2-c17">M2-C17</span> | Model computation and semantics | [Sliding-window attention and bounded cache state](model-computation-and-semantics/m2-c17-sliding-window-attention-and-bounded-cache-state.md) | [M2-C07](#m2-c07), [M1-C11](#m1-c11) |
| 46 | <span id="m2-c18">M2-C18</span> | Model computation and semantics | [Architecture-specific state: Multi-head Latent Attention](model-computation-and-semantics/m2-c18-architecture-specific-state-multi-head-latent-attention.md) | [M2-C02](#m2-c02), [M1-C04](#m1-c04), [M1-C11](#m1-c11) |
| 47 | <span id="m2-c19">M2-C19</span> | Runtime and concurrency | [Connecting block allocation to the request generator](runtime-and-concurrency/m2-c19-connecting-block-allocation-to-the-request-generator.md) | [M2-C16](#m2-c16), [M2-C17](#m2-c17), [M2-C18](#m2-c18), [M1-C16](#m1-c16) |
| 48 | <span id="m2-c20">M2-C20</span> | Numerics and correctness | [Validating allocator and cache safety](numerics-and-correctness/m2-c20-validating-allocator-and-cache-safety.md) | [M2-C19](#m2-c19), [M1-C19](#m1-c19), [M9-C01](#m9-c01) |
| 49 | <span id="m9-c15">M9-C15</span> | State, memory, and caching | [Accounting for weights, KV state, workspace, and fragmentation](state-memory-and-caching/m9-c15-accounting-for-weights-kv-state-workspace-and-fragmentation.md) | [M2-C20](#m2-c20), [M1-C14](#m1-c14) |
| 50 | <span id="m2-c21">M2-C21</span> | Measurement, experimentation, and economics | [Benchmarking KV management end to end](measurement-experimentation-and-economics/m2-c21-benchmarking-kv-management-end-to-end.md) | [M2-C20](#m2-c20), [M9-C15](#m9-c15), [M1-C20](#m1-c20), [M9-C07](#m9-c07) |

### 4. GPU execution, movement, and profiling

Explain memory resources before occupancy; establish hardware records, validation, and profiling before GPU benchmark interpretation.

| Authoring position | Chapter ID | Category | Chapter name | Direct prerequisites |
| --- | --- | --- | --- | --- |
| 51 | <span id="m3-c01">M3-C01</span> | Hardware architecture and topology | [Following a tensor from CPU to GPU](hardware-architecture-and-topology/m3-c01-following-a-tensor-from-cpu-to-gpu.md) | [M1-C14](#m1-c14), [M1-C18](#m1-c18), [M2-C04](#m2-c04) |
| 52 | <span id="m3-c02">M3-C02</span> | Hardware architecture and topology | [Reading GPU specifications and capability limits](hardware-architecture-and-topology/m3-c02-reading-gpu-specifications-and-capability-limits.md) | [M3-C01](#m3-c01), [M1-C07](#m1-c07), [M1-C08](#m1-c08) |
| 53 | <span id="m3-c03">M3-C03</span> | Hardware architecture and topology | [Threads, warps, blocks, grids, and streaming multiprocessors](hardware-architecture-and-topology/m3-c03-threads-warps-blocks-grids-and-streaming-multiprocessors.md) | [M3-C02](#m3-c02) |
| 54 | <span id="m3-c05">M3-C05</span> | Hardware architecture and topology | [Device memory, HBM, and the cache hierarchy](hardware-architecture-and-topology/m3-c05-device-memory-hbm-and-the-cache-hierarchy.md) | [M3-C01](#m3-c01), [M1-C05](#m1-c05) |
| 55 | <span id="m3-c06">M3-C06</span> | Hardware architecture and topology | [Registers, shared memory, and local resource pressure](hardware-architecture-and-topology/m3-c06-registers-shared-memory-and-local-resource-pressure.md) | [M3-C03](#m3-c03), [M3-C05](#m3-c05) |
| 56 | <span id="m3-c04">M3-C04</span> | Hardware architecture and topology | [Occupancy, latency hiding, and hardware utilization](hardware-architecture-and-topology/m3-c04-occupancy-latency-hiding-and-hardware-utilization.md) | [M3-C03](#m3-c03), [M3-C06](#m3-c06) |
| 57 | <span id="m3-c07">M3-C07</span> | Kernels, compilers, and execution | [Memory coalescing, alignment, and tensor layouts](kernels-compilers-and-execution/m3-c07-memory-coalescing-alignment-and-tensor-layouts.md) | [M3-C03](#m3-c03), [M3-C05](#m3-c05), [M1-C05](#m1-c05) |
| 58 | <span id="m3-c08">M3-C08</span> | Kernels, compilers, and execution | [Tiling and reuse through the memory hierarchy](kernels-compilers-and-execution/m3-c08-tiling-and-reuse-through-the-memory-hierarchy.md) | [M3-C07](#m3-c07), [M3-C06](#m3-c06), [M1-C04](#m1-c04) |
| 59 | <span id="m3-c09">M3-C09</span> | Kernels, compilers, and execution | [Tensor cores and supported matrix operations](kernels-compilers-and-execution/m3-c09-tensor-cores-and-supported-matrix-operations.md) | [M3-C08](#m3-c08), [M3-C02](#m3-c02), [M1-C07](#m1-c07) |
| 60 | <span id="m3-c10">M3-C10</span> | State, memory, and caching | [Host and device buffer placement and lifetime](state-memory-and-caching/m3-c10-host-and-device-buffer-placement-and-lifetime.md) | [M3-C05](#m3-c05), [M2-C04](#m2-c04) |
| 61 | <span id="m3-c11">M3-C11</span> | Runtime and concurrency | [Streams, events, and dependency ordering](runtime-and-concurrency/m3-c11-streams-events-and-dependency-ordering.md) | [M3-C03](#m3-c03), [M3-C10](#m3-c10), [M2-C10](#m2-c10) |
| 62 | <span id="m3-c12">M3-C12</span> | Runtime and concurrency | [Asynchronous copies and useful overlap](runtime-and-concurrency/m3-c12-asynchronous-copies-and-useful-overlap.md) | [M3-C11](#m3-c11) |
| 63 | <span id="m3-c13">M3-C13</span> | Hardware architecture and topology | [PCIe, NVLink, NUMA, and device topology](hardware-architecture-and-topology/m3-c13-pcie-nvlink-numa-and-device-topology.md) | [M3-C02](#m3-c02), [M3-C10](#m3-c10) |
| 64 | <span id="m3-c14">M3-C14</span> | Networking and communication | [Moving tensors between devices and hosts](networking-and-communication/m3-c14-moving-tensors-between-devices-and-hosts.md) | [M3-C13](#m3-c13), [M3-C12](#m3-c12) |
| 65 | <span id="m9-c16">M9-C16</span> | Hardware architecture and topology | [Recording hardware conditions that change measurements](hardware-architecture-and-topology/m9-c16-recording-hardware-conditions-that-change-measurements.md) | [M3-C14](#m3-c14), [M9-C02](#m9-c02) |
| 66 | <span id="m3-c15">M3-C15</span> | Measurement, experimentation, and economics | [Counting FLOPs and bytes at a defined boundary](measurement-experimentation-and-economics/m3-c15-counting-flops-and-bytes-at-a-defined-boundary.md) | [M3-C09](#m3-c09), [M3-C07](#m3-c07), [M1-C08](#m1-c08) |
| 67 | <span id="m3-c16">M3-C16</span> | Measurement, experimentation, and economics | [Using the roofline model to predict bottlenecks](measurement-experimentation-and-economics/m3-c16-using-the-roofline-model-to-predict-bottlenecks.md) | [M3-C15](#m3-c15), [M3-C02](#m3-c02), [M3-C04](#m3-c04) |
| 68 | <span id="m3-c17">M3-C17</span> | Scheduling and queueing | [Batching, weight reuse, and shifting bottlenecks](scheduling-and-queueing/m3-c17-batching-weight-reuse-and-shifting-bottlenecks.md) | [M3-C16](#m3-c16), [M1-C18](#m1-c18) |
| 69 | <span id="m3-c18">M3-C18</span> | Numerics and correctness | [Validating GPU computation and memory movement](numerics-and-correctness/m3-c18-validating-gpu-computation-and-memory-movement.md) | [M3-C14](#m3-c14), [M3-C09](#m3-c09), [M9-C17](#m9-c17) |
| 70 | <span id="m9-c12">M9-C12</span> | Measurement, experimentation, and economics | [Reading CPU-GPU timelines and scheduling gaps](measurement-experimentation-and-economics/m9-c12-reading-cpu-gpu-timelines-and-scheduling-gaps.md) | [M3-C18](#m3-c18), [M9-C02](#m9-c02) |
| 71 | <span id="m9-c13">M9-C13</span> | Measurement, experimentation, and economics | [Using kernel profilers to explain hardware bottlenecks](measurement-experimentation-and-economics/m9-c13-using-kernel-profilers-to-explain-hardware-bottlenecks.md) | [M9-C12](#m9-c12), [M3-C16](#m3-c16), [M3-C06](#m3-c06) |
| 72 | <span id="m3-c19">M3-C19</span> | Measurement, experimentation, and economics | [Designing trustworthy asynchronous GPU benchmarks](measurement-experimentation-and-economics/m3-c19-designing-trustworthy-asynchronous-gpu-benchmarks.md) | [M3-C18](#m3-c18), [M3-C11](#m3-c11), [M9-C02](#m9-c02), [M9-C07](#m9-c07), [M9-C16](#m9-c16) |
| 73 | <span id="m3-c20">M3-C20</span> | Measurement, experimentation, and economics | [Benchmarking memory copies across sizes and paths](measurement-experimentation-and-economics/m3-c20-benchmarking-memory-copies-across-sizes-and-paths.md) | [M3-C19](#m3-c19), [M3-C14](#m3-c14) |
| 74 | <span id="m3-c21">M3-C21</span> | Measurement, experimentation, and economics | [Benchmarking matrix-vector multiplication across shapes](measurement-experimentation-and-economics/m3-c21-benchmarking-matrix-vector-multiplication-across-shapes.md) | [M3-C20](#m3-c20), [M3-C16](#m3-c16) |
| 75 | <span id="m3-c22">M3-C22</span> | Measurement, experimentation, and economics | [Benchmarking matrix-matrix multiplication across shapes](measurement-experimentation-and-economics/m3-c22-benchmarking-matrix-matrix-multiplication-across-shapes.md) | [M3-C21](#m3-c21), [M3-C17](#m3-c17) |
| 76 | <span id="m3-c23">M3-C23</span> | Measurement, experimentation, and economics | [Explaining GPU profiles and end-to-end serving effects](measurement-experimentation-and-economics/m3-c23-explaining-gpu-profiles-and-end-to-end-serving-effects.md) | [M3-C22](#m3-c22), [M9-C12](#m9-c12), [M9-C13](#m9-c13), [M1-C20](#m1-c20) |

### 5. Kernels, graph execution, and controlled optimization

Explain RNG contracts before fused sampling; establish reproducible graph comparisons and regression gates before tuning.

| Authoring position | Chapter ID | Category | Chapter name | Direct prerequisites |
| --- | --- | --- | --- | --- |
| 77 | <span id="m4-c01">M4-C01</span> | Kernels, compilers, and execution | [Defining a GPU kernel and its contract](kernels-compilers-and-execution/m4-c01-defining-a-gpu-kernel-and-its-contract.md) | [M3-C23](#m3-c23), [M9-C01](#m9-c01) |
| 78 | <span id="m4-c02">M4-C02</span> | Kernels, compilers, and execution | [Mapping an operation onto CUDA threads and blocks](kernels-compilers-and-execution/m4-c02-mapping-an-operation-onto-cuda-threads-and-blocks.md) | [M4-C01](#m4-c01), [M3-C03](#m3-c03) |
| 79 | <span id="m4-c03">M4-C03</span> | Kernels, compilers, and execution | [Understanding the Triton programming model](kernels-compilers-and-execution/m4-c03-understanding-the-triton-programming-model.md) | [M4-C02](#m4-c02), [M3-C08](#m3-c08) |
| 80 | <span id="m4-c04">M4-C04</span> | Kernels, compilers, and execution | [Compilation, specialization, and the warm execution path](kernels-compilers-and-execution/m4-c04-compilation-specialization-and-the-warm-execution-path.md) | [M4-C03](#m4-c03), [M3-C02](#m3-c02) |
| 81 | <span id="m4-c05">M4-C05</span> | Kernels, compilers, and execution | [Tiling an operation for data reuse](kernels-compilers-and-execution/m4-c05-tiling-an-operation-for-data-reuse.md) | [M4-C04](#m4-c04), [M3-C08](#m3-c08) |
| 82 | <span id="m4-c06">M4-C06</span> | Kernels, compilers, and execution | [Parallel reductions and synchronization](kernels-compilers-and-execution/m4-c06-parallel-reductions-and-synchronization.md) | [M4-C05](#m4-c05), [M1-C06](#m1-c06), [M1-C07](#m1-c07) |
| 83 | <span id="m4-c07">M4-C07</span> | Numerics and correctness | [Online softmax and stable incremental reductions](numerics-and-correctness/m4-c07-online-softmax-and-stable-incremental-reductions.md) | [M4-C06](#m4-c06), [M1-C10](#m1-c10) |
| 84 | <span id="m4-c08">M4-C08</span> | Kernels, compilers, and execution | [Kernel fusion and its tradeoffs](kernels-compilers-and-execution/m4-c08-kernel-fusion-and-its-tradeoffs.md) | [M4-C05](#m4-c05), [M4-C06](#m4-c06) |
| 85 | <span id="m4-c09">M4-C09</span> | Kernels, compilers, and execution | [Register pressure, occupancy, and spills in kernel design](kernels-compilers-and-execution/m4-c09-register-pressure-occupancy-and-spills-in-kernel-design.md) | [M4-C08](#m4-c08), [M3-C04](#m3-c04), [M3-C06](#m3-c06) |
| 86 | <span id="m4-c10">M4-C10</span> | Kernels, compilers, and execution | [Shape specialization, padding, and dispatch](kernels-compilers-and-execution/m4-c10-shape-specialization-padding-and-dispatch.md) | [M4-C09](#m4-c09), [M4-C04](#m4-c04) |
| 87 | <span id="m4-c11">M4-C11</span> | Kernels, compilers, and execution | [FlashAttention as an IO-aware attention algorithm](kernels-compilers-and-execution/m4-c11-flashattention-as-an-io-aware-attention-algorithm.md) | [M4-C07](#m4-c07), [M4-C10](#m4-c10), [M1-C11](#m1-c11) |
| 88 | <span id="m4-c12">M4-C12</span> | Kernels, compilers, and execution | [Distinguishing FlashAttention, PagedAttention, and prefix caching](kernels-compilers-and-execution/m4-c12-distinguishing-flashattention-pagedattention-and-prefix-caching.md) | [M4-C11](#m4-c11), [M2-C07](#m2-c07), [M2-C13](#m2-c13) |
| 89 | <span id="m4-c13">M4-C13</span> | Runtime and concurrency | [Tracing CPU-to-GPU launch overhead](runtime-and-concurrency/m4-c13-tracing-cpu-to-gpu-launch-overhead.md) | [M4-C01](#m4-c01), [M9-C12](#m9-c12) |
| 90 | <span id="m4-c14">M4-C14</span> | Runtime and concurrency | [CPU-GPU synchronization and hidden serialization](runtime-and-concurrency/m4-c14-cpu-gpu-synchronization-and-hidden-serialization.md) | [M4-C13](#m4-c13), [M3-C11](#m3-c11) |
| 91 | <span id="m4-c15">M4-C15</span> | Kernels, compilers, and execution | [CUDA Graph capture, instantiation, and replay](kernels-compilers-and-execution/m4-c15-cuda-graph-capture-instantiation-and-replay.md) | [M4-C14](#m4-c14), [M4-C04](#m4-c04) |
| 92 | <span id="m4-c16">M4-C16</span> | Runtime and concurrency | [Replay constraints, graph variants, and buffer lifetimes](runtime-and-concurrency/m4-c16-replay-constraints-graph-variants-and-buffer-lifetimes.md) | [M4-C15](#m4-c15), [M4-C10](#m4-c10), [M2-C10](#m2-c10) |
| 93 | <span id="m9-c11">M9-C11</span> | Measurement, experimentation, and economics | [Controlled comparisons, warmup, and reproducibility](measurement-experimentation-and-economics/m9-c11-controlled-comparisons-warmup-and-reproducibility.md) | [M4-C16](#m4-c16), [M9-C07](#m9-c07), [M2-C13](#m2-c13) |
| 94 | <span id="m4-c17">M4-C17</span> | Kernels, compilers, and execution | [Designing a fused normalization kernel](kernels-compilers-and-execution/m4-c17-designing-a-fused-normalization-kernel.md) | [M4-C08](#m4-c08), [M4-C10](#m4-c10), [M1-C13](#m1-c13) |
| 95 | <span id="m4-c19">M4-C19</span> | Numerics and correctness | [Randomness, reproducibility, and sampling equivalence](numerics-and-correctness/m4-c19-randomness-reproducibility-and-sampling-equivalence.md) | [M1-C15](#m1-c15), [M9-C07](#m9-c07) |
| 96 | <span id="m4-c18">M4-C18</span> | Kernels, compilers, and execution | [Designing a fused sampling kernel](kernels-compilers-and-execution/m4-c18-designing-a-fused-sampling-kernel.md) | [M4-C19](#m4-c19), [M4-C06](#m4-c06), [M4-C10](#m4-c10), [M1-C15](#m1-c15) |
| 97 | <span id="m4-c20">M4-C20</span> | Numerics and correctness | [Validating fused kernels and graph replay](numerics-and-correctness/m4-c20-validating-fused-kernels-and-graph-replay.md) | [M4-C16](#m4-c16), [M4-C17](#m4-c17), [M4-C18](#m4-c18), [M9-C17](#m9-c17), [M9-C11](#m9-c11) |
| 98 | <span id="m9-c27">M9-C27</span> | Measurement, experimentation, and economics | [Designing regression experiments and validation gates](measurement-experimentation-and-economics/m9-c27-designing-regression-experiments-and-validation-gates.md) | [M4-C20](#m4-c20), [M9-C11](#m9-c11), [M9-C01](#m9-c01) |
| 99 | <span id="m4-c21">M4-C21</span> | Measurement, experimentation, and economics | [Tuning kernels with controlled experiments](measurement-experimentation-and-economics/m4-c21-tuning-kernels-with-controlled-experiments.md) | [M4-C20](#m4-c20), [M4-C09](#m4-c09), [M9-C13](#m9-c13), [M9-C27](#m9-c27) |
| 100 | <span id="m4-c22">M4-C22</span> | Measurement, experimentation, and economics | [Benchmarking realistic shapes and execution modes](measurement-experimentation-and-economics/m4-c22-benchmarking-realistic-shapes-and-execution-modes.md) | [M4-C21](#m4-c21), [M9-C03](#m9-c03), [M9-C04](#m9-c04), [M9-C05](#m9-c05) |
| 101 | <span id="m4-c23">M4-C23</span> | Runtime and concurrency | [Integrating a fused kernel into the generator](runtime-and-concurrency/m4-c23-integrating-a-fused-kernel-into-the-generator.md) | [M4-C22](#m4-c22), [M1-C16](#m1-c16), [M2-C19](#m2-c19) |
| 102 | <span id="m4-c24">M4-C24</span> | Measurement, experimentation, and economics | [Verifying end-to-end generator improvements](measurement-experimentation-and-economics/m4-c24-verifying-end-to-end-generator-improvements.md) | [M4-C23](#m4-c23), [M1-C20](#m1-c20), [M9-C27](#m9-c27) |

### 6. Serving, queueing, and load methodology

Explain synchronization before IPC and queues; establish workload, load-generator, SLO, lifecycle, and invariance checks before policy and capacity comparisons.

| Authoring position | Chapter ID | Category | Chapter name | Direct prerequisites |
| --- | --- | --- | --- | --- |
| 103 | <span id="m5-c01">M5-C01</span> | Scheduling and queueing | [Separating the model executor from the serving scheduler](scheduling-and-queueing/m5-c01-separating-the-model-executor-from-the-serving-scheduler.md) | [M4-C24](#m4-c24), [M2-C19](#m2-c19), [M1-C18](#m1-c18) |
| 104 | <span id="m5-c02">M5-C02</span> | Runtime and concurrency | [Processes, threads, and operating-system scheduling](runtime-and-concurrency/m5-c02-processes-threads-and-operating-system-scheduling.md) | [M5-C01](#m5-c01), [M2-C04](#m2-c04) |
| 105 | <span id="m5-c05">M5-C05</span> | Runtime and concurrency | [Synchronization, ownership, and resource lifetimes](runtime-and-concurrency/m5-c05-synchronization-ownership-and-resource-lifetimes.md) | [M5-C02](#m5-c02), [M2-C11](#m2-c11) |
| 106 | <span id="m5-c03">M5-C03</span> | Runtime and concurrency | [IPC and shared-memory communication](runtime-and-concurrency/m5-c03-ipc-and-shared-memory-communication.md) | [M5-C02](#m5-c02), [M5-C05](#m5-c05) |
| 107 | <span id="m5-c04">M5-C04</span> | Runtime and concurrency | [Producer-consumer queues and bounded work](runtime-and-concurrency/m5-c04-producer-consumer-queues-and-bounded-work.md) | [M5-C02](#m5-c02), [M5-C05](#m5-c05) |
| 108 | <span id="m5-c06">M5-C06</span> | Runtime and concurrency | [Asynchronous execution and completion-driven progress](runtime-and-concurrency/m5-c06-asynchronous-execution-and-completion-driven-progress.md) | [M5-C03](#m5-c03), [M5-C04](#m5-c04), [M3-C11](#m3-c11) |
| 109 | <span id="m9-c22">M9-C22</span> | Runtime and concurrency | [Verifying ownership and memory safety under concurrency](runtime-and-concurrency/m9-c22-verifying-ownership-and-memory-safety-under-concurrency.md) | [M5-C06](#m5-c06), [M2-C20](#m2-c20), [M3-C18](#m3-c18) |
| 110 | <span id="m5-c07">M5-C07</span> | Measurement, experimentation, and economics | [Describing mixed serving workloads and arrival traces](measurement-experimentation-and-economics/m5-c07-describing-mixed-serving-workloads-and-arrival-traces.md) | [M5-C01](#m5-c01), [M9-C02](#m9-c02) |
| 111 | <span id="m5-c08">M5-C08</span> | Scheduling and queueing | [Queueing delay, service time, and request latency](scheduling-and-queueing/m5-c08-queueing-delay-service-time-and-request-latency.md) | [M5-C07](#m5-c07), [M5-C04](#m5-c04), [M9-C03](#m9-c03), [M9-C05](#m9-c05) |
| 112 | <span id="m5-c09">M5-C09</span> | Scheduling and queueing | [Applying Little’s law with consistent boundaries](scheduling-and-queueing/m5-c09-applying-little-s-law-with-consistent-boundaries.md) | [M5-C08](#m5-c08), [M9-C07](#m9-c07) |
| 113 | <span id="m5-c10">M5-C10</span> | Scheduling and queueing | [Utilization, variability, and tail latency](scheduling-and-queueing/m5-c10-utilization-variability-and-tail-latency.md) | [M5-C09](#m5-c09), [M3-C16](#m3-c16) |
| 114 | <span id="m9-c08">M9-C08</span> | Measurement, experimentation, and economics | [Designing representative serving workloads](measurement-experimentation-and-economics/m9-c08-designing-representative-serving-workloads.md) | [M5-C07](#m5-c07), [M2-C13](#m2-c13) |
| 115 | <span id="m9-c09">M9-C09</span> | Measurement, experimentation, and economics | [Open-loop load generation and coordinated omission](measurement-experimentation-and-economics/m9-c09-open-loop-load-generation-and-coordinated-omission.md) | [M9-C08](#m9-c08), [M5-C08](#m5-c08) |
| 116 | <span id="m9-c10">M9-C10</span> | Measurement, experimentation, and economics | [Validating the load generator and request accounting](measurement-experimentation-and-economics/m9-c10-validating-the-load-generator-and-request-accounting.md) | [M9-C09](#m9-c09), [M5-C06](#m5-c06) |
| 117 | <span id="m9-c06">M9-C06</span> | Measurement, experimentation, and economics | [Defining SLOs, goodput, and useful capacity](measurement-experimentation-and-economics/m9-c06-defining-slos-goodput-and-useful-capacity.md) | [M9-C03](#m9-c03), [M9-C04](#m9-c04), [M9-C05](#m9-c05), [M9-C07](#m9-c07), [M9-C10](#m9-c10), [M5-C10](#m5-c10) |
| 118 | <span id="m5-c11">M5-C11</span> | Scheduling and queueing | [Defining a static batching baseline](scheduling-and-queueing/m5-c11-defining-a-static-batching-baseline.md) | [M5-C06](#m5-c06), [M5-C10](#m5-c10), [M3-C17](#m3-c17) |
| 119 | <span id="m5-c12">M5-C12</span> | Scheduling and queueing | [Continuous batching at execution boundaries](scheduling-and-queueing/m5-c12-continuous-batching-at-execution-boundaries.md) | [M5-C11](#m5-c11), [M2-C10](#m2-c10) |
| 120 | <span id="m5-c13">M5-C13</span> | Scheduling and queueing | [Budgeting work for each execution iteration](scheduling-and-queueing/m5-c13-budgeting-work-for-each-execution-iteration.md) | [M5-C12](#m5-c12), [M4-C10](#m4-c10), [M4-C16](#m4-c16) |
| 121 | <span id="m5-c14">M5-C14</span> | Scheduling and queueing | [Planning for future KV-cache growth](scheduling-and-queueing/m5-c14-planning-for-future-kv-cache-growth.md) | [M5-C13](#m5-c13), [M2-C15](#m2-c15), [M9-C15](#m9-c15) |
| 122 | <span id="m5-c15">M5-C15</span> | Scheduling and queueing | [Admission control and backpressure](scheduling-and-queueing/m5-c15-admission-control-and-backpressure.md) | [M5-C14](#m5-c14), [M5-C04](#m5-c04), [M9-C06](#m9-c06) |
| 123 | <span id="m5-c16">M5-C16</span> | Scheduling and queueing | [Fairness, priorities, and starvation prevention](scheduling-and-queueing/m5-c16-fairness-priorities-and-starvation-prevention.md) | [M5-C15](#m5-c15), [M5-C10](#m5-c10) |
| 124 | <span id="m5-c17">M5-C17</span> | Scheduling and queueing | [Chunked prefill and resumable prompt processing](scheduling-and-queueing/m5-c17-chunked-prefill-and-resumable-prompt-processing.md) | [M5-C13](#m5-c13), [M1-C18](#m1-c18), [M2-C19](#m2-c19) |
| 125 | <span id="m5-c18">M5-C18</span> | Scheduling and queueing | [Choosing chunk sizes and balancing prefill with decode](scheduling-and-queueing/m5-c18-choosing-chunk-sizes-and-balancing-prefill-with-decode.md) | [M5-C17](#m5-c17), [M5-C16](#m5-c16), [M9-C03](#m9-c03), [M9-C04](#m9-c04) |
| 126 | <span id="m5-c19">M5-C19</span> | Scheduling and queueing | [Preemption, resumption, and the cost of lost progress](scheduling-and-queueing/m5-c19-preemption-resumption-and-the-cost-of-lost-progress.md) | [M5-C18](#m5-c18), [M2-C14](#m2-c14) |
| 127 | <span id="m5-c20">M5-C20</span> | Reliability and capacity control | [Cancellation, deadlines, and worker failure](reliability-and-capacity-control/m5-c20-cancellation-deadlines-and-worker-failure.md) | [M5-C19](#m5-c19), [M2-C16](#m2-c16), [M5-C06](#m5-c06) |
| 128 | <span id="m5-c21">M5-C21</span> | Interfaces, protocols, and streaming | [Streaming results without unbounded buffering](interfaces-protocols-and-streaming/m5-c21-streaming-results-without-unbounded-buffering.md) | [M5-C20](#m5-c20), [M5-C04](#m5-c04), [M1-C16](#m1-c16), [M9-C04](#m9-c04) |
| 129 | <span id="m5-c22">M5-C22</span> | Runtime and concurrency | [Designing the scheduler state machine and executor contract](runtime-and-concurrency/m5-c22-designing-the-scheduler-state-machine-and-executor-contract.md) | [M5-C21](#m5-c21), [M5-C14](#m5-c14), [M5-C16](#m5-c16), [M5-C17](#m5-c17) |
| 130 | <span id="m5-c23">M5-C23</span> | Numerics and correctness | [Validating scheduling and memory invariants](numerics-and-correctness/m5-c23-validating-scheduling-and-memory-invariants.md) | [M5-C22](#m5-c22), [M2-C20](#m2-c20), [M4-C19](#m4-c19), [M9-C22](#m9-c22) |
| 131 | <span id="m9-c21">M9-C21</span> | Reliability and capacity control | [Testing cancellation, deadlines, and terminal states](reliability-and-capacity-control/m9-c21-testing-cancellation-deadlines-and-terminal-states.md) | [M5-C23](#m5-c23), [M9-C19](#m9-c19) |
| 132 | <span id="m9-c23">M9-C23</span> | Numerics and correctness | [Testing batch, schedule, and graph invariance](numerics-and-correctness/m9-c23-testing-batch-schedule-and-graph-invariance.md) | [M5-C23](#m5-c23), [M4-C20](#m4-c20), [M4-C19](#m4-c19) |
| 133 | <span id="m9-c26">M9-C26</span> | Reliability and capacity control | [Load-testing overload, backpressure, and failure recovery](reliability-and-capacity-control/m9-c26-load-testing-overload-backpressure-and-failure-recovery.md) | [M5-C23](#m5-c23), [M9-C21](#m9-c21), [M9-C10](#m9-c10), [M9-C06](#m9-c06) |
| 134 | <span id="m5-c24">M5-C24</span> | Measurement, experimentation, and economics | [Comparing scheduling policies on the same arrival trace](measurement-experimentation-and-economics/m5-c24-comparing-scheduling-policies-on-the-same-arrival-trace.md) | [M5-C23](#m5-c23), [M9-C08](#m9-c08), [M9-C10](#m9-c10), [M9-C21](#m9-c21), [M9-C23](#m9-c23), [M9-C26](#m9-c26), [M9-C27](#m9-c27) |
| 135 | <span id="m5-c25">M5-C25</span> | Measurement, experimentation, and economics | [Measuring sustainable capacity, fairness, and tail behavior](measurement-experimentation-and-economics/m5-c25-measuring-sustainable-capacity-fairness-and-tail-behavior.md) | [M5-C24](#m5-c24), [M9-C06](#m9-c06), [M9-C07](#m9-c07), [M9-C12](#m9-c12) |

### 7. Cache reuse and advanced optimizations

Validate prefix identity, speculative distributions, approximate paths, and fallbacks before integrated optimization conclusions.

| Authoring position | Chapter ID | Category | Chapter name | Direct prerequisites |
| --- | --- | --- | --- | --- |
| 136 | <span id="m6-c01">M6-C01</span> | Numerics and correctness | [Defining an optimization’s correctness and cost contract](numerics-and-correctness/m6-c01-defining-an-optimization-s-correctness-and-cost-contract.md) | [M5-C25](#m5-c25), [M9-C01](#m9-c01), [M9-C27](#m9-c27) |
| 137 | <span id="m6-c02">M6-C02</span> | State, memory, and caching | [Defining prefix identity through equivalent computation](state-memory-and-caching/m6-c02-defining-prefix-identity-through-equivalent-computation.md) | [M6-C01](#m6-c01), [M2-C13](#m2-c13) |
| 138 | <span id="m6-c03">M6-C03</span> | State, memory, and caching | [Tries, radix trees, and longest-prefix matching](state-memory-and-caching/m6-c03-tries-radix-trees-and-longest-prefix-matching.md) | [M6-C02](#m6-c02) |
| 139 | <span id="m6-c04">M6-C04</span> | State, memory, and caching | [Connecting a radix index to paged KV blocks](state-memory-and-caching/m6-c04-connecting-a-radix-index-to-paged-kv-blocks.md) | [M6-C03](#m6-c03), [M2-C12](#m2-c12), [M2-C08](#m2-c08) |
| 140 | <span id="m6-c05">M6-C05</span> | State, memory, and caching | [Reference-safe retention, eviction, and cancellation](state-memory-and-caching/m6-c05-reference-safe-retention-eviction-and-cancellation.md) | [M6-C04](#m6-c04), [M2-C14](#m2-c14), [M5-C20](#m5-c20) |
| 141 | <span id="m6-c06">M6-C06</span> | Scheduling and queueing | [Balancing cache locality, fairness, and load](scheduling-and-queueing/m6-c06-balancing-cache-locality-fairness-and-load.md) | [M6-C05](#m6-c05), [M5-C16](#m5-c16), [M5-C07](#m5-c07) |
| 142 | <span id="m6-c07">M6-C07</span> | Runtime and concurrency | [Integrating prefix caching into prefill and decode](runtime-and-concurrency/m6-c07-integrating-prefix-caching-into-prefill-and-decode.md) | [M6-C06](#m6-c06), [M5-C17](#m5-c17), [M5-C22](#m5-c22) |
| 143 | <span id="m9-c20">M9-C20</span> | Numerics and correctness | [Validating KV reuse and prefix-cache identity](numerics-and-correctness/m9-c20-validating-kv-reuse-and-prefix-cache-identity.md) | [M6-C07](#m6-c07), [M2-C20](#m2-c20), [M9-C17](#m9-c17) |
| 144 | <span id="m6-c08">M6-C08</span> | Numerics and correctness | [Quantization fundamentals: scales, zero points, and rounding](numerics-and-correctness/m6-c08-quantization-fundamentals-scales-zero-points-and-rounding.md) | [M6-C01](#m6-c01), [M1-C07](#m1-c07), [M1-C06](#m1-c06) |
| 145 | <span id="m6-c09">M6-C09</span> | Numerics and correctness | [Weight quantization and grouping granularity](numerics-and-correctness/m6-c09-weight-quantization-and-grouping-granularity.md) | [M6-C08](#m6-c08), [M1-C04](#m1-c04) |
| 146 | <span id="m6-c10">M6-C10</span> | Numerics and correctness | [Calibration and representative data selection](numerics-and-correctness/m6-c10-calibration-and-representative-data-selection.md) | [M6-C09](#m6-c09), [M9-C08](#m9-c08) |
| 147 | <span id="m6-c11">M6-C11</span> | Kernels, compilers, and execution | [Packing, dequantization, and quantized kernel execution](kernels-compilers-and-execution/m6-c11-packing-dequantization-and-quantized-kernel-execution.md) | [M6-C10](#m6-c10), [M4-C10](#m4-c10), [M3-C09](#m3-c09) |
| 148 | <span id="m6-c12">M6-C12</span> | Numerics and correctness | [KV-cache quantization and attention numerics](numerics-and-correctness/m6-c12-kv-cache-quantization-and-attention-numerics.md) | [M6-C11](#m6-c11), [M2-C03](#m2-c03), [M1-C10](#m1-c10) |
| 149 | <span id="m6-c13">M6-C13</span> | Numerics and correctness | [Validating quantization quality and memory savings](numerics-and-correctness/m6-c13-validating-quantization-quality-and-memory-savings.md) | [M6-C12](#m6-c12), [M9-C17](#m9-c17), [M9-C15](#m9-c15), [M9-C11](#m9-c11) |
| 150 | <span id="m6-c14">M6-C14</span> | Model computation and semantics | [Draft proposals and parallel target verification](model-computation-and-semantics/m6-c14-draft-proposals-and-parallel-target-verification.md) | [M6-C01](#m6-c01), [M1-C15](#m1-c15), [M1-C18](#m1-c18) |
| 151 | <span id="m6-c15">M6-C15</span> | Numerics and correctness | [Distribution-preserving speculative acceptance](numerics-and-correctness/m6-c15-distribution-preserving-speculative-acceptance.md) | [M6-C14](#m6-c14), [M1-C06](#m1-c06), [M4-C19](#m4-c19) |
| 152 | <span id="m6-c16">M6-C16</span> | Runtime and concurrency | [Managing draft and target state during speculation](runtime-and-concurrency/m6-c16-managing-draft-and-target-state-during-speculation.md) | [M6-C15](#m6-c15), [M2-C12](#m2-c12), [M5-C20](#m5-c20) |
| 153 | <span id="m9-c18">M9-C18</span> | Numerics and correctness | [Testing sampling distributions and random-state behavior](numerics-and-correctness/m9-c18-testing-sampling-distributions-and-random-state-behavior.md) | [M6-C16](#m6-c16), [M4-C19](#m4-c19), [M9-C07](#m9-c07) |
| 154 | <span id="m6-c17">M6-C17</span> | Measurement, experimentation, and economics | [When speculative decoding helps or hurts](measurement-experimentation-and-economics/m6-c17-when-speculative-decoding-helps-or-hurts.md) | [M6-C16](#m6-c16), [M9-C18](#m9-c18), [M9-C05](#m9-c05), [M9-C11](#m9-c11) |
| 155 | <span id="m6-c18">M6-C18</span> | Interfaces, protocols, and streaming | [Grammar-constrained decoding from tokens to parser state](interfaces-protocols-and-streaming/m6-c18-grammar-constrained-decoding-from-tokens-to-parser-state.md) | [M6-C01](#m6-c01), [M1-C02](#m1-c02), [M1-C15](#m1-c15) |
| 156 | <span id="m6-c19">M6-C19</span> | Interfaces, protocols, and streaming | [Grammar compilation and vocabulary-mask execution](interfaces-protocols-and-streaming/m6-c19-grammar-compilation-and-vocabulary-mask-execution.md) | [M6-C18](#m6-c18), [M4-C10](#m4-c10) |
| 157 | <span id="m6-c20">M6-C20</span> | Interfaces, protocols, and streaming | [Structured-output validity, termination, and failure](interfaces-protocols-and-streaming/m6-c20-structured-output-validity-termination-and-failure.md) | [M6-C19](#m6-c19), [M9-C19](#m9-c19) |
| 158 | <span id="m6-c21">M6-C21</span> | Model computation and semantics | [LoRA foundations and adapter-specific computation](model-computation-and-semantics/m6-c21-lora-foundations-and-adapter-specific-computation.md) | [M6-C01](#m6-c01), [M1-C04](#m1-c04), [M1-C14](#m1-c14) |
| 159 | <span id="m6-c22">M6-C22</span> | State, memory, and caching | [Adapter residency, lifetime, and cache compatibility](state-memory-and-caching/m6-c22-adapter-residency-lifetime-and-cache-compatibility.md) | [M6-C21](#m6-c21), [M6-C02](#m6-c02), [M2-C11](#m2-c11), [M5-C20](#m5-c20) |
| 160 | <span id="m6-c23">M6-C23</span> | Scheduling and queueing | [Batching requests across multiple LoRA adapters](scheduling-and-queueing/m6-c23-batching-requests-across-multiple-lora-adapters.md) | [M6-C22](#m6-c22), [M5-C12](#m5-c12), [M5-C13](#m5-c13) |
| 161 | <span id="m6-c24">M6-C24</span> | Runtime and concurrency | [Composing optimizations without breaking contracts](runtime-and-concurrency/m6-c24-composing-optimizations-without-breaking-contracts.md) | [M6-C07](#m6-c07), [M6-C13](#m6-c13), [M6-C17](#m6-c17), [M6-C20](#m6-c20), [M6-C23](#m6-c23) |
| 162 | <span id="m6-c25">M6-C25</span> | Reliability and capacity control | [Handling unsupported cases and optimization failures](reliability-and-capacity-control/m6-c25-handling-unsupported-cases-and-optimization-failures.md) | [M6-C24](#m6-c24), [M5-C20](#m5-c20) |
| 163 | <span id="m9-c24">M9-C24</span> | Numerics and correctness | [Validating approximate and constrained optimization paths](numerics-and-correctness/m9-c24-validating-approximate-and-constrained-optimization-paths.md) | [M6-C25](#m6-c25), [M9-C18](#m9-c18), [M9-C20](#m9-c20) |
| 164 | <span id="m6-c26">M6-C26</span> | Measurement, experimentation, and economics | [Designing the optimization workload and comparison matrix](measurement-experimentation-and-economics/m6-c26-designing-the-optimization-workload-and-comparison-matrix.md) | [M6-C25](#m6-c25), [M9-C08](#m9-c08), [M9-C11](#m9-c11), [M9-C24](#m9-c24) |
| 165 | <span id="m6-c27">M6-C27</span> | Runtime and concurrency | [Building prefix caching and one additional optimization](runtime-and-concurrency/m6-c27-building-prefix-caching-and-one-additional-optimization.md) | [M6-C26](#m6-c26), [M9-C20](#m9-c20), [M5-C23](#m5-c23) |
| 166 | <span id="m6-c28">M6-C28</span> | Measurement, experimentation, and economics | [Establishing end-to-end benefit and regression boundaries](measurement-experimentation-and-economics/m6-c28-establishing-end-to-end-benefit-and-regression-boundaries.md) | [M6-C27](#m6-c27), [M9-C06](#m9-c06), [M9-C27](#m9-c27) |

### 8. Distributed inference and economics

Establish collective semantics and completion measurement before partitioning, distributed validation, scaling, and cost analysis.

| Authoring position | Chapter ID | Category | Chapter name | Direct prerequisites |
| --- | --- | --- | --- | --- |
| 167 | <span id="m7-c01">M7-C01</span> | Parallelism and decomposition | [Why distribute inference across GPUs?](parallelism-and-decomposition/m7-c01-why-distribute-inference-across-gpus.md) | [M6-C28](#m6-c28), [M3-C23](#m3-c23), [M5-C25](#m5-c25) |
| 168 | <span id="m7-c02">M7-C02</span> | Hardware architecture and topology | [Mapping GPU and network topology before partitioning](hardware-architecture-and-topology/m7-c02-mapping-gpu-and-network-topology-before-partitioning.md) | [M7-C01](#m7-c01), [M3-C13](#m3-c13), [M9-C16](#m9-c16) |
| 169 | <span id="m7-c03">M7-C03</span> | Runtime and concurrency | [Workers, ranks, process groups, and communicators](runtime-and-concurrency/m7-c03-workers-ranks-process-groups-and-communicators.md) | [M7-C02](#m7-c02), [M5-C03](#m5-c03), [M5-C06](#m5-c06) |
| 170 | <span id="m7-c04">M7-C04</span> | Networking and communication | [Point-to-point transfers and communication contracts](networking-and-communication/m7-c04-point-to-point-transfers-and-communication-contracts.md) | [M7-C03](#m7-c03), [M3-C14](#m3-c14), [M3-C11](#m3-c11) |
| 171 | <span id="m7-c05">M7-C05</span> | Networking and communication | [Reductions and AllReduce from first principles](networking-and-communication/m7-c05-reductions-and-allreduce-from-first-principles.md) | [M7-C04](#m7-c04), [M1-C06](#m1-c06), [M1-C07](#m1-c07) |
| 172 | <span id="m7-c06">M7-C06</span> | Networking and communication | [AllGather and ReduceScatter as layout transformations](networking-and-communication/m7-c06-allgather-and-reducescatter-as-layout-transformations.md) | [M7-C05](#m7-c05), [M1-C05](#m1-c05) |
| 173 | <span id="m7-c07">M7-C07</span> | Networking and communication | [AllToAll and variable-size token exchange](networking-and-communication/m7-c07-alltoall-and-variable-size-token-exchange.md) | [M7-C06](#m7-c06) |
| 174 | <span id="m7-c08">M7-C08</span> | Networking and communication | [Modeling communication latency and bandwidth costs](networking-and-communication/m7-c08-modeling-communication-latency-and-bandwidth-costs.md) | [M7-C07](#m7-c07), [M3-C16](#m3-c16) |
| 175 | <span id="m7-c09">M7-C09</span> | Runtime and concurrency | [Overlapping compute and communication safely](runtime-and-concurrency/m7-c09-overlapping-compute-and-communication-safely.md) | [M7-C08](#m7-c08), [M3-C12](#m3-c12) |
| 176 | <span id="m9-c14">M9-C14</span> | Networking and communication | [Measuring transfer and collective completion](networking-and-communication/m9-c14-measuring-transfer-and-collective-completion.md) | [M7-C09](#m7-c09), [M9-C02](#m9-c02), [M9-C16](#m9-c16) |
| 177 | <span id="m7-c10">M7-C10</span> | Parallelism and decomposition | [Tensor parallelism for linear layers](parallelism-and-decomposition/m7-c10-tensor-parallelism-for-linear-layers.md) | [M7-C06](#m7-c06), [M1-C04](#m1-c04), [M9-C14](#m9-c14) |
| 178 | <span id="m7-c11">M7-C11</span> | Parallelism and decomposition | [Tensor-parallel attention and KV ownership](parallelism-and-decomposition/m7-c11-tensor-parallel-attention-and-kv-ownership.md) | [M7-C10](#m7-c10), [M2-C02](#m2-c02), [M2-C03](#m2-c03) |
| 179 | <span id="m7-c12">M7-C12</span> | Parallelism and decomposition | [Pipeline parallelism for inference](parallelism-and-decomposition/m7-c12-pipeline-parallelism-for-inference.md) | [M7-C04](#m7-c04), [M1-C14](#m1-c14), [M1-C18](#m1-c18) |
| 180 | <span id="m7-c13">M7-C13</span> | Scheduling and queueing | [Pipeline bubbles, stage balance, and scheduling](scheduling-and-queueing/m7-c13-pipeline-bubbles-stage-balance-and-scheduling.md) | [M7-C12](#m7-c12), [M5-C10](#m5-c10), [M5-C13](#m5-c13) |
| 181 | <span id="m7-c14">M7-C14</span> | Parallelism and decomposition | [Data parallelism across serving replicas](parallelism-and-decomposition/m7-c14-data-parallelism-across-serving-replicas.md) | [M7-C03](#m7-c03), [M5-C22](#m5-c22) |
| 182 | <span id="m7-c15">M7-C15</span> | Distributed coordination and routing | [Routing requests with load and cache locality](distributed-coordination-and-routing/m7-c15-routing-requests-with-load-and-cache-locality.md) | [M7-C14](#m7-c14), [M6-C06](#m6-c06), [M5-C15](#m5-c15) |
| 183 | <span id="m7-c16">M7-C16</span> | Model computation and semantics | [Mixture-of-experts computation and storage](model-computation-and-semantics/m7-c16-mixture-of-experts-computation-and-storage.md) | [M1-C13](#m1-c13), [M1-C15](#m1-c15), [M7-C01](#m7-c01) |
| 184 | <span id="m7-c17">M7-C17</span> | Parallelism and decomposition | [Expert parallelism and dispatch-combine execution](parallelism-and-decomposition/m7-c17-expert-parallelism-and-dispatch-combine-execution.md) | [M7-C16](#m7-c16), [M7-C07](#m7-c07) |
| 185 | <span id="m7-c18">M7-C18</span> | Scheduling and queueing | [Expert imbalance, capacity, and token correctness](scheduling-and-queueing/m7-c18-expert-imbalance-capacity-and-token-correctness.md) | [M7-C17](#m7-c17), [M5-C16](#m5-c16) |
| 186 | <span id="m7-c19">M7-C19</span> | Parallelism and decomposition | [Context parallelism and distributed attention state](parallelism-and-decomposition/m7-c19-context-parallelism-and-distributed-attention-state.md) | [M7-C11](#m7-c11), [M7-C09](#m7-c09), [M4-C07](#m4-c07), [M1-C11](#m1-c11) |
| 187 | <span id="m7-c20">M7-C20</span> | Parallelism and decomposition | [Combining parallelism strategies and placement](parallelism-and-decomposition/m7-c20-combining-parallelism-strategies-and-placement.md) | [M7-C13](#m7-c13), [M7-C15](#m7-c15), [M7-C18](#m7-c18), [M7-C19](#m7-c19) |
| 188 | <span id="m7-c21">M7-C21</span> | State, memory, and caching | [Distributed weights, KV caches, and memory accounting](state-memory-and-caching/m7-c21-distributed-weights-kv-caches-and-memory-accounting.md) | [M7-C20](#m7-c20), [M9-C15](#m9-c15), [M6-C22](#m6-c22) |
| 189 | <span id="m7-c22">M7-C22</span> | Distributed coordination and routing | [Coordinating requests and execution across workers](distributed-coordination-and-routing/m7-c22-coordinating-requests-and-execution-across-workers.md) | [M7-C21](#m7-c21), [M5-C22](#m5-c22) |
| 190 | <span id="m7-c23">M7-C23</span> | Reliability and capacity control | [Collective failures, timeouts, and recovery boundaries](reliability-and-capacity-control/m7-c23-collective-failures-timeouts-and-recovery-boundaries.md) | [M7-C22](#m7-c22), [M7-C05](#m7-c05), [M5-C20](#m5-c20) |
| 191 | <span id="m7-c24">M7-C24</span> | Parallelism and decomposition | [Prefill-decode disaggregation and its tradeoffs](parallelism-and-decomposition/m7-c24-prefill-decode-disaggregation-and-its-tradeoffs.md) | [M7-C23](#m7-c23), [M1-C18](#m1-c18), [M7-C08](#m7-c08) |
| 192 | <span id="m7-c25">M7-C25</span> | Networking and communication | [Transferring KV state with a safe handoff](networking-and-communication/m7-c25-transferring-kv-state-with-a-safe-handoff.md) | [M7-C24](#m7-c24), [M2-C10](#m2-c10), [M7-C21](#m7-c21) |
| 193 | <span id="m7-c26">M7-C26</span> | Distributed coordination and routing | [Balancing disaggregated stages and transfer capacity](distributed-coordination-and-routing/m7-c26-balancing-disaggregated-stages-and-transfer-capacity.md) | [M7-C25](#m7-c25), [M7-C15](#m7-c15), [M9-C06](#m9-c06) |
| 194 | <span id="m7-c27">M7-C27</span> | Numerics and correctness | [Validating distributed computation and state](numerics-and-correctness/m7-c27-validating-distributed-computation-and-state.md) | [M7-C26](#m7-c26), [M9-C17](#m9-c17), [M9-C18](#m9-c18), [M9-C22](#m9-c22), [M9-C23](#m9-c23) |
| 195 | <span id="m7-c28">M7-C28</span> | Runtime and concurrency | [Running a model across two GPUs](runtime-and-concurrency/m7-c28-running-a-model-across-two-gpus.md) | [M7-C27](#m7-c27), [M7-C10](#m7-c10), [M7-C12](#m7-c12) |
| 196 | <span id="m7-c29">M7-C29</span> | Measurement, experimentation, and economics | [Profiling compute, communication, and waiting](measurement-experimentation-and-economics/m7-c29-profiling-compute-communication-and-waiting.md) | [M7-C28](#m7-c28), [M9-C14](#m9-c14), [M9-C12](#m9-c12) |
| 197 | <span id="m7-c30">M7-C30</span> | Measurement, experimentation, and economics | [When adding a GPU reduces latency and when it does not](measurement-experimentation-and-economics/m7-c30-when-adding-a-gpu-reduces-latency-and-when-it-does-not.md) | [M7-C29](#m7-c29), [M9-C06](#m9-c06), [M9-C11](#m9-c11), [M9-C07](#m9-c07) |
| 198 | <span id="m9-c28">M9-C28</span> | Measurement, experimentation, and economics | [Evaluating cost and energy per useful result](measurement-experimentation-and-economics/m9-c28-evaluating-cost-and-energy-per-useful-result.md) | [M7-C30](#m7-c30), [M9-C06](#m9-c06), [M9-C15](#m9-c15), [M9-C16](#m9-c16) |

### 9. Integrated serving validation and final synthesis

Validate the integrated text-generation pipeline from Modules 1–7, consolidate all nine milestones, and establish the complete report methodology.

| Authoring position | Chapter ID | Category | Chapter name | Direct prerequisites |
| --- | --- | --- | --- | --- |
| 199 | <span id="m9-c25">M9-C25</span> | Numerics and correctness | [Validating the text-generation serving pipeline end to end](numerics-and-correctness/m9-c25-validating-the-text-generation-serving-pipeline-end-to-end.md) | [M6-C24](#m6-c24), [M9-C19](#m9-c19), [M9-C20](#m9-c20), [M9-C24](#m9-c24), [M5-C21](#m5-c21), [M7-C27](#m7-c27), [M9-C21](#m9-c21), [M9-C26](#m9-c26) |
| 200 | <span id="m9-c29">M9-C29</span> | Measurement, experimentation, and economics | [Validating the nine integrated build milestones](measurement-experimentation-and-economics/m9-c29-validating-the-nine-integrated-build-milestones.md) | [M9-C25](#m9-c25), [M7-C30](#m7-c30), [M6-C28](#m6-c28), [M9-C26](#m9-c26), [M9-C23](#m9-c23) |
| 201 | <span id="m9-c30">M9-C30</span> | Measurement, experimentation, and economics | [Publishing a reproducible correctness and performance report](measurement-experimentation-and-economics/m9-c30-publishing-a-reproducible-correctness-and-performance-report.md) | [M9-C29](#m9-c29), [M9-C28](#m9-c28), [M9-C27](#m9-c27), [M9-C13](#m9-c13) |

## Scope and maintenance

Module 8 is excluded. M9-C25 covers text-generation serving from prompt preparation to terminal output using Modules 1–7. M9-C29 consolidates the nine milestones, whose final milestone is an integrated text-generation pipeline and load-tested API. M9-C30 covers reproducible correctness and performance reporting for that scope. All three follow earlier chapters in this schedule without a pending module prerequisite.

Storage and persistence has no current chapter outlines. It contributes no chapter IDs or inferred prerequisites to this plan.

Module 9 support is required throughout Modules 1–7; see the [support map](module-9.md#support-for-modules-1-7). Each detailed chapter should cite the relevant guidance. Advanced validation chapters consolidate checks introduced locally in earlier chapters; their later position does not postpone basic verification. All milestones and experimental procedures remain planned until actually carried out.

When authoring reveals a missing prerequisite, update this schedule before completing the dependent chapter. Check that every inventory ID occurs exactly once, every prerequisite resolves to an existing earlier entry, and the dependency graph has no cycles. The current schedule passes these checks for all 201 existing outlines.

## Chapter completion gate

Before advancing to the next authoring position, review the chapter against the [learning approach](learning-approach.md): beginner-friendly definitions, explained formulas and diagrams, primary sources and version assumptions, named experiments with purpose and exit criteria, and explicit reference behavior and verification. Address all six dimensions and eight engineering principles with chapter-specific reasoning. Provide experimental procedures without implementation code. Distinguish predictions and proposed measurements from observed results.
