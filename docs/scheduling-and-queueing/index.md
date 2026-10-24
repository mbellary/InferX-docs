# Scheduling and queueing

> **Central question:** Which work runs next, with what budget?

This category examines scheduling and queueing through the lens of LLM inference and serving engines.

## Scope

Continuous batching, chunked prefill, priorities, fairness, admission, backpressure, queueing theory.

## Learning objectives

- Reason about prefill and decode scheduling under mixed workloads.
- Compare throughput, latency, and fairness objectives.
- Use admission and backpressure to control queued work.

## Chapters

Chapter outlines are grouped by module. Full content will be developed one chapter at a time.

### Module 2

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M2-C15 | [Admission and growth under a finite KV budget](m2-c15-admission-and-growth-under-a-finite-kv-budget.md) | Free-block budgets, growth reservations, headroom, admit-wait-reject decisions, backpressure, mixed request lengths, fairness, capacity versus latency |

Follow the complete [Module 2 reading order](../module-2.md) to move between categories.

### Module 3

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M3-C17 | [Batching, weight reuse, and shifting bottlenecks](m3-c17-batching-weight-reuse-and-shifting-bottlenecks.md) | Batch size and matrix shapes, weight reuse, arithmetic intensity changes, prefill versus decode tendencies, working-set limits, saturation, batching delay versus service time |

Follow the complete [Module 3 reading order](../module-3.md) to move between categories.
