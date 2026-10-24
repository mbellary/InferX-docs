# Networking and communication

> **Central question:** How does data move between execution domains?

This category examines networking and communication through the lens of LLM inference and serving engines.

## Scope

Collectives, dispatch/combine, RPC transport, RDMA, transfer completion, congestion, overlap.

## Learning objectives

- Trace communication through collective and point-to-point operations.
- Distinguish transfer submission from completion and safe buffer reuse.
- Investigate congestion and opportunities for communication overlap.

## Chapters

Chapter outlines are grouped by module. Full content will be developed one chapter at a time.

### Module 3

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M3-C14 | [Moving tensors between devices and hosts](m3-c14-moving-tensors-between-devices-and-hosts.md) | Host-device, device-device, peer-to-peer and staged transfers, network fabrics, RDMA and GPUDirect concepts, transfer completion, shared-link contention, communication scope and limits |

Follow the complete [Module 3 reading order](../module-3.md) to move between categories.

### Module 7

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M7-C04 | [Point-to-point transfers and communication contracts](m7-c04-point-to-point-transfers-and-communication-contracts.md) | Send and receive matching, tensor shapes and dtypes, buffer ownership, asynchronous submission and completion, peer access versus host staging, ordering, backpressure |
| M7-C05 | [Reductions and AllReduce from first principles](m7-c05-reductions-and-allreduce-from-first-principles.md) | Elementwise reductions across ranks, sum and maximum, replicated results, collective participation and ordering, shape compatibility, floating-point reduction order |
| M7-C06 | [AllGather and ReduceScatter as layout transformations](m7-c06-allgather-and-reducescatter-as-layout-transformations.md) | Sharded and replicated tensors, rank-ordered concatenation, reduce-and-partition semantics, buffer sizes, AllReduce decomposition, divisibility and padding, ownership of output shards |
| M7-C07 | [AllToAll and variable-size token exchange](m7-c07-alltoall-and-variable-size-token-exchange.md) | Per-destination partitions, dispatch and combine patterns, send and receive counts, variable-size exchanges, packing and unpacking, permutation metadata, imbalance, backend capability limits |
| M7-C08 | [Modeling communication latency and bandwidth costs](m7-c08-modeling-communication-latency-and-bandwidth-costs.md) | Message size, startup latency, effective bandwidth, alpha-beta models, rank count, algorithm-dependent traffic and steps, rings and trees, small versus large messages, topology and contention |
| M7-C25 | [Transferring KV state with a safe handoff](m7-c25-transferring-kv-state-with-a-safe-handoff.md) | Source and destination identities, cache format and shard compatibility, block mapping, receiver reservations, bulk transfer and metadata, completion versus submission, ownership commit, cancellation and partial failures |

Follow the complete [Module 7 reading order](../module-7.md) to move between categories.
