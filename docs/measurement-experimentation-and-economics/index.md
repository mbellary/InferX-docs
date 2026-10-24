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

Full content will be developed one chapter at a time.

### Module 1

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M1-C08 | [Operation counts and actual execution cost](m1-c08-operation-counts-and-actual-execution-cost.md) | Computational complexity, matrix multiplication costs, memory capacity, data movement, bandwidth, throughput, latency, allocation overhead, bottleneck predictions |
| M1-C20 | [Measuring and explaining generation latency](m1-c20-measuring-and-explaining-generation-latency.md) | Input-length and output-length sweeps, prefill time, time to first token, per-token decode latency, total latency, warmup, repeated measurements, correctness checks, predicted versus observed bottlenecks |

Follow the complete [Module 1 reading order](../module-1.md) to move between categories.

### Module 2

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M2-C21 | [Benchmarking KV management end to end](m2-c21-benchmarking-kv-management-end-to-end.md) | Contiguous versus paged baselines, context and concurrency sweeps, reuse skew, cancellation churn, allocation and reclamation latency, tail distributions, fragmentation, useful throughput, full-request latency, reproducible profiling |

Follow the complete [Module 2 reading order](../module-2.md) to move between categories.

### Module 3

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M3-C15 | [Counting FLOPs and bytes at a defined boundary](m3-c15-counting-flops-and-bytes-at-a-defined-boundary.md) | GEMV and GEMM dimensions, multiply-add counting, theoretical versus observed traffic, memory-level boundaries, cache reuse, reads and writes, units, achieved throughput and bandwidth |
| M3-C16 | [Using the roofline model to predict bottlenecks](m3-c16-using-the-roofline-model-to-predict-bottlenecks.md) | Arithmetic intensity, compute and bandwidth roofs, ridge point, idealized kernel-time estimates, effective versus peak rates, hierarchical rooflines, launch and dependency limits |
| M3-C19 | [Designing trustworthy asynchronous GPU benchmarks](m3-c19-designing-trustworthy-asynchronous-gpu-benchmarks.md) | Device-event versus host-wall timing, timing boundaries, completion waits, launch overhead, warmup, repeated trials, cache state, clocks and thermals, interference, distributions, profiler overhead |
| M3-C20 | [Benchmarking memory copies across sizes and paths](m3-c20-benchmarking-memory-copies-across-sizes-and-paths.md) | Host-to-device, device-to-host and device-to-device copies, pageable versus pinned buffers, size sweeps, setup versus transfer costs, payload versus read-plus-write bandwidth, overlap and contention |
| M3-C21 | [Benchmarking matrix-vector multiplication across shapes](m3-c21-benchmarking-matrix-vector-multiplication-across-shapes.md) | GEMV shape sweeps, weight and vector traffic, output writes, cache-resident versus device-memory working sets, bandwidth utilization, small-workload overhead, correctness checks |
| M3-C22 | [Benchmarking matrix-matrix multiplication across shapes](m3-c22-benchmarking-matrix-matrix-multiplication-across-shapes.md) | GEMM shape and batch sweeps, operand reuse, tensor-core eligibility, tile utilization, alignment and edge effects, precision controls, achieved compute throughput, GEMV comparison |
| M3-C23 | [Explaining GPU profiles and end-to-end serving effects](m3-c23-explaining-gpu-profiles-and-end-to-end-serving-effects.md) | Nsight Systems timelines, Nsight Compute counters, kernel versus request critical paths, memory traffic, occupancy and stalls, roofline reconciliation, controlled comparisons, tail latency, reproducible evidence |

Follow the complete [Module 3 reading order](../module-3.md) to move between categories.

### Module 4

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M4-C21 | [Tuning kernels with controlled experiments](m4-c21-tuning-kernels-with-controlled-experiments.md) | Tile sizes, warps and stages, register and shared-memory limits, profiling hypotheses, tuning cost, separate tuning and evaluation workloads, specialization regressions, cold-start cost |
| M4-C22 | [Benchmarking realistic shapes and execution modes](m4-c22-benchmarking-realistic-shapes-and-execution-modes.md) | Hidden and vocabulary dimensions, batch sizes, dtypes and layouts, fused versus unfused baselines, eager versus graph replay, launch counts, memory traffic, warmup, timing boundaries, latency distributions |
| M4-C24 | [Verifying end-to-end generator improvements](m4-c24-verifying-end-to-end-generator-improvements.md) | Critical-path attribution, Amdahl-style speedup limits, prefill and decode separation, time to first token, inter-token and total latency, useful throughput, correctness gates, amortization, tail regressions |

Follow the complete [Module 4 reading order](../module-4.md) to move between categories.

### Module 5

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M5-C07 | [Describing mixed serving workloads and arrival traces](m5-c07-describing-mixed-serving-workloads-and-arrival-traces.md) | Prompt and output lengths, declared output caps versus realized lengths, arrival timestamps, bursts, skew and correlations, reuse, seeds, offered versus admitted load, open-loop versus closed-loop traffic |
| M5-C24 | [Comparing scheduling policies on the same arrival trace](m5-c24-comparing-scheduling-policies-on-the-same-arrival-trace.md) | Static, continuous and chunked-prefill configurations, fixed arrivals and request contents, identical resource caps, controlled output demand, causal information boundaries, event tracing, warmup and drain, rejection and unfinished-request accounting |
| M5-C25 | [Measuring sustainable capacity, fairness, and tail behavior](m5-c25-measuring-sustainable-capacity-fairness-and-tail-behavior.md) | Time to first token, inter-token and total latency distributions, SLO definitions, goodput, completed tokens per second, queue depth, KV occupancy, CPU and GPU profiling, offered-load sweeps, coordinated omission, uncertainty, per-class fairness |

Follow the complete [Module 5 reading order](../module-5.md) to move between categories.

### Module 6

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M6-C17 | [When speculative decoding helps or hurts](m6-c17-when-speculative-decoding-helps-or-hurts.md) | Draft cost, target verification cost, acceptance rate and accepted length, useful output tokens, proposal length, batch and context effects, shared-resource contention, extra memory, break-even workloads |
| M6-C26 | [Designing the optimization workload and comparison matrix](m6-c26-designing-the-optimization-workload-and-comparison-matrix.md) | Prefix reuse and skew, context and output lengths, arrivals and concurrency, precision settings, draft agreement, grammar complexity, adapter mix, fixed resource budgets, cold and warm runs, ablations |
| M6-C28 | [Establishing end-to-end benefit and regression boundaries](m6-c28-establishing-end-to-end-benefit-and-regression-boundaries.md) | Correctness and quality gates, first-token and inter-token latency, tail distributions, goodput, capacity, CPU and GPU overhead, actual memory, compilation and loading amortization, fairness, cost, uncertainty, helps-versus-hurts results |

Follow the complete [Module 6 reading order](../module-6.md) to move between categories.
