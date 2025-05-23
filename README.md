# solar-challenge-week1
Strategic Solar Insights for Sustainable Growth 


Business Objective
MoonLight Energy Solutions is dedicated to driving forward clean energy initiatives through smart investments in solar technology. To support our long-term sustainability goals, we launched a data-driven project to evaluate environmental conditions across multiple regions and pinpoint the most promising locations for solar installations. As the Analytics Engineer on this project, my role was to lead the end-to-end analysis, from collecting and cleaning the raw data to performing exploratory analysis and building interactive dashboards. The goal was to uncover meaningful insights from solar-related environmental metrics and translate them into a clear, actionable strategy for solar investment.

1. Project Setup and Environment Configuration
We began by establishing a well-structured codebase:
Project Structure
solar-challenge-week1/
├── .github/         # CI workflows
├── .vscode/         # Editor settings
├── app/             # Streamlit dashboard
├── data/            # Cleaned CSVs (excluded from git)
├── notebooks/       # EDA notebooks
├── scripts/         # Python scripts
├── tests/           # Test utilities
├── .gitignore
├── requirements.txt
└── README.md

We created and activated a virtual environment using Python and managed dependencies via requirements.txt. Our .gitignore was carefully crafted to prevent committing large or sensitive files (like CSVs).
2. Data Profiling, Cleaning & EDA
We received raw CSV files containing hourly environmental data for Benin, Sierra Leone, and Togo. Each country had its notebook (<country>_eda.ipynb) and followed a structured workflow:
Steps Performed:
Summary Statistics
 Used .describe() and .isna().sum() to assess the distribution and missing data across key metrics like:


GHI (Global Horizontal Irradiance)


DNI (Direct Normal Irradiance)


DHI (Diffuse Horizontal Irradiance)


Wind Speed (WS), Gust (WSgust), and Temperature (Tamb)


Missing Value & Outlier Detection


Identified columns with >5% nulls.


Used Z-scores to detect outliers in core columns.


Cleaned data via imputation (median) or row removal.


Visual EDA


Time series plots to show daily and monthly irradiance trends.


Heatmaps to show correlations between variables.


Wind roses and bubble plots to illustrate directional wind speed and combined metrics like RH vs. GHI.


Cleaned Output


Final cleaned files were saved as data/<country>_clean.csv.


3. Cross-Country Comparison
To synthesize insights across regions, we created compare_countries.ipynb:
Key Deliverables:
Boxplots comparing GHI, DNI, and DHI across the three countries.


Summary Table of mean, median, and standard deviation.


Statistical Test: One-way ANOVA was used to test whether GHI differences between countries were statistically significant.


Visual Insights: Bar charts highlighted the top performers for average irradiance.


 Key Insight:
 Benin consistently showed high median GHI values with relatively low variance—making it a strong candidate for investment. Sierra Leone followed closely but had more fluctuations.
4. Interactive Dashboard (Not done fully)
To empower decision-makers with real-time insights, we built a Streamlit dashboard.
 Dashboard Features:
Country selector widget
Boxplots and trends for GHI, DNI, and DHI
Summary metrics table
Clean and professional UI for easy navigation
Folder: /app/main.py
We also added utility functions (utils.py) for reusability and separation of concerns.
Deployment Plan
Though optional, we structured the app to be deployable to Streamlit Community Cloud. This makes it easy for MoonLight’s leadership to interact with the data without needing technical tools.
Recommendation
Based on our detailed analysis and interactive visualizations, we recommend:
Top Region for Solar Investment:
Benin (Malanville) – High and stable GHI values, strong correlation with temperature and humidity, minimal sensor noise.
Strategic Actions:
Prioritize solar installations in Benin with phased deployment in Sierra Leone.


Set up real-time monitoring dashboards using Streamlit for ongoing evaluation.


Continue data acquisition across seasons to validate long-term trends.
Conclusion 
When processed and visualized thoughtfully, this project highlights how environmental data can provide powerful strategic insights for sustainable energy planning. MoonLight Energy Solutions is now equipped with data and direction to make impactful solar investments.
