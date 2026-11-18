# Evaluating Fourier Neural Operators and U-Net Architectures for Regional Weather Prediction and High-Factor Spatial Downscaling Using ERA5 Reanalysis

An end-to-end meteorological data analysis and AI-based forecasting project using ERA5 and ERA5-Land reanalysis datasets to study weather patterns across India, with a detailed regional focus on Tamil Nadu and Chennai.

## Project Overview

This project explores historical meteorological data from 2020 to 2024 and develops machine-learning and deep-learning workflows for weather forecasting and spatial downscaling.

It combines climate data processing, statistical analysis, geospatial visualization, time-series forecasting, and deep-learning architectures to investigate atmospheric patterns and predict important weather variables.

## Research Objectives

- Analyze historical meteorological patterns across India.
- Study seasonal and regional variations in temperature, rainfall, humidity-related variables, and atmospheric conditions.
- Investigate Chennai's weather patterns using historical ERA5-Land data.
- Develop leakage-safe datasets for hourly and daily weather forecasting.
- Explore deep-learning architectures for spatial weather forecasting.
- Compare learned spatial downscaling against conventional interpolation methods.

## Datasets

The project uses two primary datasets:

| Dataset | Geographic coverage | Resolution | Period |
|---|---|---|---|
| ERA5 daily statistics | India | 0.25° | 2020–2024 |
| ERA5-Land hourly | Tamil Nadu | 0.1° | 2020–2024 |

Data source: [Copernicus Climate Data Store](https://cds.climate.copernicus.eu/)

### Meteorological Variables

- `t2m` – 2-metre air temperature
- `tp` – Total precipitation
- `tcwv` – Total column water vapour
- `blh` – Boundary layer height
- `tcc` – Total cloud cover
- `d2m` – 2-metre dewpoint temperature
- `u10` – 10-metre U wind component
- `v10` – 10-metre V wind component
- `sp` – Surface pressure

## Project Methodology

### Part 1: Understanding and Processing Meteorological Data

- Load and inspect ERA5 meteorological datasets.
- Merge daily NetCDF files.
- Handle missing and invalid observations.
- Convert physical units into interpretable measurements.
- Apply geographical masks to isolate India.

### Part 2: Statistical Analysis and Climatology

- Calculate descriptive statistics.
- Analyze daily, weekly, and monthly patterns.
- Generate monthly, weekly, and daily climatologies.
- Investigate seasonal variations.
- Calculate area-weighted meteorological averages.

### Part 3: Geospatial Visualization and Interpretation

- Generate spatial weather maps.
- Compare representative daily weather conditions.
- Visualize monthly and seasonal rainfall distributions.
- Study long-term climatological patterns.
- Compare weather characteristics between Chennai and Delhi.
- Investigate extreme rainfall events.

### Part 4: AI Dataset Preparation

Prepare hourly and daily weather datasets for forecasting.

Key operations:
- Feature and target selection.
- Hour-of-day and day-of-year cyclic encoding.
- Rainfall transformation using `log1p`.
- Chronological training, validation, and testing splits.
- Training-only standardization.
- Sliding-window generation.
- Data leakage validation.

The dataset is divided chronologically:

| Dataset | Period | Purpose |
|---|---|---|
| Training | 2020–2022 | Model learning |
| Validation | 2023 | Model selection |
| Testing | 2024 | Final evaluation |

### Part 5: Deep Learning-Based Weather Forecasting

Explore deep-learning architectures for spatial and temporal weather prediction.

Architectures investigated include:

- CNN – Convolutional Neural Networks
- U-Net – Encoder-decoder architecture with skip connections
- FNO – Fourier Neural Operator
- UFNO – U-Net and Fourier Neural Operator hybrid

The forecasting workflow includes model training, validation, prediction, and evaluation against baseline approaches.

### Part 5.4: Spatial Downscaling

Investigate spatial resolution enhancement using:

- Bilinear interpolation
- Bicubic interpolation
- U-Net-based downscaling
- FNO-based downscaling

Experiments include 10× and 16× downscaling, with comparisons against ERA5 reference fields.

### Part 6: Spatial Forecasting over Tamil Nadu

- Generate regional weather forecast maps.
- Compare observed and predicted weather conditions.
- Visualize forecast errors.
- Generate spatial RMSE maps.
- Evaluate rainfall forecasting using Critical Success Index (CSI).
- Investigate regional model performance.

## Technology Stack

| Category | Technologies |
|---|---|
| Programming | Python |
| Development | Google Colab, Jupyter Notebook |
| Data Processing | NumPy, Pandas, Xarray |
| Scientific Computing | SciPy |
| Machine Learning | Scikit-learn |
| Deep Learning | PyTorch |
| Geospatial Analysis | GeoPandas, Regionmask |
| Visualization | Matplotlib |
| Data Format | NetCDF |
| Data Source | Copernicus ERA5 / ERA5-Land |

## Repository Structure

```text
Meteorological-Data-AI-Forecasting/
│
├── iitp_project.ipynb
├── README.md
├── requirements.txt
│
└── outputs/
    ├── figures/
    ├── tables/
    └── processed/
```

*Note: The outputs directory represents the generated project outputs. The original notebook saves outputs to Google Drive under `iitp_project/`.*

## Installation and Execution

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Meteorological-Data-AI-Forecasting.git
```

### 2. Navigate into the project

```bash
cd Meteorological-Data-AI-Forecasting
```

### 3. Install dependencies

```bash
pip install numpy pandas xarray netCDF4 matplotlib geopandas regionmask scipy scikit-learn torch
```

### 4. Open the notebook

The recommended environment is Google Colab.

1. Upload the notebook to Google Colab.
2. Mount your Google Drive.
3. Download the required ERA5 and ERA5-Land datasets.
4. Configure the dataset directories in the notebook.
5. Execute the notebook cells sequentially.

### Dataset Requirements

The raw ERA5 and ERA5-Land NetCDF files are not included in this repository.

You must download the corresponding datasets from the Copernicus Climate Data Store and configure their locations before executing the notebook.

If using CDS API access, configure your credentials securely. Never upload API keys or authentication files to GitHub.

## Research Significance

This project combines meteorological data analysis with modern deep-learning approaches to investigate weather forecasting and spatial resolution enhancement.

It provides a framework for studying:

- Regional climate variability.
- Extreme rainfall patterns.
- Short-term weather prediction.
- Spatial forecasting performance.
- Deep-learning-based meteorological downscaling.

## Future Scope

- Extend forecasting experiments to additional Indian regions.
- Investigate transformer-based weather forecasting architectures.
- Explore improved extreme rainfall prediction.
- Evaluate generalization across different climatic regions.
- Investigate operational weather forecasting applications.

## Acknowledgements

- Copernicus Climate Change Service (C3S)
- European Centre for Medium-Range Weather Forecasts (ECMWF)
- Open-source scientific Python community

---

**Project:** Meteorological Data Analysis and AI-Based Forecasting  
**Data Period:** 2020–2024  
**Primary Region:** India  
**Regional Focus:** Tamil Nadu and Chennai  
**Development Environment:** Google Colab / Python
