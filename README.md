
# WindDatas – Analysis of Observed and Modeled Wind Data

WindDatas is a modular and scalable Python project designed to analyze, compare, and validate wind data from **weather stations (observed)** and **weather APIs or climate reanalysis models (modeled)**. The goal is to provide a rigorous, transparent, and reproducible evaluation of model performance using long-term historical datasets.

---

## Objectives

- Automatically retrieve wind data for dozens to hundreds of sites worldwide.
- Compare observed data (NOAA ISD, Meteostat) with modeled sources (ERA5, NASA POWER, OpenMeteo, MERRA-2, Visual Crossing, Meteo-France).
- Perform detailed statistical analyses with return period calculations, outlier detection, and wind direction/intensity characterization.
- Generate clean CSV files and Word reports for each site, structured by country.
- Enable reproducible scientific investigation via detailed analysis notebooks.
- Support automation, modularity, and professional documentation for future team adoption.

---

## Main Features

- Selection of the two closest **Meteostat** and **NOAA ISD** stations per site, based on distance and temporal coverage.
- Automatic data download from all activated sources, without filtering by country or custom rules.
- Extraction of daily wind extremes (max gusts, mean speed, direction) from hourly ISD NOAA files.
- Tkinter interface to dynamically define the study period at runtime.
- Multi-source support: observed and modeled data are always fetched in parallel for each site.
- ERA5 retrieval with asynchronous/month-tracking logic (auto-restart and timeout handling).
- Optional support for additional sources: MERRA-2, Visual Crossing, Meteo-France.
- CSV naming convention includes station and source info (e.g., `meteostat1_<site>.csv`, `noaa_station2_<site>.csv`).
- Generation of interactive HTML globe visualizing sites and station links.
- Word reports auto-generated per country, with embedded figures and summary tables.
- Modular architecture and maintainable code: each fetcher or analyzer lives in a dedicated module.
- Unit testing infrastructure with tests located in the `tests/` directory.

---

## Project Structure

```
WindDatas/
├── script.py
├── modele_sites.csv
├── run_winddatas.bat
├── environment.yml
├── requirements.txt
├── data/
│   └── <site_code>/figures_and_tables/
│   └── <site_code>/report/
│   └── <site_code>/raw datas .csv
├── modules/
│   ├── noaa_station_finder.py
│   ├── noaa_isd_fetcher.py
│   ├── noaa_api_fetcher.py
│   ├── meteostat_fetcher.py
│   ├── era5_fetcher.py
│   ├── openmeteo_fetcher.py
│   ├── nasa_power_fetcher.py
│   ├── visualcrossing_fetcher.py
│   ├── merra2_fetcher.py
│   ├── meteo_france_fetcher.py
│   ├── comparator.py
│   ├── stats_calculator.py
│   ├── source_manager.py
│   ├── merger.py
│   ├── site_enricher.py
│   ├── globe_visualizer.py
│   ├── report_generator.py
│   ├── tkinter_ui.py
│   └── utils.py
├── notebooks/
│   └── Notebook.ipynb
├── tests/
│   └── test_<module>.py
└── README.md
```

---

## Workflow Overview

```
    modele_sites.csv
            │
            ▼
        script.py
            │
            ▼
     All sources activated
 ┌─────────────┬─────────────┬─────────────┐
 ▼             ▼             ▼             ▼
NOAA ISD   Meteostat      ERA5     OpenMeteo/NASA/Other
  │             │             │             │
  ▼             ▼             ▼             ▼
 CSV1/2     CSV1/2         CSV           CSV
            │
            ▼
   Statistical Analysis & Comparison
            │
            ▼
     Word Reports, Graphs, HTML Globe
```

---

## Installation

### With Conda (recommended)

```
conda env create -f environment.yml
conda activate winddatas
```

### With pip (alternative)

```
pip install -r requirements.txt
```

---

## Usage

To run the full workflow:

```
run_winddatas.bat
```

Or manually:

```
python script.py
```

This triggers:
- UI interface to input study dates
- Automatic download of all sources for all sites
- Statistical comparison and return period computation
- Generation of CSVs, plots, and Word reports

Output example: data/IND002_MUMBAI/meteostat1_RUMSL.csv

---

## Output Files

For each site in `data/<SITE_NAME>/`:

- `meteostat1_<site>.csv`, `meteostat2_<site>.csv`
- `noaa_station1_<site>.csv`, `noaa_station2_<site>.csv`
- `era5_<site>.csv`, `openmeteo_<site>.csv`, etc.
- Folder `figures_and_tables/` with all plots
- Summary Word report per country
- Optional interactive globe view in HTML

---

## Integrated Data Sources

**Observed:**
- NOAA ISD (2 nearest stations, hourly decoded)
- Meteostat (2 nearest stations with metadata)

**Modeled:**
- ERA5 (wind gusts optionally commented)
- OpenMeteo (temporary solution)
- NASA POWER (model-based historical data)
- MERRA-2 (can be deactivated)
- Visual Crossing (can be deactivated)
- Meteo-France (integrated in `source_manager.py`)

---

## Notebooks

- Technical analysis of wind distributions
- Wind rose and radar charts
- Weibull/Gumbel distribution fitting
- Return period curves
- Outlier and threshold detection
- Comparison with building code values

---

## License

MIT License – Free to use and modify with attribution.

---

## Project Documents

- [Project Roadmap](ROADMAP.md)
- [Git Workflow](WORKFLOW.md)
- [Contribution Guidelines](CONTRIBUTING.md)

---

## Author

Initial project: **Adrien Salicis**  
Organization: **Ciel & Terre International**  
Contact: [adrien.salicis@cieletterre.net](mailto:adrien.salicis@cieletterre.net), [adrien.salicis@icloud.com](mailto:adrien.salicis@icloud.com)
