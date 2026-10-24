# Model computation and semantics

> **Central question:** What computation produces a correct output?

This category examines model computation and semantics through the lens of LLM inference and serving engines.

## Scope

Transformers, attention, MoE, multimodal encoders, positional encoding, sampling.

## Learning objectives

- Follow a request from tokens through transformer layers to logits and sampled tokens.
- Explain how attention, positional information, and expert selection affect model behavior.
- Identify model-specific requirements a serving engine must preserve.

## Chapters

Full content will be developed one chapter at a time.

### Module 1

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M1-C01 | [From a prompt to the next token](m1-c01-from-a-prompt-to-the-next-token.md) | LLMs, inference, decoder-only models, model weights, token-by-token generation, stages of a single request |
| M1-C03 | [Numbers, vectors, matrices, and tensors](m1-c03-numbers-vectors-matrices-and-tensors.md) | Scalars, vectors, matrices, tensors, axes, dimensions, shapes, indexing, basic Rust representations |
| M1-C04 | [Dot products and matrix multiplication](m1-c04-dot-products-and-matrix-multiplication.md) | Weighted sums, dot products, matrix multiplication, dimension compatibility, batched multiplication, model projections |
| M1-C09 | [Token embeddings and learned projections](m1-c09-token-embeddings-and-learned-projections.md) | Embedding lookup, embedding dimensions, learned weights, linear transformations, intermediate activations, tensor shape tracing |
| M1-C10 | [Attention, one dimension at a time](m1-c10-attention-one-dimension-at-a-time.md) | Queries, keys, values, batch and sequence axes, heads, head dimensions, QKᵀ, scaling by √dₖ, softmax axes, weighted value aggregation |
| M1-C11 | [Causal masking and positional information](m1-c11-causal-masking-and-positional-information.md) | Autoregressive dependencies, causal masks, position indices, positional encoding, RoPE, position handling during generation |
| M1-C12 | [Multi-head attention and its variants](m1-c12-multi-head-attention-and-its-variants.md) | Splitting and combining heads, attention output projection, multi-head attention, multi-query attention, grouped-query attention, query-head versus KV-head counts |
| M1-C13 | [Building a complete Transformer block](m1-c13-building-a-complete-transformer-block.md) | Residual connections, normalization, LayerNorm and RMSNorm, MLPs, activation functions, gated MLPs, operation ordering |
| M1-C14 | [Assembling a small decoder-only Transformer](m1-c14-assembling-a-small-decoder-only-transformer.md) | Model configuration, stacked blocks, final normalization, vocabulary projection, logits, fixed weights, loading weights, inference versus training |
| M1-C15 | [Turning logits into the next token](m1-c15-turning-logits-into-the-next-token.md) | Greedy decoding, temperature, top-k and top-p filtering, probability renormalization, random sampling, seeds, tie handling |

Follow the complete [Module 1 reading order](../module-1.md) to move between categories.

### Module 2

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M2-C02 | [Attention head sharing: MHA, GQA, and MQA](m2-c02-attention-head-sharing-mha-gqa-and-mqa.md) | Query heads versus KV heads, multi-head attention, grouped-query attention, multi-query attention, cache shapes, architecture-dependent memory requirements |
| M2-C17 | [Sliding-window attention and bounded cache state](m2-c17-sliding-window-attention-and-bounded-cache-state.md) | Model-defined attention windows, retained token ranges, logical versus physical positions, ring-buffer mapping, per-layer windows, hybrid attention, limits of dropping old state |
| M2-C18 | [Architecture-specific state: Multi-head Latent Attention](m2-c18-architecture-specific-state-multi-head-latent-attention.md) | MLA compressed latent state, positional components, architecture-specific cache representations, storage versus reconstruction work, limits of the conventional KV formula |

Follow the complete [Module 2 reading order](../module-2.md) to move between categories.

### Module 6

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M6-C14 | [Draft proposals and parallel target verification](m6-c14-draft-proposals-and-parallel-target-verification.md) | Draft and target models, proposal length, autoregressive draft generation, causal target scoring, conditional distributions, accepted prefixes, bonus or correction tokens, stopping rules |
| M6-C21 | [LoRA foundations and adapter-specific computation](m6-c21-lora-foundations-and-adapter-specific-computation.md) | Low-rank updates, base weights, adapter matrices, rank and scaling, target layers, merged versus unmerged computation, adapter identity, reference outputs, heterogeneous adapter requests |

Follow the complete [Module 6 reading order](../module-6.md) to move between categories.
