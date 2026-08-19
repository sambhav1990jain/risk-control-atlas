# Risk & Control 101

An interactive risk and control database spanning 28 industries, built by
**Sambhav Jain, CA** — Manager, Financial Compliance and Governance.

Choose an industry, then choose a lens:

- **Internal audit** — for each risk: the audit objective, what to review, field procedures,
  red flags, the evidence to request, and the measures that show whether the process works.
- **ICFR** — the risk–control matrix: control objective, control description, preventive or
  detective, nature, frequency, financial-statement assertions, COSO component, key-control and
  fraud flags, segregation-of-duties considerations, and the design and operating-effectiveness
  test steps with population and sample guidance.

Navigate by process and sub-process, search across everything, filter by risk rating, key
controls, fraud relevance and control type, and switch to a coverage map to see where the
risk weight sits.

## Frameworks referenced

- COSO Internal Control — Integrated Framework (2013)
- IIA Global Internal Audit Standards (2024)
- IFRS 15 / ASC 606 for revenue recognition risks
- Sector regulation where relevant — hours of service, dangerous goods, customs, airworthiness

## How it is built

`data/` holds the database as JSON — this is the source of truth. `index.html` is a
self-contained page with the data inlined; it needs no server, no build step and no
dependencies to view.

Content is written from professional practice. It is not reproduced from any proprietary
course, employer material or client engagement.

© 2026 Sambhav Jain. All rights reserved.
