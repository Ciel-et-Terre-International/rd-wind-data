
# Roadmap – WindDatas v1.1 and beyond

This roadmap outlines planned features, ongoing improvements, and development priorities for upcoming versions of the WindDatas project.

---

## General Objectives

- Strengthen the robustness of statistical analyses (return periods, distributions)
- Expand the range of integrated weather data sources (observed and modeled)
- Professionalize user experience through well-structured notebooks and consistent outputs
- Prepare for a potential open-source release

---

## Task Status – Version v1.1

| Task                                                                 | Status     | Priority |
|----------------------------------------------------------------------|------------|----------|
| Integration of MERRA-2 as a new modeled source                       | ✅ Done     | High     |
| Generation of statistical distributions (Weibull, Gumbel)            | ✅ Done     | High     |
| Automatic detection of outliers in wind data                         | ✅ Done     | Medium   |
| Interactive reports and summaries within the analysis notebooks      | ✅ Done     | Medium   |
| Cleanup and unification of all notebooks                             | ✅ Done     | Medium   |
| Comparative multi-site analysis notebook                             | ✅ Done     | Medium   |
| Unit testing coverage for all `fetcher` modules                      | In progress| Medium   |
| Command-line interface (CLI) to launch individual modules            | Planned    | Low      |
| English translation of README and documentation                      | ✅ Done     | Low      |
| Import/export scripts for integration with SQLite or external DB     | Planned    | Low      |

---

## Next Version – v1.1.0

Goal: deliver a stable version with extended statistical capabilities and broader source coverage.

Main Milestones:
- All major sources integrated and working in parallel
- Complete automation through `run_winddatas.bat`
- Word report generation by country
- Interactive HTML globe showing all sites and selected stations

---

## Roadmap Beyond v1.1 (v1.2 → v2.0)

| Planned Feature                                                                 | Version | Priority |
|----------------------------------------------------------------------------------|---------|----------|
| Improved radar plots combining wind direction, intensity, and frequency         | v1.2    | High     |
| Dynamic return period comparison with Building Code reference values            | v1.2    | High     |
| Aggregated statistical summaries per country or region                          | v1.2    | Medium   |
| Integration of quality/rugosity metadata for stations                           | v1.2    | Medium   |
| Automatic rugosity (z0) estimation from OSM or raster data                      | v2.0    | Medium   |
| Dynamic source prioritization strategy per country/region (optional override)   | v2.0    | Low      |
| Optional PostgreSQL or SQLite database backend for site data                    | v2.0    | Low      |
| Full public documentation and open-source release (GitHub Pages or similar)     | v2.0    | Low      |

