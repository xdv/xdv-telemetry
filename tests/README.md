# XDV Telemetry Tests

Deterministic tests and fixtures for `xdv-telemetry`.

## Covered Behaviors

- Unified metric schema validation and Q/Phi exposure protection.
- Deterministic local/distributed aggregation behavior.
- Capability-scoped tenant/domain access control checks.

## Entrypoints

- `xdv-telemetry/src/telemetry_tests.ds` : core behavior checks.
- `xdv-telemetry/tests/telemetry_e2e.ds` : aggregate test entrypoint.

## Run

```bash
dust check xdv-telemetry/src
dust check xdv-telemetry/tests/telemetry_e2e.ds
```
