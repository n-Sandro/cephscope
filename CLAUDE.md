# Cephscope

Metrics collector for Ceph clusters (inspired by NetApp Harvest).
Language: Go. MVP focus: 1 cluster, core metrics.

See `ARCHITECTURE.md` for architecture and `docs/metrics.md` for metric mapping.
Detailed planning: `docs/planning.md`
Decisions are recorded as ADRs in `docs/adr/`.

## Data sources
- Prometheus mgr module (`ceph mgr module enable prometheus`), port 9283
- ceph-exporter daemon (per host, required in newer releases for complete perf counters)
- Ceph Dashboard REST API (JSON, for inventory/metadata)
- CLI with `--format json` as fallback

## Differentiation vs existing Ceph Prometheus exporter
Raw data already exists – value comes from aggregation, multi-cluster support,
meaningful derived metrics, ready dashboards, and a Harvest-like
template system for metric mappings. Not just duplicating raw data export.

## Conventions
- Go module structure, static binaries as build target
- Document new architecture decisions as ADRs in `docs/adr/`, not only in chat
- Maintain metric mappings centrally in `docs/metrics.md` (Harvest-like template system)
## Sync Routine: Claude.ai Project ↔ Repo
- New decision made? → add a new ADR in docs/adr/ (sequential numbering, format like 0001-name-und-sprache.md)
- Overall planning status has changed significantly? → have docs/planning.md updated in the Project chat and bring the new version into the repo
- Need a new document from the Project knowledge base for implementation (diagram, spec, research result)? → download it manually, put it under docs/, and link it from ARCHITECTURE.md or docs/metrics.md
- Before starting a new coding session, briefly check: are there unprocessed decisions from the last Project chat that aren't yet reflected in CLAUDE.md, ARCHITECTURE.md, or docs/adr/?