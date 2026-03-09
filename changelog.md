# Changelog

## 0.1.1 - XDV-070 Telemetry Core Implementation

- Implemented unified telemetry contracts in `src/telemetry_contracts.ds`.
- Implemented metric/fault schema tokenization and deterministic ordering in `src/telemetry_schema.ds`.
- Implemented deterministic local/distributed aggregation in `src/telemetry_aggregation.ds`.
- Implemented capability-scoped telemetry access checks in `src/telemetry_access.ds`.
- Added XDV-070 behavior tests in `src/telemetry_tests.ds`.
- Added aggregate test entrypoint `tests/telemetry_e2e.ds`.
- Updated README/docs/test docs for delivered functionality.

## 0.1.0 - Initial Skeleton

- Created project scaffold for XDV Telemetry.
- Added State.toml, README.md, and docs/test placeholders.
- Imported LICENSE from xdv-os/LICENSE.
