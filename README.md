# Artur Smirnov — Senior Go Engineer, Payments & High-Load Systems

Four years building backend systems for payments (six years with Go overall): payout processing, ledger
consistency, and integrations with third-party payment service providers
that fail in every way a distributed system can fail.

## What I work on

- **Exactly-once payouts** over an at-least-once transport: idempotency
  keys on the API boundary, deduplication at the consumer, and unique
  constraints as the last line of defense against double-processing.
- **Saga orchestration without two-phase commit** for multi-step money
  movements (reserve → transfer → settle) — persisted state machines with
  compensating transactions instead of distributed locks.
- **Transactional outbox → Kafka → ClickHouse** for reliable event
  delivery out of the primary database, feeding both downstream services
  and analytics without a dual-write race.
- **Circuit breaker and dead-letter queues for unstable PSPs** — the
  external providers a payments system depends on are the least reliable
  part of it; isolating their failures brought incident MTTR down from
  ~3h to ~45min.

## Pinned

| Repo | What it shows |
|---|---|
| [`idempotency`](https://github.com/smirnov-artur/idempotency) | Idempotency-Key HTTP middleware for payment APIs — in-memory and Postgres stores, concurrent-request handling, table-driven tests with `-race` |
| [`outbox`](https://github.com/smirnov-artur/outbox) | Transactional outbox → Kafka design: `FOR UPDATE SKIP LOCKED` poller, at-least-once delivery, consumer-side dedup |
| [`saga-orchestrator`](https://github.com/smirnov-artur/saga-orchestrator) | Saga orchestration for money movements without 2PC: compensating transactions, idempotent steps, persisted state |

## Stack

Go, PostgreSQL, Kafka, ClickHouse, gRPC/REST, Docker, Kubernetes.

## Contact

- Email: paladei702@gmail.com
- Telegram: @smirnovarturr
- Book a call: https://cal.com/paladei-rxmf8b/30min

Open to remote Go roles.
