# Projekt: Cephscope – Metrik-Collector für Ceph (wie NetApp Harvest)

## Ziel
Collector für Ceph-Cluster-Metriken, ähnlich NetApp Harvest.
Später ggf. Appliance oder SaaS, sobald Collector sich bewährt hat.

## Entscheidungen bisher
- Name: **Cephscope** (geprüft: keine Kollision auf GitHub/npm/PyPI,
  Domain vermutlich frei aber nicht final verifiziert)
- Sprache: **Go** (wie Harvest selbst, gute Prometheus-Client-Libs,
  statische Binaries, gut für spätere Appliance)

## Ceph-Datenquellen (recherchiert)
- Prometheus-mgr-Modul (`ceph mgr module enable prometheus`), Port 9283,
  liefert Rohcounter im Prometheus-Textformat
- ceph-exporter-Daemon (pro Host, seit neueren Releases nötig für
  vollständige Perf-Counter, da mgr-Modul sie nicht mehr standardmäßig liefert)
- Ceph Dashboard REST API (JSON, für Inventar/Metadaten)
- CLI mit --format json als Fallback

## Differenzierung ggü. bestehendem Ceph-Prometheus-Exporter
Rohdaten sind schon da – Mehrwert liegt in: Aggregation, Multi-Cluster-Support,
sinnvolle abgeleitete Kennzahlen, fertige Dashboards, Harvest-artiges
Template-System für Metrik-Mappings.

## Grobe Aufwandsschätzung (bei 1-2h/Tag)
- MVP (1 Cluster, Kern-Metriken): 3-6 Wochen
- Multi-Cluster + Config: +3-4 Wochen
- Dashboards/Aggregation: +2-4 Wochen
- Stabilisierung/Release v1: +2-3 Wochen
- Bis "guter Collector": ~3-5 Monate
- Appliance danach: +2-4 Monate
- SaaS danach: +4-6+ Monate

## Tooling-Setup
- Planung/Architektur: Claude Chat im Project "Ceph Harvest"
- Coding: Claude Code (VS-Code-Extension, offizielle Anthropic-Extension,
  benötigt VS Code 1.94+)
- Repo-Struktur: ARCHITECTURE.md, docs/adr/ für Entscheidungen,
  docs/metrics.md für Metrik-Mapping

## Offene nächste Schritte
- GitHub-Account/Domain final für "cephscope" verifizieren
- Go-Modul-Grundstruktur aufsetzen
- Erste Architekturskizze (Scraper-Interface, Exporter-Interface)
