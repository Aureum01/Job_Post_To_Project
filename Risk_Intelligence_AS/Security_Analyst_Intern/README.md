### Maritime Chokepoint Risk Monitor

An Excel-based structural risk monitor covering all 18 major global maritime chokepoints. Built as the first project in the Job Post to Project series, in response to a Security Analyst intern role at Risk Intelligence A/S in Denmark.

### What it does

Scores each of the 18 chokepoints on a 0 to 100 risk scale using a three-ring model. Ring 1 covers the countries that physically control the chokepoint. Ring 2 covers the surrounding countries. Ring 3 covers outside powers that pressure Rings 1 and 2. An environmental layer scores geography, weather, and bypass availability on top.

Each of the 65 countries in the model gets a country risk score built from six pillars: Governance and Corruption, Economic Strength, Security Environment, Political Stability, External Influence, and Infrastructure. The pillar scores are averaged with adjustable weights in 00_Config.

### What it uses

All public data. No paid APIs. Nineteen source files across thirteen organizations including Transparency International, the IMF, the World Bank, Vision of Humanity, the Fund for Peace, ACLED (manual on my end but has a public dataset), ECMWF Copernicus, IMF PortWatch, and the CIA World Factbook.

### What it delivers

A live Excel dashboard with a chokepoint dropdown, a per-ring breakdown, a weighted final score, and a ranked summary of all 18 chokepoints. Every score is traceable through Excel formulas back to the source data. Attached I have included the datasets I used. 

### What it does not do

It does not predict specific events. It measures the conditions of a structure that makes a chokepoint vulnerable to disruption. Live incident monitoring is what commercial platforms do on top of this analytical layer. 

### Python As a Secondary

In order to pull the data together from various datasets into the Excel document, I had to use Python to automate the process of pulling specific data from downloaded datasets into the workbook. ERA5 had the most amount of data but that is why it is important to understand the structure of the columns and rows of the target dataset before automation. You can use VBA to pull data from different sources as well but stick with what you find most comfortable. Do not use AI to pull the data. It's not that hard to use Python and add the proper values to automate the process. The formulas can get long but it's easier to write down the sheets and specific columns/rows you want to pull from with IF statements. The data for ACLED is more so manually as the most recent data from the monthly dataset is a bit far back. 

## Full write-up

See the accompanying article on LinkedIn for the full methodology and the case study on why Bab el-Mandeb ranked first and the Strait of Hormuz ranked sixth despite the current crisis.
