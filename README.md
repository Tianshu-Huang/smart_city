# Allegheny County Right-Turn & RTOR Crash Analysis (2005–2024)

This repository analyzes 20 years of PennDOT crash data (2005–2024) for **Allegheny County, PA**, with a specific focus on:

- Right-turn crashes  
- Right-Turn-On-Red (RTOR) crashes  
- Non-motorist involvement (pedestrians & cyclists)  
- Crash severity and fatalities  
- County-wide spatial risk mapping and heatmaps  

This project supports **Vision Zero–style safety analysis** by identifying high-risk intersections and movement patterns that disproportionately impact vulnerable road users.

---

## Data Sources & Coding Standards

- **Data Source:** PennDOT Crash Reporting System  
- **Tables Used:**
  - Crash Table: crash-level severity, location, non-motorist counts  
  - Vehicle Table: per-vehicle movement codes  
  - Roadway Table: roadway & street name context  

- **Key Movement Codes:**
  - `09` = Right Turn on Red (RTOR)  
  - `10` = Right Turn  
  - `11`, `12` = Left Turn  

- **Intersection Classification:**
  - `INTERSECT_TYPE = 01–13` → intersection-related  
  - `00` → non-intersection  
  - `99` → unknown (excluded)  

---

## Automatic Multi-Year Data Loading

- Automatically scans:
  - `Allegheny_2005` through `Allegheny_2024`  
- Automatically loads:
  - Crash records  
  - Vehicle movement records  
  - Roadway & street name data  
- Automatically merges:
  - Crash + Vehicle + Roadway tables  
- **No manual year selection is required**

---

## Non-Motorist Risk Analysis

- Left-turn vs Right-turn vs RTOR crash comparison  
- Non-motorist hit rate calculation  
- Pedestrian vs cyclist breakdown  
- Serious injury and fatality rate computation  
- Motorist vs non-motorist severity comparison  

### Confirmed Findings

- Right-turn crashes show **higher non-motorist hit rates than left turns**
- RTOR crashes show **dramatically elevated non-motorist hit rates**
- Non-motorist crashes are **2–3× more likely** to result in serious injury or death  

---

## Spatial Mapping & Visualization Outputs

- Static crash point maps  
- County-wide right-turn-only heatmaps  
- Animated year-by-year heatmaps (2014–2024)  
- Intersection-level danger maps  
- RTOR-specific non-motorist intersection maps  
- Hoverable intersection maps with:
  - Crash counts  
  - Serious injuries  
  - Fatalities  

### Output Format

- All maps are exported as:
  - `*.html`  
- All maps are viewable in:
  - Any web browser  
  - GitHub Pages  

---

## Severity-Weighted Heatmaps

### Crash Weighting System

- `1` point  = base crash  
- `+4` points = serious injury  
- `+10` points = fatality  

### Purpose

- Ensures fatal clusters visually dominate risk zones  
- Prevents low-severity clutter from masking lethal intersections  

---


### Available Demonstrations

- Animated right-turn crash heatmap  
- RTOR non-motorist intersection danger map  

---

## Python Libraries Used

- `pandas`  
- `numpy`  
- `geopandas`  
- `matplotlib`  
- `folium`  
- `branca`  
- `glob`  
- `os`  

---

## Research Applications

- Vision Zero safety audits  
- RTOR policy evaluation  
- Intersection redesign decisions  
- Smart city traffic mitigation planning  
- Pedestrian & cyclist safety studies  

---

## Limitations

- Near-miss events are **not recorded** in PennDOT data  
- RTOR identification is **inferred from vehicle movement codes**  
- Coordinate accuracy **varies by year**  
- Pedestrian signal phase data is **not available**  

---

## Author

- **Developed by:** Tianshu Huang  
- **Affiliation:** Carnegie Mellon University  
- **Focus Area:** Smart Cities / Transportation Safety Analysis  
