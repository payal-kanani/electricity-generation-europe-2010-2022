# Electricity Generation Analysis in Europe: 2010–2022

**Electricity Generation Analysis in Europe** A comprehensive data analytics and visualization project exploring and predicting monthly electricity production across European countries between 2010 and 2022.

![Cover photo] (../data/images/dataset-cover.jpg)

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


## The rationale to map the business requirements to the Data Visualisations
* List your business requirements and a rationale to map them to the Data Visualisations

## Analysis techniques used
* List the data analysis methods used and explain limitations or alternative approaches.
* How did you structure the data analysis techniques. Justify your response.
* Did the data limit you, and did you use an alternative approach to meet these challenges?
* How did you use generative AI tools to help with ideation, design thinking and code optimisation?

## Ethical considerations
* Were there any data privacy, bias or fairness issues with the data?
* How did you overcome any legal or societal issues?

## Dashboard Design
* List all dashboard pages and their content, either blocks of information or widgets, like buttons, checkboxes, images, or any other item that your dashboard library supports.
* Later, during the project development, you may revisit your dashboard plan to update a given feature (for example, at the beginning of the project you were confident you would use a given plot to display an insight but subsequently you used another plot type).
* How were data insights communicated to technical and non-technical audiences?
* Explain how the dashboard was designed to communicate complex data insights to different audiences. 

## Unfixed Bugs
* Please mention unfixed bugs and why they were not fixed. This section should include shortcomings of the frameworks or technologies used. Although time can be a significant variable to consider, paucity of time and difficulty understanding implementation are not valid reasons to leave bugs unfixed.
* Did you recognise gaps in your knowledge, and how did you address them?
* If applicable, include evidence of feedback received (from peers or instructors) and how it improved your approach or understanding.

## Development Roadmap
* What challenges did you face, and what strategies were used to overcome these challenges?
* What new skills or tools do you plan to learn next based on your project experience? 

## Deployment
### Heroku

* The App live link is: https://YOUR_APP_NAME.herokuapp.com/ 
* Set the runtime.txt Python version to a [Heroku-20](https://devcenter.heroku.com/articles/python-support#supported-runtimes) stack currently supported version.
* The project was deployed to Heroku using the following steps.

1. Log in to Heroku and create an App
2. From the Deploy tab, select GitHub as the deployment method.
3. Select your repository name and click Search. Once it is found, click Connect.
4. Select the branch you want to deploy, then click Deploy Branch.
5. The deployment process should happen smoothly if all deployment files are fully functional. Click now the button Open App on the top of the page to access your App.
6. If the slug size is too large then add large files not required for the app to the .slugignore file.


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


