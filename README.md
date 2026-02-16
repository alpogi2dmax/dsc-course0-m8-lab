# Aviation Accident Analysis

## Overview

This lab analyzes aircraft accident data to understand safety patterns across small and large planes. We explore how plane type, weather, and phase of flight affect accident severity and aircraft destruction.

The goal is to identify safest plane types and key factors influencing injuries and damage.

## Dataset

- Source: AviationData.csv
- Filtered to:
    - Accidents from 1983 onward
    - Only professionally built aircraft (Amateur.Built = 'No')
    - PlaneTypes with ≥50 occurrences for reliable statistics

## Key Metrics

- Total.Passengers – Total onboard (fatal, serious, minor, uninjured)
- Frac.Fatal.Serious – Fraction of passengers fatally or seriously injured
- destroyed – Flag if aircraft was destroyed
- PlaneType – Make + Model combination
- PlaneSize – Small (≤20 passengers) vs Large (>20 passengers)
- Weather.Condition.Clean – Visual / Instrument / Unknown
- Phase.Clean – Takeoff, Climb, Cruise, Landing, Maneuvering, Other

## Data Cleaning Process

1. Load dataset with correct encoding
2. Convert dates and extract year
3. Filter for accidents ≥1983 and professional-built aircraft
4. Derive metrics: Total.Passengers, Frac.Fatal.Serious, Destroyed
5. Clean Make/Model, create PlaneType
6. Clean additional variables: Engine type, Weather, Purpose, Phase
7. Remove mostly missing columns
8. Save cleaned dataset for analysis

## Analysis Workflow

1️. Plane Safety Summaries

- Group by PlaneType to compute:
    - Num_Accidents – total accidents
    - Avg_Frac_Fatal_Serious – mean serious/fatal fraction
    - Destruction_Rate – fraction destroyed
- Filter to ≥10 accidents for reliability
- Sort to identify safest planes


2️. Visualizations

- Stripplots / Violinplots for Frac.Fatal.Serious per PlaneType
    - Highlights accident spread and outliers
- Heatmaps for:
    - Weather.Condition.Clean vs PlaneSize
    - Phase.Clean vs PlaneSize


## How to Use

1. Run the cleaning script to generate AviationData_Cleaned.csv
2. Generate PlaneSize from Total.Passengers
3. Use summarize_plane_types() to compute safety summaries
4. Visualize accident patterns with stripplots and heatmaps
5. Interpret findings for reporting or further analysis