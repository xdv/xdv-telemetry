# Unified Metric Schema

## Scope

`src/telemetry_schema.ds` implements the unified metric/fault schema for XDV-070.

## Metric Record

`metric_record_token` validates and encodes:

- metric id
- domain
- source id
- process id
- resource id
- value
- unit
- logical timestamp
- severity
- signature
- exposure mode

## Domain Safety

`XdvTelemetryContracts::K::validate_exposure_mode` enforces:

- K domain: structured or raw exposure modes accepted.
- Q/Phi domains: structured mode only.

This prevents raw Q/Phi state export.

## Ordering and Chain

- `metric_order_key` yields deterministic ordering key using logical timestamp and identity fields.
- `metric_chain_hash` supports deterministic append-only hash chaining.

## Fault Event

`fault_event_token` encodes deterministic fault telemetry metadata with domain and severity validation.
