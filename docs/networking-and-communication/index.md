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
