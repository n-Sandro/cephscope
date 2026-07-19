# Architecture – Cephscope

Status: Draft / sketch. Will evolve with the project.

## Goal
Collector for Ceph cluster metrics, similar to NetApp Harvest.
Later possibly an appliance or SaaS once the collector proves itself.

## High-level components (sketch)
- **Scraper interface**: abstracts the different Ceph data sources
  (Prometheus mgr module, ceph-exporter, dashboard REST API, CLI fallback)
  behind a unified interface.
- **Exporter interface**: accepts aggregated/derived metrics
  and exposes them externally (e.g. Prometheus format, later possibly
  additional backends).
- **Template system**: Harvest-like mapping of raw counters to
  named, documented metrics (see `docs/metrics.md`).
- **Aggregation/multi-cluster**: collect multiple clusters and provide
  consolidated output.

## Open questions
- Concrete interface design for scraper/exporter not final
- Config format for multi-cluster setup still open
- Dashboards: which tool (Grafana?) and how to deliver them

## Decision history
See `docs/adr/` for individual architecture decisions (ADRs).
