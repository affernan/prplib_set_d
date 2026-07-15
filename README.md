<p align="center">
  <strong>PRPLIB_SET_D</strong><br />
  Set D benchmark instances for PRPLIB-style vehicle routing experiments.
</p>

<p align="center">
  <img alt="Text instances" src="https://img.shields.io/badge/format-text-2f6f4e" />
  <img alt="Instances 180" src="https://img.shields.io/badge/instances-180-444444" />
</p>

<p align="center">
  <code>PRPLIB</code> | <code>Vehicle Routing</code> | <code>Time Windows</code> | <code>Benchmarks</code>
</p>

---

`prplib_set_d` contains Set D instances for PRPLIB-style vehicle routing experiments. The files use UK-based location names and include matrix data, depot information, customer data, and time-window-related fields.

The repository is data-only. It does not include a solver, parser, or benchmark runner.

## Product Surface

| Area | Contract |
| --- | --- |
| Runtime | None; static benchmark files |
| Data format | Plain-text routing instances |
| Data path | External solver or parser reads files directly |
| Storage | Git-tracked `.txt` files |
| Documentation | This README |
| Distribution | GitHub repository |

## Runtime Shape

```mermaid
flowchart LR
  researcher["Researcher"] --> repo["PRPLIB_SET_D"]:::primary
  repo --> files["180 UK instances"]
  files --> solver["Routing algorithm"]

  classDef primary fill:#2f6f4e,stroke:#173927,color:#ffffff,stroke-width:2px
```

## Responsibilities

- Preserve Set D routing instances in a stable file layout.
- Organize files by UK problem size and variant.
- Keep matrix, depot, customer, and time-window data available for external experiments.
- Avoid embedding solver-specific assumptions in the repository.

## How It Is Built

Files follow this pattern:

```text
UK<size>_<variant>-D.txt
```

| Group | Count |
| --- | ---: |
| `UK10` | 20 |
| `UK15` | 20 |
| `UK20` | 20 |
| `UK25` | 20 |
| `UK50` | 20 |
| `UK75` | 20 |
| `UK100` | 20 |
| `UK150` | 20 |
| `UK200` | 20 |

## Platform and Service Dependencies

<table>
  <tr>
    <th>Service / Object</th>
    <th>Provider</th>
    <th>Usage</th>
    <th>Purpose</th>
  </tr>
  <tr>
    <td><code>UK*_*-D.txt</code></td>
    <td>Repository files</td>
    <td>Consumed by external vehicle routing experiments.</td>
    <td>Provides reproducible Set D routing benchmark inputs.</td>
  </tr>
</table>

## File Structure

Representative files include:

- Number of customers.
- Depot and customer location data.
- Matrix data for travel costs or distances.
- Customer attributes such as demand, service information, and time-window values.

Parser implementations should validate the expected section order against a representative instance before processing all 180 files.

## Verification

No automated tests are defined. Recommended manual verification is to parse one instance from each size group.

## Secret Handling

The repository contains benchmark data only and should not store credentials or private operational data.
