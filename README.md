# Rental Affordability Across the United States

An exploratory analysis of rental affordability across U.S. metropolitan areas using Zillow Research data. This project quantifies where renters face the highest barriers in housing affordability and how rents have moved relative to other U.S. metros and relative incomes.

## Research Question

How has housing affordability evolved over time across major U.S. metropolitan areas?

## Datasets

- `top10_metros_clean.csv`
- `us_all_datasets_cleaned.csv`

### Metrics

- **Zillow Home Value Index (ZHVI):** A measure of the typical home value and market changes across a given region and housing type. It reflects the typical value for homes in the 35th to 65th percentile range. Available as a smoothed, seasonally adjusted measure and as a raw measure.
- **New Homeowner Income Needed:** An estimate of the annual household income required to spend less than 30% of monthly income on the total monthly payment after newly purchasing the typical home with a 20% down payment.
- **Years to Save:** A measure of the number of years it would take the median household to save for a 20% down payment on a home, assuming they are able to save 10% of their income into a simple savings account accruing no interest. This is equivalent to the number of years it would take the median household to save for a 10% down payment, assuming a 5% savings rate.
- **New Homeowner Affordability:** A measure of the share of income the median household would spend on a newly purchased home, including its mortgage payment, homeowner's insurance, property taxes, and maintenance costs. Typically, spending more than 30% of income on housing is considered unaffordable.
- **Zillow Observed Rent Index (ZORI):** A smoothed measure of the typical observed market rate rent across a given region. ZORI is a repeat-rent index that is weighted to the rental housing stock to ensure representativeness across the entire market, not just those homes currently listed. The index is dollar-denominated by computing the mean of listed rents that fall into the 35th to 65th percentile range for all homes and apartments in a given region, which is weighted to reflect the rental housing stock.
- **Zillow Observed Renter Demand Index (ZORDI):** A measure of the typical observed rental market engagement across a region. ZORDI tracks engagement on Zillow's rental listings to proxy changes in rental demand. The metric is smoothed to remove volatility.
- **New Renter Income Needed:** An estimate of the household income required to spend less than 30% of monthly income to newly lease the typical rental.
- **New Renter Affordability:** A measure of the share of income the median household would spend to newly lease the typical rental. Spending more than 30% of income on housing is considered unaffordable.

## Methodology

1. **Ingestion:** pulled ZHVI, ZORI, ZORDI, and Zillow's affordability series at the metro level directly from Zillow Research's public data releases. Reshaped the wide-format CSVs (dates as columns) into long format for time-series analysis, then merged across metric files on region and date. Produced two analysis-ready datasets: a focused panel of the top 10 U.S. metros by population (`top10_metros_clean.csv`) and a broader national-level file for baseline context (`us_all_datasets_cleaned.csv`).
2. **Cleaning:** handled missing months, aligned metro names across datasets, and filtered to the study period.
3. **Feature engineering:** computed rent-to-income and mortgage-to-income ratios, year-over-year rent and home-value growth rates, price-to-rent ratios, affordability gaps against the 30% benchmark, and years-to-save metrics for prospective buyers at median household income.
4. **Analysis:** bivariate comparisons across metros, trend decomposition, and affordability gap calculations against the 30% benchmark.
5. **Visualizations:** temporal trends and cross-metro comparisons.
