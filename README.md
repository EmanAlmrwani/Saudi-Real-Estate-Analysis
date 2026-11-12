# Saudi Real Estate Market Analysis

## Overview
An exploratory data analysis of Saudi Arabian real estate **listings** using Python. The project compares asking prices and annual apartment rents across five cities: Riyadh, Jeddah, Dammam, Khobar and Madinah.

> **Important:** These figures describe listings in the dataset, not completed transactions, official market statistics, or necessarily current market prices.

## Business Questions
- How do villa and apartment asking prices per square meter differ across the five cities?
- How do annual apartment asking rents compare?
- Which Riyadh neighborhoods have the highest median villa asking price per square meter, among neighborhoods with at least 100 listings?
- How strongly are listed property area and asking price correlated?

## Tools
Python · Pandas · NumPy · Matplotlib · Google Colab

## Data and Approach
- Source: *Real Estate Listings Dataset: Saudi Arabia* on Kaggle (downloaded for analysis).
- Filtered to five target cities.
- Separated sale listings from rental listings; for rent comparisons, used listings identified as **Yearly**.
- Analyzed villas and apartments separately.
- Excluded sale listings priced at SAR 1 or less.
- For the villa price-per-sqm analysis, used listings with area ≥100 m².
- For the apartment sale analysis, used listings with price ≥SAR 10,000 and area ≥30 m².
- For annual apartment rent comparisons, used listings with asking rent ≥SAR 5,000.
- For additional rental *area-based* analyses, used a separate subset with area from 30 to 500 m².
- Compared **medians** to reduce sensitivity to unusually high values.

These screening cutoffs are exploratory assumptions, not official definitions of valid prices or sizes. Listings may contain other data-quality issues, and duplicate IDs alone do not rule out repeated physical properties.

## Key Findings

### Median asking prices per square meter (SAR)

| City | Villas | Apartments |
|---|---:|---:|
| Dammam | 4,229.81 | 3,026.32 |
| Jeddah | 4,900.00 | 3,600.96 |
| Khobar | 3,720.00 | 3,625.00 |
| Madinah | 4,733.73 | 3,318.38 |
| Riyadh | 5,929.49 | 5,020.92 |

Riyadh recorded the highest median listed price per square meter for both villas and apartments in the selected dataset.

### Median annual apartment asking rents (SAR)

| City | Median annual rent |
|---|---:|
| Dammam | 24,000 |
| Jeddah | 33,000 |
| Khobar | 28,000 |
| Madinah | 20,000 |
| Riyadh | 38,000 |

### Additional observations
- Hittin had the highest median villa asking price per sqm (SAR 12,500) among the Riyadh neighborhoods examined with at least 100 villa listings.
- Pearson area–asking-price correlations within **different focused plotting subsets** were 0.595 for villas and 0.429 for apartments. These subset-specific figures should not be treated as a controlled like-for-like comparison.
- Large and very small listed areas and implausible asking prices were observed; these highlight the need for data-quality checks.

## Project Files
The analysis notebook, charts, and processed summary CSV files will be added to this repository. The notebook is the source of the computations; outputs shown above are based on the analysis performed in Google Colab.

## Limitations
- Listing prices are not verified sale or lease transaction values.
- Data collection period and representativeness should be verified before making time-specific claims.
- Different filtering rules apply across property types; comparisons are descriptive rather than causal.
- No location-, age-, or feature-adjusted valuation model has been developed.
- Rental area anomalies were investigated separately; city-level annual-rent summaries use the price-filtered subset, not the area-filtered one.

## Next Steps
- Publish the complete Colab notebook and generated charts.
- Add data provenance, data dictionary, and reproducible environment instructions.
- Validate remaining extreme and missing values, and document sensitivity to filters.
