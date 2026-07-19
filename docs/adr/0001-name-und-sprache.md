# ADR 0001: Projektname und Sprache

Status: Angenommen

## Kontext
Es wurde ein Collector für Ceph-Cluster-Metriken geplant, vergleichbar mit
NetApp Harvest.

## Entscheidung
- Name: **Cephscope** (geprüft: keine Kollision auf GitHub/npm/PyPI;
  Domain vermutlich frei, aber nicht final verifiziert)
- Sprache: **Go** (wie Harvest selbst, gute Prometheus-Client-Libs,
  statische Binaries, gut geeignet für spätere Appliance)

## Konsequenzen
- Go-Tooling und -Ökosystem bestimmen weitere technische Entscheidungen
  (Modul-Struktur, Build, Client-Libs)
- Domain/Account-Verifizierung für "cephscope" ist offener nächster Schritt
