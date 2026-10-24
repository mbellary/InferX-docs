# Measurement, experimentation, and economics

> **Central question:** How do we establish correctness, explain performance, and assess cost?

This category examines measurement, experimentation, and economics through the lens of LLM inference and serving engines.

## Scope

Profiling, benchmarks, p50/p99, goodput, workload design, statistical uncertainty, cost and energy.

## Learning objectives

- Design workload-specific correctness and performance experiments.
- Interpret latency distributions, throughput, and goodput together.
- Assess uncertainty, cost, and energy before drawing conclusions.

## Chapters

Module 1 chapter outlines, listed in learning order. Full content will be developed one chapter at a time.

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M1-C08 | [Operation counts and actual execution cost](m1-c08-operation-counts-and-actual-execution-cost.md) | Computational complexity, matrix multiplication costs, memory capacity, data movement, bandwidth, throughput, latency, allocation overhead, bottleneck predictions |
| M1-C20 | [Measuring and explaining generation latency](m1-c20-measuring-and-explaining-generation-latency.md) | Input-length and output-length sweeps, prefill time, time to first token, per-token decode latency, total latency, warmup, repeated measurements, correctness checks, predicted versus observed bottlenecks |

Follow the complete [Module 1 reading order](../module-1.md) to move between categories.
