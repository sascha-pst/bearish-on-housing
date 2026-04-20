# Rental Affordability Across the United States

An exploratory analysis of rental affordability across U.S. metropolitan areas using Zillow Research data. This project quantifies where renters face the highest barriers in housing affordability and how rents have moved relative to other U.S. metros and relative incomes.

## Research Question

Where in the United States can one afford housing under 30% of gross household income?

## Datasets
- Metro_zori_.csv
- Metro_zordi_uc_.csv
- Metro_new_renter_affordability_.csv
- Metro_new_renter_income_needed_.csv


### Metrics

- **Zillow Observed Rent Index (ZORI):** A smoothed measure of the typical observed market rate rent across a given region. ZORI is a repeat-rent index that is weighted to the rental housing stock to ensure representativeness across the entire market, not just those homes currently listed. The index is dollar-denominated by computing the mean of listed rents that fall into the 35th to 65th percentile range for all homes and apartments in a given region, which is weighted to reflect the rental housing stock.

- **Zillow Observed Renter Demand Index (ZORDI):** A measure of the typical observed rental market engagement across a region. ZORDI tracks engagement on Zillow's rental listings to proxy changes in rental demand. The metric is smoothed to remove volatility.

- **New Renter Income Needed:** An estimate of the household income required to spend less than 30% of monthly income to newly lease the typical rental.

- **New Renter Affordability:** A measure of the share of income the median household would spend to newly lease the typical rental. Spending more than 30% of income on housing is considered unaffordable.

## Methodology

1. **Ingestion:** pulled ZORI, ZORDI, and ZHVI series at the metro level and reshaped from wide to long format for time-series analysis.
2. **Cleaning:** handled missing months, aligned metro names across datasets, and filtered to the study period.
3. **Feature engineering:** computed rent-to-income ratios, year-over-year rent growth, and price-to-rent ratios.
4. **Analysis:** bivariate comparisons across metros, trend decomposition, and affordability gap calculations against the 30% benchmark.
5. **Visualizations:** temporal trends and cross-metro comparisons.
