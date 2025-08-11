# Electricity Generation Analysis in Europe: 2010–2022

**Electricity Generation Analysis in Europe** A comprehensive data analytics and visualization project exploring and predicting monthly electricity production across European countries between 2010 and 2022.

![Dataset Cover](data/images/dataset-cover.jpg)

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

## Hypotheses and Validation
- Renewable energy production has increased significantly in Europe since 2010.
    - Validation: This was tested through year-wise trend analyses focusing on Wind, Solar, and Hydro energy generation.
- Renewable sources show an upward trend over the years.
    - Validation: Line plots and detailed trend analyses of renewable source
- Electricity production can be predicted based on time, country, and product type.
    - Validation: A Random Forest machine learning model was developed and tested to predict electricity production using these features.
- Renewable electricity generation will surpass non-renewable generation in Europe within the coming years.
    - Validation: Linear and polynomial regression models were applied to historical aggregated data to forecast the crossover year when renewables exceed non-renewables.

## Project Plan
* High-Level Steps for the Analysis
1. Data Collection:
    * The dataset used in this project was sourced from Kaggle, a reputable platform that hosts a wide range of open datasets contributed by the data science community. 
    * This particular dataset was chosen because it contains comprehensive and relevant information related electricity generation over time 2010 to 2022.
    *  The dataset was downloaded in CSV format.

2. Data Processing and Cleaning:
    * After downloading the dataset, I performed several cleaning and preprocessing steps to prepare the data for analysis.
        * Unnecessary and redundant columns were dropped, and remaining columns were renamed for improved readability and consistency.
        * Filter the dataset to include only European countries based on a predefined list. 
        * The separate year and month columns were combined into a single datetime column to facilitate time series analysis.
        * Any missing values (NaNs) in the dataset were filled with zeros to maintain data completeness.
        * Negative values were carefully addressed, while invalid negatives were corrected or handled, negative values in electricity trade rows were retained as they represent exports and have meaningful interpretations.
        * The dataset was checked for potential outliers to ensure data quality and reliability.
    * After these cleaning steps, the processed dataset was saved as 'cleaned_european_countries_dataset.csv'. 
    * This cleaned dataset, with its standardized columns and properly formatted date column, is now ready for exploratory data analysis and modeling.

3. Exploratory Data Analysis (EDA)
    * This phase involved thorough analysis of the cleaned electricity generation dataset (2010–2022) for European countries using Python libraries such as pandas, numpy, matplotlib, seaborn, and plotly.
        * Performed descriptive statistics to summarize central tendencies and dispersion of key variables. 
        * Visualized total electricity generation trends over time with line charts and compared the top 5 energy sources using multi-line plots.
        * Conducted a detailed comparison of renewable versus non-renewable electricity generation through stacked and grouped bar charts.
        * Analyzed trends within renewable sources (solar, wind, hydro) to understand their growth patterns.
        * Generated bar charts showing total generation by country to highlight regional contributions.
        * Computed correlation matrices to investigate relationships among variables like generation values and year to date metrics.
        * Preserved error bars in visualizations to represent data variability and confidence intervals.
        * Manually curated renewable classifications for accuracy in analysis.
    * The insights obtained through EDA laid the groundwork for predictive modeling and powered an interactive Power BI dashboard for stakeholder decision-making.

4. Modeling and Prediction:
    * In this project, various statistical and machine learning models were applied to analyze energy production data and forecast future trends.
    * Specifically, linear and polynomial regression models were used to model the growth of renewable and non renewable electricity generation and predict the crossover year when renewables surpass non-renewables.
    
5. Dashboard Design:
    * Developed interactive dashboards using Power BI to visualize key insights, trends, allowing stakeholders to explore the data dynamically.

* Data Management Throughout the Project
    * Data from Kaggle was imported and stored in CSV format and processed primarily in Python using pandas and numpy.
    * Data cleaning and preprocessing were scripted for reproducibility and automation.
    * Visualizations were created iteratively during EDA using matplotlib, seaborn, and plotly.
    * Models were developed and evaluated within Jupyter notebooks for clarity and version control.
    * Power BI was used to design dashboards that integrate the processed data and model outputs, providing a user friendly interface for stakeholders.

* Choice of Research Methodologies
    * Exploratory Data Analysis (EDA):
        * Employed to understand data distributions, identify trends, and detect anomalies. Visual tools helped in forming hypotheses about renewable energy growth patterns.

    * Regression Models (Linear and Polynomial):
        * Chosen to model time-based trends in energy production. Linear regression captures straightforward growth, while polynomial regression handles potential nonlinear growth patterns.

    * Random Forest Regression:
        * Implemented to capture complex, nonlinear relationships in the data that simpler regression models might miss, potentially improving forecast accuracy.

    * Interactive Dashboarding (Power BI):
        * Used to communicate results effectively to stakeholders through dynamic and intuitive visualizations.


## Mapping Business Requirements to Visuals

| Business Requirement                                                            | Visualization / Technique                                            |
|---------------------------------------------------------------------------------|----------------------------------------------------------------------|
| Identify and visualize energy production trends across Europe from 2010 to 2022 | Line plots, stacked area/bar charts                                  |
| Provide insights into the shift from fossil fuels to renewable sources          | Stacked bar charts, area charts                                      |
| Predict when renewables will surpass non-renewables in Europe                   | Regression models (Linear, Polynomial regression)                    |
| Predict electricity production for a given country, month, and energy source    | Random Forest regression model                                       |

## Analysis techniques used
* Exploratory Data Analysis (EDA): 
    * Used descriptive statistics and visualizations (line plots, bar charts, area charts) to understand energy production trends and shifts over time.
    * Limitations: EDA is descriptive and does not provide predictive insights or causal inference.
* Regression Models (Linear and Polynomial): 
    * Applied to model and forecast renewable energy trends, capturing linear and nonlinear growth patterns.
    * Limitations: These models assume certain relationships and may not handle complex interactions or external factors influencing energy production.
* Random Forest Regression: 
    * Employed for detailed predictions of electricity production by country, month, and energy source, capturing nonlinearities and feature interactions.
    * Limitations: Can be computationally intensive and less interpretable compared to simpler regression models.
* How did you use generative AI tools to help with ideation, design thinking and code optimisation?

* Structure and Justification of Techniques
    * The analysis was structured progressively: 
        * beginning with EDA to explore and understand data patterns, followed by regression models to forecast overall trends, and finally using Random Forest for granular, accurate predictions. 
        * This approach ensured both interpretability and predictive power, balancing simplicity and complexity appropriately.

* Data Limitations and Alternative Approaches
    * Data limitations included sparsity in monthly data for some countries and occasional missing values. 
    * To address this, aggregation to yearly levels was performed where appropriate, and model complexity was adjusted to prevent overfitting. 
    * Missing data was handled via imputation to maintain data quality.

* Use of Generative AI Tools
    * Generative AI tools assisted by suggesting analysis approaches, generating code snippets for data cleaning, visualization, and modeling, and optimizing code efficiency. 
    * They supported design thinking by offering alternative perspectives and helped accelerate development while ensuring best coding practices.


## Ethical considerations
* Data Privacy, Bias, and Fairness
    * The dataset used contains aggregated energy production data at the country and year level, which does not involve any personal or sensitive information, thereby minimizing data privacy concerns. 
    * However, potential biases could arise from uneven data quality or coverage across different countries and time periods, which might affect model fairness and generalizability.
* Addressing Legal and Societal Issues
    * To mitigate bias and ensure fairness, data cleaning steps included careful handling of missing or incomplete data to avoid skewed results. 
    * All data sources used are publicly available and compliant with legal and ethical standards. 
    * Insights were communicated transparently to avoid misinterpretation or misuse. 
    * The project respects environmental and societal implications by focusing on promoting renewable energy awareness and supporting informed decision-making.

## Dashboard Design
**Note:**
You can access the electricity_production_pverview_in_europe_dashboard.pbix in the dashboard folder. Please download the file from this folder to view and interact with the dashboard.

#### Dashboard Pages and Content
* Cover Page:
    * This page features the dashboard title and key objectives. It also includes project Description.
* Electricity Generation Overview: 
    * This page provides a high-level summary of electricity production across Europe with the following visuals and interactive elements.
    * Map Visual: Displays total electricity generation by country, offering geographic insights into production distribution.
    * Column Chart: Shows total electricity generated by each country, allowing easy comparison.
    * Donut Chart: Represents the breakdown of total electricity generated by different energy types (renewable and non-renewable).
    * Cards:
        * Share of renewable energy as a percentage of total production.
        * Total electricity generated across all countries.
    * Year Slicer: Enables filtering data by year from 2010 to 2022, allowing users to explore trends over time interactively.

* Breakdown by Energy type: 
    * This page provides detailed insights into electricity production by energy source with the following visualizations and controls.
    * Stacked Column Chart: Visualizes the count of different energy types, showing the composition and contribution of each type.
    * Clustered Column Chart: Displays the total electricity generated by each product/energy source, enabling side-by-side comparison.
    * Slicers:
        * Country slicer to filter data by selected countries.
        * Year slicer to filter data by year, allowing users to focus on specific time periods.
    
* Trend over Time:
    * This page features a line chart showing the total electricity generated over time, broken down by electricity generation source.
    * Users can interactively filter the data using slicers for:
        * Year
        * Energy type
        * Country
    * This setup allows detailed exploration of how energy production trends have evolved across different sources and regions from 2010 to 2022.

* Year on Year Comparison: 
    * This page compares electricity generation performance across years with the following visualizations.
    * Clustered Column Chart: Displays total electricity generated over time, enabling comparison between different years.
    * Area Chart: Shows Year-to-Date (YTD) and Previous Year-to-Date electricity generation trends, making it easy to track annual changes and growth patterns.
    * Slicer: Country name slicer to filter and analyze the data for a specific country.

* Iterative Development and Feature Updates:
    * During development, some visualizations were refined based on user feedback and data exploration.

* Communication of Data Insights:
    * The dashboard was designed with both technical and non-technical audiences in mind. 
    * For technical users, detailed charts and statistical summaries provide in-depth analysis. 
    * For non-technical stakeholders, simplified visualizations, KPIs, and clear annotations highlight key messages. 
    * Interactive elements enable users to explore data at their own pace and according to their interest.

## Unfixed Bugs
* Granular Hourly or Daily Data Unavailable
    * Description: The dataset only contains annual electricity generation data, which limits the ability to analyze seasonal or monthly trends.
    * Reason Unfixed: This limitation comes from the source dataset, and no public API with historical hourly/daily breakdowns for all European countries was identified during this project.
* Knowledge Gaps Identified & Addressed
    * Predictive Modelling in Jupyter + Dashboard Integration: Learned how to export predictions from Python to CSV and then connect them to Power BI for visualization.
    * Predictive Modelling in Jupyter + Dashboard Integration: Learned how to export predictions from Python to CSV and then connect them to Power BI for visualization.



## Development Roadmap
* What challenges did you face, and what strategies were used to overcome these challenges?
* What new skills or tools do you plan to learn next based on your project experience? 


## Main Data Analysis Libraries
* Here you should list the libraries you used in the project and provide an example(s) of how you used these libraries.


## Credits 

* In this section, you need to reference where you got your content, media and extra help from. It is common practice to use code from other repositories and tutorials, however, it is important to be very specific about these sources to avoid plagiarism. 
* You can break the credits section up into Content and Media, depending on what you have included in your project. 

### Content 

- The text for the Home page was taken from Wikipedia Article A
- Instructions on how to implement form validation on the Sign-Up page was taken from [Specific YouTube Tutorial](https://www.youtube.com/)
- The icons in the footer were taken from [Font Awesome](https://fontawesome.com/)

### Media

- The photos used on the home and sign-up page are from This Open-Source site
- The images used for the gallery page were taken from this other open-source site



## Acknowledgements (optional)
* Thank the people who provided support through this project.


