# PRPLIB Set D Instances

This repository contains Set D instances for PRPLIB-style vehicle routing experiments.

The files use UK-based location names and include distance or travel-time matrices, depot information, customer data, and time-window related fields. They are intended for computational experiments in pollution-routing and related vehicle routing variants.

## Contents

The repository includes 180 plain-text instances grouped by size:

- `UK10`: 20 instances
- `UK15`: 20 instances
- `UK20`: 20 instances
- `UK25`: 20 instances
- `UK50`: 20 instances
- `UK75`: 20 instances
- `UK100`: 20 instances
- `UK150`: 20 instances
- `UK200`: 20 instances

Files follow the pattern:

```text
UK<size>_<variant>-D.txt
```

## File Structure

Each instance includes:

- Number of customers.
- Depot and customer location data.
- Matrix data for travel costs or distances.
- Customer attributes such as demand, service information, and time-window values.

Because the files are plain text, parser implementations should validate the expected section order against a representative instance before batch processing the full set.

## Suggested Use

These instances are suitable for benchmarking exact methods, heuristics, and metaheuristics for routing problems with environmental or time-dependent cost components.
