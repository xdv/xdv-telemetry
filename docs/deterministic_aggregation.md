# Deterministic Aggregation

## Scope

`src/telemetry_aggregation.ds` implements local/distributed deterministic aggregation.

## Local Aggregation

- `local_flush_decision` triggers flush based on logical interval only.
- `local_aggregate_sum3` and `local_aggregate_avg3` provide deterministic rollups.
- `local_buffer_epoch` partitions metric buffer windows by logical timestamp/interval.

## Distributed Aggregation

- `distributed_merge_key` uses deterministic metric ordering key.
- `distributed_choose_first` picks deterministic winner by key then node-id tie-break.
- `distributed_merge_token` emits stable merged output token.
- `distributed_aggregate_sum_two` and `distributed_aggregate_avg_two` provide deterministic rollups.

## Determinism Guarantee

For identical inputs, merge and aggregate outputs are stable and replay-equivalent.
