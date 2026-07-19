# Cephscope

Cephscope is a Go-based metrics collector for Ceph clusters, focusing on aggregation, derived useful metrics, and ready-made dashboards.

## Status

- Early planning and setup phase
- MVP not yet started

## Goals

- Collect Ceph metrics from Prometheus, Ceph Dashboard API, and CLI fallbacks
- Cross-cluster aggregation and reporting
- Harvest-like template system for metric mappings
- Ready dashboards and meaningful metrics instead of raw data only

## Structure

- `ARCHITECTURE.md` – architecture overview
- `docs/metrics.md` – metric mapping and data sources
- `docs/adr/` – architecture decisions (ADRs)
- `docs/planning.md` – planning and roadmap
- `CLAUDE.md` – context for Claude-assisted code generation

## Developer notes

- Write the project in Go
- Target static binaries
- Document new architecture decisions as ADRs

## GitHub

- `https://github.com/n-Sandro/cephscope`
