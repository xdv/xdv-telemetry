# Fault Reporting and Replay

## Scope

Fault telemetry in this milestone is emitted through `fault_event_token` in `src/telemetry_schema.ds`.

## Fault Event Model

Fault records include deterministic metadata:

- fault id
- domain
- severity
- resource id
- description code
- logical timestamp
- signature

## Replay Considerations

- Logical timestamp and order key are used for deterministic replay ordering.
- Chain hash (`metric_chain_hash`) supports append-only integrity checks.
- Aggregation modules preserve deterministic merge semantics for distributed replay.

This keeps telemetry replay-compatible without exposing execution internals.
