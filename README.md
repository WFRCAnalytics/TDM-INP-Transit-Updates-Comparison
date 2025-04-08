# TDM-INP-Transit-Updates-Comparison

# UTA Transit Boardings Comparison

This Python script analyzes and compares daily transit boardings between two Travel Demand Model (TDM) scenarios:  
- **TDM1**: Base Scenario  
- **TDM2**: UTA Proposed Changes  

The goal is to evaluate ridership impacts across transit **modes**, **routes**, and **service districts**.


## Workflow Summary

### 1. Initialization
- Import Python and ArcPy libraries
- Set working, data, results, and lookup directories

### 2. Data Preparation
- Convert TDM `.dbf` files to `.csv` using `arcpy`
- Read and verify shape of datasets

### 3. Data Processing
- Merge TDM1 and TDM2 datasets by `TDM_Name`
- Calculate differences in:
  - Total daily boardings
  - Walk-access boardings
  - Drive-access boardings
- Join with route metadata (`RouteInfo.csv`)

### 4. Visualization & Analysis
Generates bar charts and summary tables for:
- Total boardings by **transit mode**
- Total boardings by **service district**
- Route-level comparisons for:
  - Local Bus
  - BRT / CRT / LRT
  - Express Bus
- Walk vs. Drive access impacts

---

## Example Output Metrics

### Boardings by Mode (System-Wide)

| Mode         | Base   | UTA Changes | Diff   | % Diff |
|--------------|--------|-------------|--------|--------|
| Local Bus    | 82,595 | 79,579      | -3,016 | -3.7%  |
| LRT          | 65,369 | 60,859      | -4,509 | -6.9%  |
| CRT          | 24,984 | 24,138      | -846   | -3.4%  |
| BRT III      | 14,575 | 13,328      | -1,247 | -8.6%  |
| Express Bus  | 3,794  | 3,751       | -43    | -1.1%  |
| BRT I        | 1,757  | 1,597       | -160   | -9.1%  |
| **Total**    | **193,073** | **183,252** | **-9,821** | **-5.1%** |

---

### Boardings by Service District

| Service District | Base   | UTA Changes | Diff   | % Diff |
|------------------|--------|-------------|--------|--------|
| Salt Lake        | 154,300 | 147,019     | -7,280 | -4.7%  |
| Provo            | 23,889  | 22,154      | -1,735 | -7.3%  |
| Ogden            | 14,884  | 14,078      | -805   | -5.4%  |
| **Total**        | **193,073** | **183,252** | **-9,821** | **-5.1%** |

---

### Walk vs. Drive Access Impacts (Total by Mode)

| Mode        | Walk % Diff | Drive % Diff |
|-------------|-------------|--------------|
| BRT I       | -9.3%       | -1.1%        |
| BRT III     | -9.0%       | +11.7%       |
| CRT         | -4.5%       | -1.3%        |
| Express Bus | -6.4%       | +29.1%       |
| LRT         | -6.6%       | -8.9%        |
| Local Bus   | -4.1%       | +1.0%        |
| **Total**   | **-5.5%**   | **-2.0%**    |

---

## 📈 Charts
- All key comparisons are visualized using Matplotlib
- Custom coloring and formatting for clarity
- Grouped charts include:
  - Daily boardings by mode and district
  - Walk and drive access boarding comparisons
  - Route-level bar charts for each district and transit type

---

## 🧰 Requirements

- Python 3.x  
- ArcPy (must be run within ArcGIS Pro environment)
- `pandas`, `numpy`, `matplotlib`
