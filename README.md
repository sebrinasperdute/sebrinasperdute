Staff engineer building distributed ingestion systems.

## Trevor Emard

I design and operate data ingestion pipelines that move tens of millions of events per day across Kafka, Postgres, and S3. I own the full lifecycle: schema evolution, partition strategy, retry semantics, and the on-call runbooks that keep them honest. I trade strict consistency for availability at the edge, and I keep queues bounded because backpressure is a feature, not a bug.

### 🛠 Tech & Infrastructure

**Core** — `TypeScript`, `Node.js`, `Kafka`, `Postgres`

**Data** — `Redis`, `S3`, `Parquet`, `Debezium`

**Infra** — `Docker`, `Kubernetes`, `Terraform`, `GitHub Actions`

**Tooling** — `Prometheus`, `Grafana`, `OpenTelemetry`, `pgTAP`

### ⚙️ Engineering Areas

- Designing idempotent consumers with exactly-once semantics using Kafka transactions and deduplication keys.
- Migrating legacy ETL jobs to streaming pipelines with schema registry and versioned Avro contracts.
- Tuning Postgres indexes and partitioning for time-series event data under high write volume.
- Building self-healing worker pools with exponential backoff and circuit breakers for downstream APIs.

### 🔭 Current Focus

- Reducing tail latency in the ingestion path by sharding hot partitions and moving to tiered storage.
- Implementing schema validation at the edge to catch malformed events before they hit the queue.
- Replacing manual retry queues with a dead-letter topic and replay tooling that preserves ordering.
- Evaluating a shift from Kafka to Redpanda for lower operational overhead and better throughput at the same partition count.

### 📌 Engineering Notes

- Tests should assert behavior, not implementation; property-based tests catch more edge cases than hand-written examples.
- Migrations are safer when they are additive and reversible; backfill jobs must be idempotent and resumable.
- Retries need jitter and exponential backoff; infinite retries without a dead-letter topic are a silent data-loss bug.
- Every deployment should be traceable to a commit and every alert should link to a runbook; if it isn't documented, it doesn't exist.

### 🧭 How I Work

- Prefer boring, proven technologies over novel ones unless the new tool solves a specific pain we already feel.
- Write code that fails loudly in development and degrades gracefully in production.
- Review code for data flow and failure modes, not just style.

*Reliability is the feature users notice when it's missing.*