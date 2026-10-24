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
