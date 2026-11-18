# NYPL Energy & Sustainability Map

An interactive map of the New York Public Library's 90+ branches across the Bronx, Manhattan and Staten Island. It brings each branch's energy upgrade status together with the climate and equity risks of the neighborhood it serves.

**Live map:** https://tugesra.github.io/NYPLEnergyMap/

## Why this map exists

NYPL is the largest public library system in the United States, with about 2.7 million gross square feet of buildings. Many of them are designated landmarks. Under NYC Local Law 97 (building emissions limits) and Local Law 88 (lighting upgrades and submetering), the Library must keep cutting energy use and emissions across the whole portfolio.

Every NYPL branch also serves as a cooling center during extreme heat. Many branches are in the city's most heat-vulnerable and environmentally burdened neighborhoods.

The map helps facilities staff answer one question: **where should the next energy upgrade go so that it does the most good for the building and the community?**

## What the map shows

For each branch:

| Layer | What it shows |
|---|---|
| LED lighting | Upgrade status, funding source (NYPL capital or DCAS) and fiscal year |
| Building Management System (BMS) | Installation status, funding source and fiscal year |
| Electrical submetering | Whether the branch is submetered |
| Solar | Whether solar is installed |

Neighborhood context, by census tract:

| Layer | Source |
|---|---|
| Heat Vulnerability Index (HVI), tiers 1–5 | NYC Department of Health and Mental Hygiene |
| Environmental Justice areas | NYC Environmental Justice mapping |
| Flood risk zones | FY2020 energy audits funded by DCAS Division of Energy Management |

Branches are grouped by borough and by NYPL network, so staff can switch a whole network on or off.

## Key findings

From the map data (as of 2024):

- 22 branches (24%) are in HVI Tier 5, the most heat-vulnerable category.
- 30 branches (33%) are inside Environmental Justice areas.
- 49 branches are in areas at risk of flooding.
- 71 branches (78%) have been fully upgraded to LED lighting.
- 44 branches have a Building Management System, up from 7 in 2020.

## Team and my role

This map was built by Jacob Stahl, EHS & Esra Tug, Sustainability at the NYPL Facilities department in 2024. Jacob built the map’s code; Esra built the data and analysis.

**My role (Esra Tug, [Sustainability Analyst Intern], NYPL Facilities, May–December 2024):**

- Built the census-tract-to-branch dataset (`CensusTractbyBranch.geojson`) that links each branch to its HVI tier, Environmental Justice status and flood risk.
- Added the LED and BMS breakdown by funding source (NYPL capital vs. DCAS), so staff can see which agency funds each upgrade.
- Conducted 26 compliance site visits for Local Law 88, Local Law 97 and Local Law 152; findings informed the upgrade data on the map.
- Used the map as the basis for the NYPL case study in my master's capstone, *[Decarbonizing NYC Buildings, Case Study: New York Public Library]*, [Pace University], [2024].


## Tech stack

- [SvelteKit](https://kit.svelte.dev/) with static site generation
- [Leaflet](https://leafletjs.com/) for the map, with layer tree, search and locate plugins
- Branch data in a static JSON file (`static/Data/EnergyDatabase.json`), a snapshot of the original project database
- [CARTO](https://carto.com/basemaps) base map tiles
- GitHub Pages, deployed automatically by GitHub Actions on every push to `main`

## Run it locally

You need [Node.js](https://nodejs.org/) 18 or later.

```bash
git clone https://github.com/tugesra/NYPLEnergyMap.git
cd NYPLEnergyMap
npm install
npm run dev
```

Then open http://localhost:5173.

No API keys or database are needed: all data lives in the repository.

The site is published automatically to GitHub Pages by the workflow in `.github/workflows/deploy.yml` whenever `main` changes.

## Data and license

Branch energy data belongs to the New York Public Library. Census tract, HVI and Environmental Justice layers come from public NYC open data.

This repository is a fork of [stahlnypl/NYPLEnergyMap](https://github.com/stahlnypl/NYPLEnergyMap), the original NYPL Facilities team project. All original commit history and authorship are preserved.

No license has been applied. The original code was written by Jacob Stahl and Esra Tug.

## How to cite

> Tug, E., et al. (2024). *NYPL Energy & Sustainability Map* [Software]. New York Public Library. https://github.com/tugesra/NYPLEnergyMap
