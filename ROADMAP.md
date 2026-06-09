# Project Roadmap

The Open Data Lakehouse Lab follows a milestone-based roadmap.

## Milestones

| Milestone | Name | Description | Status |
| --------- | ---- | ----------- | ------ |
| M0 | Foundation | Project governance, principles, and core local repository foundation. | **Completed** |
| M1 | Weather MVP | First local vertical slice implemented with `meteocat-weather`. | **In Progress** |
| M2 | Local cloud lab integration | Integration with Azure/AWS/GCP local lab repositories and emulator candidates. | To Do |
| M3 | Silver/gold modeling | Implementation of Silver and Gold layers for the weather dataset. | To Do |
| M4 | Analytics and dashboard evolution | Advanced BI tools, Parquet evaluation, and API development. | To Do |
| M5 | Multi-cloud comparison | Comparative analysis and deployment across different cloud providers. | To Do |

## Milestone Details

### M0 - Foundation (Completed)
Core infrastructure and governance established for:
- [x] `datasets-catalog`
- [x] `ingestion`
- [x] `transformation`
- [x] `quality`
- [x] `orchestration`
- [x] `observability`
- [x] `dashboards`
- [x] Documentation site (`open-data-lakehouse-lab.github.io`)

### M1 - Weather MVP (In Progress)
First local vertical slice implemented.

**Completed:**
- [x] `meteocat-weather` dataset selected
- [x] Landing JSON ingestion foundation
- [x] Draft landing contracts and permissive schemas
- [x] Bronze JSONL transformation foundation
- [x] Silver JSONL transformation foundation
- [x] Local quality checks
- [x] Optional landing contract validation in quality
- [x] Silver quality validation
- [x] Multi-resource local orchestration
- [x] Optional contract validation integrated into orchestration
- [x] Multi-resource local E2E run with Silver verified
- [x] Multi-resource local E2E run with contracts verified
- [x] `stations-metadata -> stations`
- [x] `variables-metadata -> variables`
- [x] `measured-variable -> measurements`
- [x] Local observability reports
- [x] Static local dashboard
- [x] Documentation site updated
- [x] Local E2E run verified
- [x] Observability report generated from real local run summary
- [x] Static dashboard generated from observability report
- [x] Meteocat real API ingestion hardening
- [x] Configurable timeout and retry settings
- [x] Connector-specific error handling
- [x] Mocked tests for HTTP errors, timeouts and invalid JSON

**Pending:**
- [ ] Real live API verification
- [ ] Real source payload verification
- [ ] Schema verification hardening
- [ ] Silver model hardening
- [ ] Gold modeling
- [ ] Cloud/local emulator integration
- [ ] Automated end-to-end CI
