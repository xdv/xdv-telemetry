# Capability-Scoped Access Controls

## Scope

`src/telemetry_access.ds` enforces tenant/domain/capability-scoped access for telemetry reads.

## Capability Token

`capability_token` encodes:

- token id
- tenant scope
- domain scope
- capability scope
- issued logical timestamp
- expiry logical timestamp
- signature

## Authorization

`authorize_metric_read` enforces deterministic checks:

1. token active in logical time window
2. request tenant validity
3. same-tenant by default
4. cross-tenant read only with explicit grant
5. domain and capability scope alignment

`authorize_distributed_aggregation` applies same logic for cluster aggregation.

## Auditability

`access_decision_token` emits deterministic metadata for allow/deny decisions.
