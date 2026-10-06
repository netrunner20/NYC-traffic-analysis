# Traffic Accidents in NYC

An exploratory analysis of NYPD motor vehicle collision records from NYC Open Data, built around two questions:

1. Where in Manhattan do collisions cluster?
2. Which vehicle types and brands are most often involved in collisions citywide?

**[Read the full report](https://netrunner20.github.io/nyc-traffic-accidents/Analysis.html)** (rendered from [`Analysis.qmd`](Analysis.qmd))

## Key findings

- **Where crashes cluster:** A 2D density map of ~330K Manhattan crashes shows hotspots in Midtown and the Lower East Side. Each hotspot sits near an entrance to a bridge or tunnel leaving Manhattan: the Lincoln Tunnel, the Ed Koch Queensboro Bridge, the Queens–Midtown Tunnel, and the Williamsburg Bridge. These entry points are likely bottlenecks where commuter traffic merges and changes speed.
- **Which vehicles are involved:** Sedans and SUVs make up 83% of the 2.5M vehicle records analyzed, and Toyota is the most frequent make (17%), followed by Honda, Nissan, and Ford. These are involvement counts, not crash rates, so they largely mirror how common each vehicle is on the road.

## Limitations

- The data only covers collisions reported to the NYPD, so minor crashes are likely under-represented.
- Hotspot locations were read visually from the density map, not computed.
- Without data on how many of each vehicle type or brand are on the road, true collision rates cannot be estimated.

## Data

The raw CSVs (467 MB and 959 MB) are too large for GitHub, so they are not included. To reproduce the report, download both datasets from NYC Open Data (Export → CSV) and save them in this folder under these names:

| File name | Dataset |
|---|---|
| `MotorVehicleCollisions_Crashes.csv` | [Motor Vehicle Collisions – Crashes](https://data.cityofnewyork.us/Public-Safety/Motor-Vehicle-Collisions-Crashes/h9gi-nx95) |
| `MotorVehicleCollisions_Vehicles.csv` | [Motor Vehicle Collisions – Vehicles](https://data.cityofnewyork.us/Public-Safety/Motor-Vehicle-Collisions-Vehicles/bm4k-52h4) |

The report uses a snapshot downloaded in November 2025, covering July 2012 through October 28, 2025 (2,216,938 crash records and 4,448,313 vehicle records). Both datasets are updated regularly, so a newer download will give slightly different numbers.

## Reproduce

Requires R (tidyverse) and [Quarto](https://quarto.org/).

```bash
quarto render Analysis.qmd
```

## Files

| File | Description |
|---|---|
| `Analysis.qmd` | Quarto source: R code and write-up |
| `Analysis.html` | Rendered report (self-contained) |
| `map_image.png` | Google Maps screenshot annotated with the hotspot locations |

## Tools

R (tidyverse, ggplot2), Quarto
