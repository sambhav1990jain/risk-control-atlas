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

## Licence

The content of this project — every risk, control, audit programme and test procedure, and the
JSON data behind them — is licensed under the
[Creative Commons Attribution 4.0 International Licence](https://creativecommons.org/licenses/by/4.0/).

You are free to copy it, adapt it, translate it, and use it commercially, including inside your
firm's own audit methodology. The only condition is attribution: credit *Risk & Control 101 by
Sambhav Jain* and indicate whether you changed anything.

The full legal text is in [LICENSE](LICENSE).

## How this was written

The structure, standard and editorial direction are mine. The entries were drafted with the help
of a large language model working to that direction, and every entry was reviewed before
publication. Content is based on professional practice; none of it is reproduced from any
training course, employer material or client engagement.

Where an entry reflects something specific to how a particular organisation works, that is
coincidence rather than disclosure.

## Using it

Risks and controls here are a starting point, not a conclusion. Adapt them for the size of the
organisation, how it operates, and the regulations that apply where it operates. Nothing here is
professional advice.
