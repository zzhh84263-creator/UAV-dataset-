
# UAV Dataset

This repository contains UAV (Unmanned Aerial Vehicle) building coverage signal datasets for tasks such as target detection, signal coverage analysis, and image-based research.  
**Note:** The repository provides **data results only**, generated using **MATLAB ray-tracing methods**, and does not include the scripts used to generate them.

---

## Dataset Description

### Dataset 1: Single-Scenario Dataset
- **Folder:** `dataset1`
- **Content:** Signal data for a single building coverage scenario, suitable for scenario-specific research and analysis.
- **Features:**
  - Each data file corresponds to a set of UAV grid points.
  - Moderate dataset size, convenient for quick experiments.

### Dataset 2: Multi-Scenario Dataset
- **Folder:** `dataset2`
- **Content:** Signal data for multiple building coverage scenarios, covering different environments and viewpoints.
- **Features:**
  - Each data file corresponds to a set of UAV grid points.
  - Larger dataset, suitable for cross-scenario research and evaluating model generalization.

## Data Contents

Each `.mat` file contains the following fields:

| Field Name       | Description |
|-----------------|------------|
| `UAVLatitude`    | UAV latitude |
| `UAVLongitude`   | UAV longitude |
| `GridIndex`      | UAV grid point index |
| `SignalStrength` | Signal strength matrix at receiver points |
| `Latitudes`      | Latitude matrix for the receiver grid |
| `Longitudes`     | Longitude matrix for the receiver grid |

> **Note:** `SignalStrength` corresponds to `Latitudes` and `Longitudes` and can be used directly for visualization and analysis.

## Usage Instructions

1. Clone the repository:
```bash
git clone https://github.com/zzhh84263-creator/UAV-dataset.git
````

2. Choose the dataset according to your experiment:

   * Single-scenario experiments: `dataset1`
   * Multi-scenario experiments: `dataset2`

3. Load a `.mat` file in MATLAB and visualize signal coverage, for example:

```matlab
load('dataset1/result_TJ_001.mat');
imagesc(Longitudes, Latitudes, SignalStrength);
colorbar;
xlabel('Longitude'); ylabel('Latitude');
title(['Signal Strength at UAV grid point ', num2str(GridIndex)]);
```

4. The data can be used for:

   * Signal coverage analysis
   * UAV path planning studies
   * Machine learning experiments

---

## Citation

Please cite this dataset appropriately in your research if you use it.

---

## Notes

* Each `.mat` file corresponds to a specific UAV grid point within the dataset.
* The MATLAB ray-tracing method ensures realistic signal propagation calculations.
* This repository contains **only the result data**, not the generation scripts.
