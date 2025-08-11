# Electricity Generation Analysis in Europe: 2010–2022

**Electricity Generation Analysis in Europe** A comprehensive data analytics and visualization project exploring and predicting monthly electricity production across European countries between 2010 and 2022.

## Dataset Content
* The cleaned dataset contains 107726 monthly records of electricity generation (in GWh) across European countries from 2010 to 2022, broken down by energy source (Hydro, Wind, Solar, etc.). 
* It includes:
    - Country: Austria, Belgium, Bulgaria, Croatia, Cyprus, Czech Republic, Denmark, Estonia, Finland, France, Germany, Greece, Hungary, Iceland, Ireland, Italy, Latvia, Lithuania, Luxembourg, Malta, Netherlands, North Macedonia, Norway, Poland, Portugal, Republic of Turkiye, Romania, Serbia, Slovak Republic, Slovenia, Spain, Sweden, Switzerland, United Kingdom.
    - Year, Month, Date : time componenets
    - Products(Type of electricity generation) : Hydro, Wind, Solar, Geothermal, Other renewables, Nuclear, Total combustible fuels, Coal, Oil, Natural gas, Combustible renewables, Other combustible non-renewables, Not specified, Net electricity production, Total imports, Total exports, Electricity supplied, Used for pumped storage, Distribution losses, Final consumption, Electricity trade, Renewables, Non-renewables, Others, Other renewables aggregated, Low carbon, Fossil fuels.
    - Values: The amount of electricity generated in gigawatt-hours (GWh)
    - yearToDate: The amount of electricity generated for the current year up to the current month in GWh
    - previousYearToDate: The amount of electricity generated for the previous year up to the current month in GWh
    - share: The share of the product in the total electricity generation for the country in decimal format

**Note**: Dataset was filtered to include only European countries.

## Business Requirements
- Identify and visualize energy production trends across Europe from 2010 to 2022.
- Provide insights into the shift from fossil fuels to renewable sources.
- predict when will renewables surpass non-renewables in Europe
- Predict electricity production for a given country, month, and energy source.
- Group countries by energy behaviour using unsupervised learning.

## Hypotheses and Validation
- Renewable energy production has increased significantly in Europe since 2010.
    - Validation: Year-wise trend analysis for Wind, Solar, Hydro energy.
- Renewable sources like wind and solar show an upward trend over the years.
    - Validation: Line plots and trend analysis of Wind and Solar electricity generation over time.
- Electricity production can be predicted based on time, country, and product type.
    - Validation: Regression modeling (e.g., Random Forest Regressor).

## Handling Negative Values
- ‘Electricity trade’ and ‘Oil’ are the only two products showing negative values.
- These negative values appear in:
    - value (monthly GWh generation)
    - yeartodate
    - previousyeartodate
    - share
- Negative values in 'Electricity trade' represents import/export flows, and negative values likely indicate net electricity exports (more electricity sent out than received).
- Negative values in 'Oil' are likely due to data reporting errors or inconsistencies, as negative electricity generation is not logically valid in this context. After considering domain knowledge and consulting with an industry expert, we decided to remove rows where the product is 'Oil' and any of the above columns contain negative values.

## Outlier Handling
- During data exploration, outliers were detected in value, yeartodate, previousyeartodate, share columns. After careful consideration, outliers were retained in the dataset.
- The dataset represents real-world electricity generation data across European countries.
- Outliers in this context are often a result of:
    - Seasonal peaks in production or demand
    - Sudden policy changes
    - Cross-border electricity trade or import/export anomalies
- These data points are not errors, but rather valuable indicators of unique events and trends.
- Removing them would risk hiding meaningful insights that could improve the quality of the analysis.




