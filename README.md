# XDV Telemetry

Version: 0.1.0
Status: active
Language: Dust Programming Language (DPL)

## Specification Alignment

Primary specification: XDV-070 in `xdv-spec`.

Implemented focus for this milestone:

1. Unified metric schema across K/Q/Phi domains.
2. Deterministic local and distributed aggregation paths.
3. Capability-scoped telemetry access controls.

## Purpose

Unified deterministic telemetry schema and aggregation pipeline.

## Modules

- `src/telemetry_contracts.ds`
  Domain/category/severity/tenant/capability validators and exposure constraints.

- `src/telemetry_schema.ds`
  Metric and fault record tokenization, deterministic ordering key, and chain hash.

- `src/telemetry_aggregation.ds`
  Deterministic local flush/sum/avg and distributed merge/aggregation functions.

- `src/telemetry_access.ds`
  Capability token model and tenant/domain capability-gated access authorization.

- `src/telemetry_tests.ds`
  Behavioral tests for schema, aggregation determinism, and access controls.

- `src/main.ds`
  Startup validation, smoke flows, and self-test entrypoints.

## Design Notes

- Q/Phi telemetry rejects raw-state exposure mode.
- Ordering uses logical timestamp + node/source/metric deterministic keys.
- Distributed merge uses stable key ordering with deterministic node tie-break.
- Cross-tenant reads require explicit grant and valid capability scope.

## Build

```bash
dust check xdv-telemetry/src
```

## Test

```bash
dust check xdv-telemetry/src/telemetry_tests.ds
dust check xdv-telemetry/tests/telemetry_e2e.ds
```

## Integration Contracts

- Telemetry remains observational and does not mutate runtime orchestration state.
- No raw Q/Phi state leaves telemetry interface.
- Aggregation output is replay-equivalent for identical inputs.
- Access checks enforce tenant/domain capability scope deterministically.
