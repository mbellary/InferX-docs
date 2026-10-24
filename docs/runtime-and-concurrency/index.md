# Runtime and concurrency

> **Central question:** How do concurrent operations progress without violating dependencies?

This category examines runtime and concurrency through the lens of LLM inference and serving engines.

## Scope

Processes, threads, async execution, synchronization, ownership, buffer lifetimes, CPU/device overlap.

## Learning objectives

- Trace dependencies across host and device execution.
- Explain synchronization and buffer ownership in concurrent request processing.
- Identify opportunities for overlap without violating lifetimes.

## Chapters

Module 1 chapter outlines, listed in learning order. Full content will be developed one chapter at a time.

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M1-C18 | [Understanding prefill and decode](m1-c18-understanding-prefill-and-decode.md) | Prompt processing, first-token selection, subsequent decode steps, phase-specific tensor shapes, cache reads and writes, context-length and batch-size effects |

Follow the complete [Module 1 reading order](../module-1.md) to move between categories.
