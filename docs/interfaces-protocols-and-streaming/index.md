# Interfaces, protocols, and streaming

> **Central question:** How are user requests translated into computation and results?

This category examines interfaces, protocols, and streaming through the lens of LLM inference and serving engines.

## Scope

API contracts, templates, tokenization, control-token identity, incremental parsing, structured outputs.

## Learning objectives

- Trace an API request through templating and tokenization.
- Preserve control-token identity and output protocol requirements.
- Reason about partial streaming results and structured output validation.

## Chapters

Module 1 chapter outlines, listed in learning order. Full content will be developed one chapter at a time.

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M1-C02 | [Representing text as tokens](m1-c02-representing-text-as-tokens.md) | Vocabulary, token IDs, tokenization, encoding and decoding, special tokens, chat templates, preserving token identity |
| M1-C16 | [Building the single-request generation loop](m1-c16-building-the-single-request-generation-loop.md) | Prompt preparation, repeated forward passes, appending tokens, end-of-sequence tokens, output limits, stop sequences, incremental detokenization, partial text handling |

Follow the complete [Module 1 reading order](../module-1.md) to move between categories.

### Module 5

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M5-C21 | [Streaming results without unbounded buffering](m5-c21-streaming-results-without-unbounded-buffering.md) | Per-request token ordering, result routing, bounded output queues, slow consumers, output backpressure, disconnect handling, completion delivery, generation versus client-visible timing |

Follow the complete [Module 5 reading order](../module-5.md) to move between categories.
