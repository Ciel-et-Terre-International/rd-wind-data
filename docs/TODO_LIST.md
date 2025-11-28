
# TODO List – WindDatas (Updated July 2025)

This consolidated TODO brings together technical, analytical, and scientific priorities across the entire WindDatas project.

---

## TECHNICAL & INFRASTRUCTURE TASKS

### 🔴 PRIORITY 1 – Repository Cleanup & Structure

- [x] Review and update `.gitignore`  
- [x] Must exclude: `__pycache__/`, `*.pyc`, `debug_output.txt`, `/data/`, `/modules/0ld/` (optional)
- [ ] Clarify `temp.py` status → rename `temp_dev_only.py` with header comment
- [ ] Clean or archive `.html` files, or explain their use in README

### 🟠 PRIORITY 2 – Harmonize Fetcher Modules

- [ ] Standardize headers/docstrings (source, purpose, output format)
- [ ] Use consistent function signatures (e.g. `fetch_<source>_data(site_config, dates, output_dir)`)
- [ ] Review error handling and logging strategy
- [ ] Ensure all imports are listed in `requirements.txt` and `environment.yml`

### 🟡 PRIORITY 3 – Orchestration & Core Scripts

- [ ] Review `source_manager.py` for clarity and modularity
- [ ] Clean up `script.py` (clear `main()`, path management, imports)
- [ ] Ensure all output paths (e.g., `/data/`) are configurable

### 🟢 PRIORITY 4 – Documentation & Usage

- [x] Update `README.md` (add scripts/modules explanation, .bat file, source list)
- [x] Maintain `ROADMAP.md`, `CHANGELOG.md`, `WORKFLOW.md`, and this TODO file
- [ ] Add internal references (where to find: `.bat`, notebooks, `/modules/0ld/`)
- [x] Clarify optional visual outputs (e.g., `.html` maps or globe)

### ⚪ PRIORITY 5 – Environment & Installation

- [ ] Clean `requirements.txt` and fix version numbers
- [ ] Harmonize `environment.yml` with `requirements.txt`
- [x] Add an installation guide in `README.md` (conda, pip, Windows/Linux)

### 🔵 PRIORITY 6 – Long-term Enhancements (Optional)

- [ ] Organize `/modules/0ld/` with internal README or archive folder
- [ ] Add linting/formatting tools (e.g. `black`, `flake8`, pre-commit)
- [ ] Refactor UI logic to separate CLI vs GUI
- [ ] Centralize logging using `logging.config`
- [ ] Add test coverage for main modules (even if `tests/` is ignored now)

---

## SCIENTIFIC & DATA ANALYSIS TASKS

### 🔴 PRIORITY A – Station Metadata & Exposure

- [x] Draft technical profiles for Meteostat, NOAA, ERA5, Open-Meteo
- [x] Integrate ECMWF response (Hans Hersbach)
- [x] Create a slide/summary of metadata and source comparison
- [x] Enrich `modele_sites.csv` with height, exposure, terrain context

### 🟠 PRIORITY B – Site-specific Technical Reports

- [x] Standardize report generation for each site
- [x] Include: site description, data sources, statistical results, comparison plots
- [x] Improve `.docx` report format for reproducibility

### 🟡 PRIORITY C – Missing Data & Coverage

- [x] Calculate coverage rates (% of valid days per source)
- [x] Handle missing values (`NA`, `-9999`)
- [ ] Clarify return period methods (e.g., all-direction vs directional)

### 🟢 PRIORITY D – Visualization & Statistics

- [x] Implement Weibull
- [x] Start Gumbel distribution and extrapolation
- [x] Finalize return period standardization
- [x] Improve automated wind rose + radar chart generation
- [x] Build synthesis plots per site and per country

### ⚪ PRIORITY E – Rugosity & Terrain Analysis

- [ ] Implement semi-automated z0 roughness estimation (Google Earth, OSM, CORINE, SRTM)
- [ ] Include exposure scores from 1 to 5
- [ ] Integrate terrain context into station fact sheets

### 🔵 PRIORITY F – Global Wind Atlas (Optional)

- [ ] Evaluate potential for integration (cross-check with observed data)
- [ ] Use GWA as contextual layer, not as primary source

---

_Last updated: July 2025_
