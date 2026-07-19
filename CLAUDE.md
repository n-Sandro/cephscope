# Cephscope

Metrik-Collector für Ceph-Cluster (Vorbild: NetApp Harvest).
Sprache: Go. MVP-Fokus: 1 Cluster, Kern-Metriken.

Siehe @ARCHITECTURE.md für Architektur und @docs/metrics.md für Metrik-Mapping.
Ausführliche Vorplanung: @docs/planning.md
Entscheidungen werden als ADRs in docs/adr/ festgehalten.

## Datenquellen
- Prometheus-mgr-Modul (`ceph mgr module enable prometheus`), Port 9283
- ceph-exporter-Daemon (pro Host, seit neueren Releases nötig für vollständige Perf-Counter)
- Ceph Dashboard REST API (JSON, für Inventar/Metadaten)
- CLI mit `--format json` als Fallback

## Differenzierung ggü. bestehendem Ceph-Prometheus-Exporter
Rohdaten sind schon da – Mehrwert liegt in: Aggregation, Multi-Cluster-Support,
sinnvolle abgeleitete Kennzahlen, fertige Dashboards, Harvest-artiges
Template-System für Metrik-Mappings. Nicht einfach Rohdaten-Export duplizieren.

## Konventionen
- Go-Module-Struktur, statische Binaries als Build-Ziel
- Neue Architekturentscheidungen als ADR in docs/adr/ dokumentieren, nicht nur im Chat klären
- Metrik-Mappings zentral in docs/metrics.md pflegen (Harvest-artiges Template-System)
