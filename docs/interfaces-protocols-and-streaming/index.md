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
