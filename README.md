# EVCharging-Management
# Saudi Arabia Al Jouf — EV Charging Station Dataset

## Overview

This dataset captures simulated electric vehicle (EV) charging operations across a **9-station highway EVCS network** in the **Al Jouf region, Saudi Arabia**. It is constructed through a physics-based Monte Carlo simulation calibrated against real infrastructure deployment parameters, commercially available EV battery specifications, and empirically derived highway traffic arrival patterns.

## Region

The Al Jouf region is one of the largest administrative regions in the Kingdom of Saudi Arabia. Nine EVCS nodes (EVSE 1–9) are positioned along major inter-city highway corridors, serving 14 bidirectional trip routes ranging from 410 km to 787 km. All roads are classified as highways with speed limits of 100–120 km/h.

## Simulation

A fleet of **8,000 EVs** comprising four commercially available models (Tesla Model 3, MG ZS EV Long Range, Ford Explorer Extended Range RWD, and Lucid Air Grand Touring) is distributed daily across a 24-hour Poisson-derived arrival profile (peak: 09:00 at 12.5%). Each vehicle traverses its assigned route with energy consumption computed as:

**E = distance × base\_consumption × driver\_behaviour\_modifier × weather\_modifier**

Charging sessions are triggered at each EVCS when battery SOC drops below 80%, using Level 3 DC fast charging (150 kW). The simulation runs for **90 days** (2,160 hourly timesteps) with a fixed random seed (42) for full reproducibility.

## Files

| File | Shape | Description |
|------|-------|-------------|
| `saudi_ev_unified.csv` | 2,160 × 64 | Hourly time-series: 9 EVCS × 7 features (occupancy, volume\_kwh, duration\_min, e\_price, s\_price, renewable\_kw, ess\_soc) |
| `saudi_evcs_distance.csv` | 9 × 9 | Inter-EVCS pairwise distance matrix (km) |
| `saudi_evcs_adj.csv` | 9 × 9 | K-nearest-neighbour adjacency matrix (K=4) |

```

## License

This dataset is released under the [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) licence.
