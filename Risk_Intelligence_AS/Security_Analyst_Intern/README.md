### Maritime Chokepoint Risk Monitor

An Excel-based structural risk monitor covering all 18 major global maritime chokepoints. Built as the first project in the Job Post to Project series, in response to a Security Analyst intern role at Risk Intelligence A/S in Denmark.

### What it does

Scores each of the 18 chokepoints on a 0 to 100 risk scale using a three-ring model. Ring 1 covers the countries that physically control the chokepoint. Ring 2 covers the surrounding countries. Ring 3 covers outside powers that pressure Rings 1 and 2. An environmental layer scores geography, weather, and bypass availability on top.

Each of the 65 countries in the model gets a country risk score built from six pillars: Governance and Corruption, Economic Strength, Security Environment, Political Stability, External Influence, and Infrastructure. The pillar scores are averaged with adjustable weights in 00_Config.

### What it uses

All public data. No paid APIs. Nineteen source files across thirteen organizations including Transparency International, the IMF, the World Bank, Vision of Humanity, the Fund for Peace, ACLED (manual on my end but has a public dataset), ECMWF Copernicus, IMF PortWatch, and the CIA World Factbook. I'll attach the CIA World Factbook data I have given they closed the CIA World Factbook this year in February.

### What it delivers

A live Excel dashboard with a chokepoint dropdown, a per-ring breakdown, a weighted final score, and a ranked summary of all 18 chokepoints. Every score is traceable through Excel formulas back to the source data. Attached I have included the datasets I used. 

### What it does not do

It does not predict specific events. It measures the conditions of a structure that makes a chokepoint vulnerable to disruption. Live incident monitoring is what commercial platforms do on top of this analytical layer. 

### Python As a Secondary

In order to pull the data together from various datasets into the Excel document, I had to use Python to automate the process of pulling specific data from downloaded datasets into the workbook. ERA5 had the most amount of data but that is why it is important to understand the structure of the columns and rows of the target dataset before automation. You can use VBA to pull data from different sources as well but stick with what you find most comfortable. Do not use AI to pull the data. It's not that hard to use Python and add the proper values to automate the process. The formulas can get long but it's easier to write down the sheets and specific columns/rows you want to pull from with IF statements. The data for ACLED is more so manually as the most recent data from the monthly dataset is a bit far back. 

### Full write-up

On LinkedIn I made an article about this project more in-depth. 
### Sources 
Note: All datasets accessed and downloaded on 3 July 2026 for this project.

##### GOVERNANCE & CORRUPTION

- Transparency International: Corruption Perceptions Index 2025
  https://worldpopulationreview.com/country-rankings/corruption-perceptions-index-by-country

- EIU: Democracy Index 2026
  https://worldpopulationreview.com/country-rankings/democracy-index-by-country

- Cato Institute: Human Freedom Index 2026
  https://worldpopulationreview.com/country-rankings/freedom-index-by-country

- World Justice Project: Rule of Law Index 2026
  https://worldpopulationreview.com/country-rankings/world-justice-project-(wjp)-rule-of-law-index

##### ECONOMIC STRENGTH

- IMF: GDP per Capita 2026
  https://worldpopulationreview.com/country-rankings/gdp-per-capita-by-country

- WorldPopulationReview: Inflation Rate 2026
  https://worldpopulationreview.com/country-rankings/inflation-rate-by-country

- WorldPopulationReview: Unemployment Rate 2026
  https://worldpopulationreview.com/country-rankings/unemployment-by-country

- WorldPopulationReview: Debt-to-GDP Ratio 2026
  https://worldpopulationreview.com/country-rankings/debt-to-gdp-ratio-by-country

##### SECURITY

- Vision of Humanity: Global Peace Index 2026
  https://worldpopulationreview.com/country-rankings/safest-countries-in-the-world

- Vision of Humanity: Global Terrorism Index 2026
  https://worldpopulationreview.com/country-rankings/global-terrorism-index-by-country

- WorldPopulationReview: Military Spending % GDP 2026
  https://worldpopulationreview.com/country-rankings/military-spending-by-country

- ACLED: Political Violence Events, Fatalities, Civilian Targeting 2023-2025
  Download: https://acleddata.com/data-export-tool/
  Live pull (acled_batch.py): https://apps.acleddata.com/newexplorer/standard/

##### POLITICAL STABILITY

- World Bank: Political Stability Percentile Rank 2026
  https://worldpopulationreview.com/country-rankings/political-stability-by-country

- Fund for Peace: Fragile States Index 2023
  https://fragilestatesindex.org/excel/

##### INFRASTRUCTURE & COUNTRY REFERENCE

- CIA World Factbook (final version January 2026)
  Original site sunset February 4, 2026.
  I had previously web scraped the full Factbook using VBA before the shutdown.
  Archived versions available via:
  Internet Archive: https://web.archive.org/web/2026*/https://www.cia.gov/the-world-factbook/
  OpenFactBook (community rebuild): https://openfactbook.org/

##### ENVIRONMENTAL LAYER

- ECMWF Copernicus: ERA5 Wave Height + Wind Speed 2023-2026
  https://cds.climate.copernicus.eu/datasets/reanalysis-era5-single-levels-monthly-means
  Requires free CDS account. Select: significant wave height,
  10m u/v wind components, monthly means, NetCDF format.

- IMF PortWatch: Chokepoint Vessel Transit Counts
  https://portwatch.imf.org/datasets/

- HyperVolatility: Strait Width, Depth, Lane Counts
  https://hypervolatility.com/maritime-chokepoints/
