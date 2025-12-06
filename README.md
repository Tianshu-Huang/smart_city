Allegheny County Right-Turn & RTOR Crash Analysis (2005–2024)

This repository analyzes 20 years of PennDOT crash data (2005–2024) for Allegheny County, PA, with a specific focus on:

Right-turn crashes

Right-Turn-On-Red (RTOR) crashes

Non-motorist involvement (pedestrians & cyclists)

Crash severity and fatalities

County-wide spatial risk mapping and heatmaps

The project supports Vision Zero–style safety analysis by identifying high-risk intersections and movement patterns that disproportionately impact vulnerable road users.

Repository Structure
smart_city/
│
├── Allegheny_2005/ ... Allegheny_2024/   # Raw PennDOT yearly datasets
│   ├── CRASH_ALLEGHENY_YYYY.csv
│   ├── VEHICLE_ALLEGHENY_YYYY.csv
│   ├── ROADWAY_ALLEGHENY_YYYY.csv
│
├── Crash_Data_Dictionary_2025.pdf      # PennDOT datasets dictonary
├── traffic_analysis.ipynb              # Main analysis notebook
├── right_turn_heatmap_animation.html  # Animated right-turn heatmap
├── rtor_non_motorist_intersection_map.html  # RTOR intersection map
├── README.md


Data Sources

All data originates from the PennDOT Crash Reporting System, including:

Crash Table – crash-level details (severity, location, non-motorist counts)

Vehicle Table – per-vehicle movement codes (turn behavior)

Roadway Table – street & intersection context

Key movement codes used:

09 = Right Turn on Red (RTOR)

10 = Right Turn

11, 12 = Left Turn

Intersection classification uses:

INTERSECT_TYPE = 01–13 → intersection-related

00 → non-intersection

99 → unknown (excluded)

Key Features of the Analysis
Automatic Multi-Year Data Loading

The notebook automatically scans all Allegheny_YYYY folders and merges:

Crash data

Vehicle movement records

Roadway & street name data

No manual year selection is required.

Non-Motorist Risk Analysis

The notebook computes:

Left-turn vs Right-turn vs RTOR crash risk

Non-motorist hit rate

Pedestrian vs Cyclist breakdown

Serious injury and fatality rates

Motorist vs Non-motorist severity comparison

Confirmed findings include:

Right-turn crashes have a higher non-motorist hit rate than left turns

RTOR crashes have a dramatically elevated non-motorist hit rate

Non-motorist crashes are 2–3× more likely to result in serious injury or death

Spatial Mapping & Visualization Features

The notebook generates:

Static crash point maps

Right-turn-only county heatmaps

Animated year-by-year heatmaps (2014–2024)

Intersection-level danger maps

RTOR-specific non-motorist intersection maps

Hoverable intersection maps with crash counts & injuries

All maps are exported as:

*.html


and can be opened in any browser or deployed via GitHub Pages.

Severity-Weighted Heatmaps

To better reflect true safety risk, each crash is weighted using:

1  point  = base crash  
+4 points = serious injury  
+10 points = fatality  


This ensures that fatal clusters visually dominate risk zones.

GitHub Pages Interactive Maps

Live, shareable interactive maps are hosted here:

https://tianshu-huang.github.io/smart_city/


Available demos include:

Animated right-turn crash heatmap

RTOR non-motorist intersection danger map

Key Python Libraries Used
pandas
numpy
geopandas
matplotlib
folium
branca
glob
os

Research Applications

This analysis supports:

Vision Zero safety audits

RTOR policy evaluation

Intersection redesign decisions

Smart city traffic mitigation planning

Pedestrian & cyclist safety studies

Limitations

PennDOT does not record true near-miss events

RTOR is inferred from vehicle movement codes

Coordinate accuracy varies by year

No direct pedestrian signal phase data available

Author

Developed by Tianshu Huang
Carnegie Mellon University – Smart Cities / Transportation Safety Analysis
