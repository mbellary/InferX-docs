# Parallelism and decomposition

> **Central question:** How is computation divided across devices and stages?

This category examines parallelism and decomposition through the lens of LLM inference and serving engines.

## Scope

DP, TP, PP, EP, CP, encoder/prefill/decode separation.

## Learning objectives

- Distinguish data, tensor, pipeline, expert, and context parallelism.
- Identify the state and communication boundaries created by decomposition.
- Evaluate encoder, prefill, and decode separation for a workload.

## Chapters

Chapter outlines are grouped by module. Full content will be developed one chapter at a time.

### Module 7

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M7-C01 | [Why distribute inference across GPUs?](m7-c01-why-distribute-inference-across-gpus.md) | Model fit, aggregate capacity, single-request latency, replicas versus sharding, strong versus weak scaling, communication overhead, two-GPU versus single-GPU goals |
| M7-C10 | [Tensor parallelism for linear layers](m7-c10-tensor-parallelism-for-linear-layers.md) | Row and column partitioning, weight and activation shards, partial outputs, collective placement, replication, layer boundaries, frequent communication, shape compatibility |
| M7-C11 | [Tensor-parallel attention and KV ownership](m7-c11-tensor-parallel-attention-and-kv-ownership.md) | Query and KV head partitioning, MHA and GQA constraints, replicated versus sharded KV state, head-count divisibility, output projection, position and mask consistency, rank-local cache budgets |
| M7-C12 | [Pipeline parallelism for inference](m7-c12-pipeline-parallelism-for-inference.md) | Layer partitions, stage interfaces, activation transfers, per-stage KV state, forward-only execution, microbatches, request-token identity, autoregressive feedback dependencies |
| M7-C14 | [Data parallelism across serving replicas](m7-c14-data-parallelism-across-serving-replicas.md) | Request partitioning, replicated model weights, independent worker queues, replica-local KV caches, capacity scaling, single-request limits, shared resource contention |
| M7-C17 | [Expert parallelism and dispatch-combine execution](m7-c17-expert-parallelism-and-dispatch-combine-execution.md) | Expert placement, token routing, AllToAll dispatch, grouped expert computation, weighted combine, token permutation, expert replication choices, communication and storage costs |
| M7-C19 | [Context parallelism and distributed attention state](m7-c19-context-parallelism-and-distributed-attention-state.md) | Sequence partitions, query versus KV partitioning, attention communication, ring exchange or partial-output reductions, online-softmax merging, causal masks, positions, prefill versus decode differences |
| M7-C20 | [Combining parallelism strategies and placement](m7-c20-combining-parallelism-strategies-and-placement.md) | TP, PP, DP, EP and CP groups, rank mapping, nested partitioning, topology-aware placement, compatible dimensions, replicated versus sharded state, communication domains |
| M7-C24 | [Prefill-decode disaggregation and its tradeoffs](m7-c24-prefill-decode-disaggregation-and-its-tradeoffs.md) | Separate phase workers, compute and memory specialization, interference reduction, extra queues, KV transfer volume, resource split, latency objectives, workload-dependent benefit |

Follow the complete [Module 7 reading order](../module-7.md) to move between categories.
