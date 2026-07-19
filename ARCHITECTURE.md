# Architektur – Cephscope

Status: Entwurf / Skizze. Wird mit dem Projekt weiterentwickelt.

## Ziel
Collector für Ceph-Cluster-Metriken, ähnlich NetApp Harvest.
Später ggf. Appliance oder SaaS, sobald der Collector sich bewährt hat.

## Grobkomponenten (Skizze)
- **Scraper-Interface**: abstrahiert die verschiedenen Ceph-Datenquellen
  (Prometheus-mgr-Modul, ceph-exporter, Dashboard REST API, CLI-Fallback)
  hinter einer einheitlichen Schnittstelle.
- **Exporter-Interface**: nimmt aggregierte/abgeleitete Metriken entgegen
  und stellt sie nach außen bereit (z. B. Prometheus-Format, später ggf.
  weitere Backends).
- **Template-System**: Harvest-artiges Mapping von Rohcountern auf
  benannte, dokumentierte Metriken (siehe docs/metrics.md).
- **Aggregation/Multi-Cluster**: mehrere Cluster einsammeln und konsolidiert
  bereitstellen.

## Offene Punkte
- Konkretes Interface-Design für Scraper/Exporter noch nicht final
- Config-Format für Multi-Cluster-Setup noch offen
- Dashboards: welches Tool (Grafana?) und wie werden sie ausgeliefert

## Entscheidungshistorie
Siehe docs/adr/ für einzelne Architekturentscheidungen (ADRs).
