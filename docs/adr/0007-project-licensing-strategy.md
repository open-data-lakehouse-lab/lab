# ADR 0007: Project Licensing Strategy

## Status

Accepted

## Context

Open Data Lakehouse Lab contains both software assets and documentation/content assets.

Software assets include:

- Source code.
- Scripts.
- Infrastructure as Code.
- SQL models.
- Configuration files.
- Executable assets.
- Automation assets.

Documentation/content assets include:

- Documentation.
- Articles.
- Architecture diagrams.
- Mermaid diagrams.
- Dataset metadata.
- Data dictionaries.
- Schemas.
- Data contracts.
- Written content.

The project needs a clear licensing strategy that is permissive, professional, easy to understand and suitable for a public open-source data engineering laboratory.

## Decision

Use Apache License 2.0 for software assets.

Use Creative Commons Attribution 4.0 International for documentation/content assets.

For software-oriented repositories, the main `LICENSE` file should be Apache License 2.0 and the README should clarify that documentation/content is licensed under Creative Commons Attribution 4.0 International unless otherwise noted.

For documentation/content-oriented repositories, the main `LICENSE` file should be Creative Commons Attribution 4.0 International, and a `LICENSE-CODE` file should contain Apache License 2.0 for software/code assets.

Original upstream dataset licenses are not changed by this project. The project may document metadata, schemas, examples and transformations, but original datasets remain governed by their original source licenses and terms.

## Consequences

Positive consequences:

- Clear reuse permissions.
- Good fit for software, infrastructure and data engineering assets.
- Attribution requirement for documentation and diagrams.
- Better clarity than having no license.
- Lower adoption friction than strong copyleft licenses.

Trade-offs:

- Dual licensing requires clear README and NOTICE sections.
- Contributors must understand which assets are covered by which license.
- Dataset source licenses must still be respected independently.
