# Data schema — Risk & Control 101

Everything published here is available as open data under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Attribute as
*Risk & Control 101 by Sambhav Jain* and say if you changed anything.

## Files

| File | What it is |
|---|---|
| `data/risk-control-101.json` | Everything in one bundle — metadata, industry taxonomy and all records |
| `data/internal-audit-programmes.csv` | The internal audit lens, one row per review area |
| `data/icfr-risk-control-matrix.csv` | The ICFR lens, one row per control |
| `data/industries.csv` | The industry taxonomy, flat |
| `data/*.json` | The working source files the site is built from |

CSV files are UTF-8 with a byte-order mark, so they open correctly in Excel by
double-click. List fields are collapsed into a single cell, numbered, one per line.

## Record types

Every record carries `lens`, an array containing `ia`, `icfr`, or both. That is what
decides which view it appears in.

### Shared fields

| Field | Type | Notes |
|---|---|---|
| `industry` | array of strings | Industry ids from the taxonomy. `["cross"]` means it applies to every industry |
| `process` | string | Top-level process, e.g. `Procure to Pay` |
| `subprocess` | string | The specific area within the process |
| `risk` | string | What can go wrong, stated as an outcome rather than a topic |
| `rating` | `High` \| `Medium` \| `Low` | Inherent risk, before controls |
| `lens` | array | `["ia"]`, `["icfr"]`, or both |

### Internal audit records

| Field | Type | Notes |
|---|---|---|
| `id` | string | Stable reference, e.g. `IA-PAY-03` |
| `plain` | string | One sentence on why the risk matters, in plain English |
| `risk_category` | string | `Financial`, `Operational`, `Compliance`, `Fraud`, `IT`, `Strategic` |
| `audit_objective` | string | The single thing this part of the audit establishes |
| `what_to_review` | array | The areas to look at |
| `procedures` | array | Field procedures, in the order you would run them |
| `red_flags` | array | Signs the risk may already have materialised |
| `evidence` | array | Data and documents to request |
| `kpis` | array | Measures that indicate whether the process is working |

### ICFR records

| Field | Type | Notes |
|---|---|---|
| `control_id` | string | Stable reference, e.g. `P2P-01` |
| `risk_id` | string | Reference for the risk the control answers |
| `control_objective` | string | What the control is there to achieve |
| `control` | string | What actually happens, who does it, and when |
| `control_type` | `Preventive` \| `Detective` | |
| `control_nature` | string | `Manual`, `Automated`, `IT-Dependent Manual` |
| `frequency` | string | `Per Transaction`, `Daily`, `Weekly`, `Monthly`, `Quarterly`, `Annual`, `Event Driven` |
| `assertions` | string | Comma-separated codes — see below |
| `coso` | string | COSO component |
| `key_control` | `Yes` \| `No` | Whether reliance would be placed on it |
| `fraud` | `Yes` \| `No` | Whether it addresses a fraud risk |
| `owner` | string | Role that performs the control |
| `sod` | string | Segregation of duties considerations |
| `test_design` | string | How to test that the control is designed to work |
| `test_oe` | string | How to test that it operated all period |
| `population` | string | What the sample is drawn from |
| `sample` | string | Sample size guidance |

### Assertion codes

`E/O` existence or occurrence · `C` completeness · `A/V` accuracy and valuation ·
`R&O` rights and obligations · `CO` cut-off · `P&D` presentation and disclosure

## Industry taxonomy

`industries.json` groups industries by sector. Each entry has an `id`, a `name`, and
optionally `exclude` — processes that do not apply to that industry, so a bank is not
shown inventory and costing.

Industry ids are stable. Names may be refined; ids will not change.

## Deep links

Any view can be linked directly:

```
?tab=ia&industry=banking&process=Payroll
?tab=icfr&industry=aviation&process=all
```

`tab` is `ia`, `icfr` or `industry`. `industry` is an id from the taxonomy. `process`
is a process name or `all`.

## Caveats worth knowing before you build on it

- Coverage is uneven. Some processes carry ten or more review areas; others carry one.
  Count before you assume completeness.
- Entries are a starting point, not a conclusion. They need adapting for organisation
  size, operating model and local regulation.
- Nothing here is jurisdiction-specific by design. Where regulation matters, the record
  names the *type* of obligation, not a particular country's law.
