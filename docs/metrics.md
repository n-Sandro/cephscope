# Metrik-Mapping

Harvest-artiges Template-System: Rohcounter aus den Ceph-Datenquellen werden
hier auf benannte, dokumentierte Metriken gemappt.

## Quellen
- Prometheus-mgr-Modul (Port 9283) – Rohcounter im Prometheus-Textformat
- ceph-exporter-Daemon (pro Host) – vollständige Perf-Counter
- Ceph Dashboard REST API – Inventar/Metadaten (JSON)
- CLI `--format json` – Fallback

## Mapping-Tabelle (Platzhalter – wird mit MVP befüllt)

| Cephscope-Metrik | Quelle | Roh-Counter/Feld | Beschreibung |
|---|---|---|---|
| _(noch offen)_ | | | |

## Konventionen für neue Einträge
- Name folgt Schema `<bereich>_<metrik>_<einheit>` (z. B. `pool_used_bytes`)
- Quelle immer eindeutig angeben (mgr-Modul, ceph-exporter, Dashboard-API, CLI)
- Abgeleitete/aggregierte Metriken kennzeichnen und Berechnung kurz erläutern
