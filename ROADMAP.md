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
- [x] Bronze JSONL transformation foundation
- [x] Local quality checks
- [x] Local orchestration foundation
- [x] Local observability reports
- [x] Static local dashboard
- [x] Documentation site updated

**Pending:**
- [ ] Real API execution hardening
- [ ] Schema verification
- [ ] Silver modeling
- [ ] Gold modeling
- [ ] Cloud/local emulator integration
- [ ] Automated end-to-end CI
