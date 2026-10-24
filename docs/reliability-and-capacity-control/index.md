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
