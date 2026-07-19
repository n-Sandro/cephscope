# Metric Mapping

Harvest-like template system: raw counters from Ceph data sources are mapped here
to named, documented metrics.

## Sources
- Prometheus mgr module (port 9283) – raw counters in Prometheus text format
- ceph-exporter daemon (per host) – complete perf counters
- Ceph Dashboard REST API – inventory/metadata (JSON)
- CLI `--format json` – fallback

## Mapping table (placeholder – to be populated with MVP)

| Cephscope metric | Source | Raw counter/field | Description |
|---|---|---|---|
| _(still open)_ | | | |

## Conventions for new entries
- Name follows schema `<area>_<metric>_<unit>` (e.g. `pool_used_bytes`)
- Always specify the source clearly (mgr module, ceph-exporter, dashboard API, CLI)
- Mark derived/aggregated metrics and briefly explain the calculation
