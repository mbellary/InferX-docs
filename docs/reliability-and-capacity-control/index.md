# Reliability and capacity control

> **Central question:** How does service continue through overload, failures, and changing demand?

This category examines reliability and capacity control through the lens of LLM inference and serving engines.

## Scope

Timeouts, retries, draining, migration, failure domains, autoscaling, headroom.

## Learning objectives

- Follow a request through timeouts, retries, and worker failure.
- Explain safe draining and migration of active serving work.
- Connect autoscaling and headroom to service objectives.

## Chapters

Chapter outlines are grouped by module. Full content will be developed one chapter at a time.

### Module 2

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M2-C16 | [Completion, cancellation, and allocation failure](m2-c16-completion-cancellation-and-allocation-failure.md) | Terminal request states, idempotent cleanup, cancellation during growth or sharing, partial-allocation rollback, draining in-flight work, worker loss and volatile-state recovery |

Follow the complete [Module 2 reading order](../module-2.md) to move between categories.

### Module 5

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M5-C20 | [Cancellation, deadlines, and worker failure](m5-c20-cancellation-deadlines-and-worker-failure.md) | Queued versus in-flight cancellation, deadline expiry, idempotent terminal transitions, deferred block release, worker error propagation, safe retry boundaries, draining, shutdown, capacity recovery |

Follow the complete [Module 5 reading order](../module-5.md) to move between categories.

### Module 6

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M6-C25 | [Handling unsupported cases and optimization failures](m6-c25-handling-unsupported-cases-and-optimization-failures.md) | Capability checks, invalidated cache identities, missing adapters, grammar errors, allocation failures, safe fallback versus explicit rejection, cancellation, cleanup, bounded recovery costs |

Follow the complete [Module 6 reading order](../module-6.md) to move between categories.

### Module 7

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M7-C23 | [Collective failures, timeouts, and recovery boundaries](m7-c23-collective-failures-timeouts-and-recovery-boundaries.md) | Rank mismatch, divergent collective ordering, hung or failed workers, stragglers, asynchronous errors, timeout scopes, coordinated abort, retry boundaries, lost volatile state, safe cleanup |

Follow the complete [Module 7 reading order](../module-7.md) to move between categories.

### Module 9

| Chapter ID | Chapter name | Target concepts |
| --- | --- | --- |
| M9-C21 | [Testing cancellation, deadlines, and terminal states](m9-c21-testing-cancellation-deadlines-and-terminal-states.md) | Queued and in-flight cancellation, deadline expiry, disconnects, idempotent cleanup, no post-terminal delivery, bounded cancellation latency, worker errors, reclamation after completion |
| M9-C26 | [Load-testing overload, backpressure, and failure recovery](m9-c26-load-testing-overload-backpressure-and-failure-recovery.md) | Offered-load sweeps, bounded queues, rejection and retry effects, slow consumers, memory exhaustion, worker loss, draining, recovery time, resource leaks, latency and goodput during failures |

Follow the complete [Module 9 reading order](../module-9.md) to move between categories.
