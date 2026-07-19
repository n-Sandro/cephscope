# Project: Cephscope – metrics collector for Ceph (like NetApp Harvest)

## Goal
Collector for Ceph cluster metrics, similar to NetApp Harvest.
Later possibly an appliance or SaaS once the collector proves itself.

## Decisions so far
- Name: **Cephscope** (checked: no collision on GitHub/npm/PyPI,
  domain likely available but not finally verified)
- Language: **Go** (like Harvest itself, good Prometheus client libraries,
  static binaries, well suited for a future appliance)

## Ceph data sources (researched)
- Prometheus mgr module (`ceph mgr module enable prometheus`), port 9283,
  provides raw counters in Prometheus text format
- ceph-exporter daemon (per host, required in newer releases for
  complete perf counters, because the mgr module no longer provides them by default)
- Ceph Dashboard REST API (JSON, for inventory/metadata)
- CLI with `--format json` as fallback

## Differentiation vs existing Ceph Prometheus exporter
Raw data already exists – value lies in aggregation, multi-cluster support,
meaningful derived metrics, ready dashboards, and a Harvest-like
template system for metric mappings.

## Rough effort estimate (at 1-2h/day)
- MVP (1 cluster, core metrics): 3-6 weeks
- Multi-cluster + config: +3-4 weeks
- Dashboards/aggregation: +2-4 weeks
- Stabilization/release v1: +2-3 weeks
- Until a "good collector": ~3-5 months
- Appliance afterwards: +2-4 months
- SaaS afterwards: +4-6+ months

## Tooling setup
- Planning/architecture: Claude Chat in project "Ceph Harvest"
- Coding: Claude Code (VS Code extension, official Anthropic extension,
  requires VS Code 1.94+)
- Repo structure: `ARCHITECTURE.md`, `docs/adr/` for decisions,
  `docs/metrics.md` for metric mapping

## Open next steps
- Verify GitHub account/domain for "cephscope" finally
- Set up Go module base structure
- First architecture sketch (scraper interface, exporter interface)
