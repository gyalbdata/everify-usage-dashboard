# E-Verify Usage Dashboard

file:///C:/Users/sherp/Downloads/everify_dashboard.html

🔗 **[Live Demo](https://gyalbdata.github.io/everify-usage-dashboard/)** 

An interactive dashboard analyzing employment verification activity across all 50 U.S. states, D.C., and 4 territories — built to answer one question: **is E-Verify enrollment the same as active usage, or are there major gaps between the two?**


---

## Project Background

E-Verify is the U.S. federal system employers use to confirm that new hires are authorized to work in the country. States vary widely in how many employers are enrolled, how many sites are actively verifying hires, and how that activity has shifted year over year.

This project takes a state-level E-Verify usage export (enrolled MOUs, hiring sites, FY2025/FY2026 case counts, 365-day usage, and activity rate) and turns it into an interactive dashboard to surface patterns that aren't visible in the raw numbers — particularly the gap between *enrollment* and *actual usage*.

## Key Findings

- **Scale**: Across 55 jurisdictions, 1.37M+ hiring sites are enrolled and filed 43.8M+ cases in FY2025. Texas, California, Florida, Georgia, and New York alone account for roughly a third of total volume.
- **Enrollment ≠ engagement**: Georgia has the 2nd-highest number of enrolled hiring sites in the country (333K) but the *lowest* Activity % (14.2%) — meaning most of its enrolled sites aren't actually running verification checks. Alabama, Missouri, and Rhode Island show the same pattern.
- **Most engaged states**: Wisconsin (37.0%), Tennessee (36.3%), and Iowa (35.8%) have the highest share of enrolled sites actively verifying new hires.
- **Usage intensity outlier**: Arkansas averages ~71 cases per hiring site in FY2025 — far above the typical 10–25 range elsewhere, consistent with high-turnover industries like agriculture or food processing.
- **Data integrity fix**: FY2026 in the raw data only covers ~9 months (the federal fiscal year starts in October), so a naive FY2026-vs-FY2025 comparison would look like a steep decline. The dashboard instead annualizes FY2026's run rate before comparing it to FY2025, avoiding a misleading conclusion.

## Tech Stack

- **HTML / CSS / JavaScript** — single self-contained file, no build step
- **Chart.js** (via CDN) — bar, dual-series comparison, logarithmic bubble scatter, and horizontal ranking charts
- **Vanilla JS** — client-side sorting for the full data table

## Data Source

E-Verify Usage Statistics, state-level export (Enrolled MOUs, Hiring Sites, FY2026 Cases, FY2025 Cases, 365-day Usage, Activity %). See [`data/everify_2026.csv`](data/everify_2026.csv).

## How to Run Locally

```bash
git clone https://github.com/your-username/everify-usage-dashboard.git
cd everify-usage-dashboard
open index.html   # or just double-click the file
```

No dependencies to install — it runs entirely in the browser.

## What I'd Do Next

- Add a historical time series if multi-year data becomes available, to show real trends instead of a single snapshot
- Add a state-vs-state comparison toggle
- Break out territory data (Guam, Puerto Rico, etc.) into its own view since their scale skews the national charts

## License

MIT — see [LICENSE](LICENSE).
