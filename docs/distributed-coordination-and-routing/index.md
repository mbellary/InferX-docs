# Distributed coordination and routing

> **Central question:** How do independent workers cooperate using incomplete information?

This category examines distributed coordination and routing through the lens of LLM inference and serving engines.

## Scope

Discovery, membership, placement, load balancing, reservations, consistency, stale telemetry.

## Learning objectives

- Explain routing and placement decisions using incomplete worker state.
- Reason about reservations, membership changes, and consistency.
- Recognize the effects of stale telemetry on load balancing.

## Chapters

Chapter outlines are grouped by module. Full content will be developed one chapter at a time.

### Module 7

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M7-C15 | [Routing requests with load and cache locality](m7-c15-routing-requests-with-load-and-cache-locality.md) | Discovery and membership, replica selection, outstanding work versus request counts, prefix affinity, stale telemetry, reservations, locality versus fairness, overload and retry routing |
| M7-C22 | [Coordinating requests and execution across workers](m7-c22-coordinating-requests-and-execution-across-workers.md) | Request and iteration IDs, agreed batch membership, control-plane versus data-plane messages, metadata consistency, stale events, epochs, completion aggregation, cancellation propagation |
| M7-C26 | [Balancing disaggregated stages and transfer capacity](m7-c26-balancing-disaggregated-stages-and-transfer-capacity.md) | Prefill and decode pool sizing, phase-aware routing, KV availability, receiving capacity, bandwidth bottlenecks, reservations, stale telemetry, backpressure, admission and tail-latency objectives |

Follow the complete [Module 7 reading order](../module-7.md) to move between categories.
