# ADR 0001: Project name and language

Status: Accepted

## Context
A collector for Ceph cluster metrics was planned, comparable to NetApp Harvest.

## Decision
- Name: **Cephscope** (checked: no collision on GitHub/npm/PyPI;
  domain likely available but not finally verified)
- Language: **Go** (like Harvest itself, good Prometheus client libraries,
  static binaries, well suited for a future appliance)

## Consequences
- Go tooling and ecosystem will determine further technical decisions
  (module structure, build, client libraries)
- Domain/account verification for "cephscope" remains an open next step
