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

### Module 6

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M6-C18 | [Grammar-constrained decoding from tokens to parser state](m6-c18-grammar-constrained-decoding-from-tokens-to-parser-state.md) | Regular versus context-free languages, finite-state machines and parser stacks, token-to-byte transitions, grammar state, valid continuations, accepting states, tokenizer compatibility |
| M6-C19 | [Grammar compilation and vocabulary-mask execution](m6-c19-grammar-compilation-and-vocabulary-mask-execution.md) | Grammar and schema compilation, mask generation, token filtering, mask caching, state advancement, CPU-GPU coordination, preprocessing versus per-token overhead, constraint and sampling order |
| M6-C20 | [Structured-output validity, termination, and failure](m6-c20-structured-output-validity-termination-and-failure.md) | Syntactic validity versus semantic correctness, incomplete outputs, empty allowed-token sets, EOS legality, unsupported schema features, compilation failures, length limits, cancellation, explicit failure contracts |

Follow the complete [Module 6 reading order](../module-6.md) to move between categories.

### Module 9

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M9-C04 | [Measuring inter-token latency in a streamed protocol](m9-c04-measuring-inter-token-latency-in-a-streamed-protocol.md) | Token generation versus delivery, token timestamps, chunk coalescing, buffering, network and client delays, per-request gaps, first-token exclusion, limits of inferring tokens from chunks |
| M9-C19 | [Validating tokenization, stopping, and final output](m9-c19-validating-tokenization-stopping-and-final-output.md) | Tokenizer and template identity, control tokens, EOS, length caps, multi-token stop sequences, boundary-spanning text, incremental detokenization, terminal reasons, no-token and truncated outputs |

Follow the complete [Module 9 reading order](../module-9.md) to move between categories.
