# Correlation Analysis: Political Climate and Bonds Yield

This project analyzes the correlation between political climate (as measured through Twitter sentiment) and UK government bond yields during October 2022.

## Project Overview

The analysis focuses on understanding the relationship between:
- Twitter sentiment from British users
- UK sovereign debt prices
- Political climate indicators

## Data Sources

The project uses three main data sources:
1. Twitter data from October 2022 (split across 6 CSV files)
2. UK government bonds data
3. User information data

## Technical Requirements

The project requires the following Python libraries:
- pandas
- numpy
- matplotlib
- seaborn
- textblob
- nltk
- statsmodels
- scikit-learn

## Setup Instructions

1. Install required Python packages:
```bash
pip install pandas numpy matplotlib seaborn textblob nltk statsmodels scikit-learn
```

2. Download NLTK resources:
```python
import nltk
nltk.download('stopwords')
nltk.download('punkt_tab')
```

3. Place the following data files in your working directory:
- bonds.csv
- chunk_00000.csv.gz through chunk_00005.csv.gz
- info_users.csv

## Analysis Steps

1. Data Loading and Preprocessing
   - Loading government bonds data
   - Loading and combining Twitter data chunks
   - Loading user information

2. Data Exploration
   - Initial data preview
   - Data cleaning and transformation
   - Sentiment analysis of Twitter data

3. Correlation Analysis
   - Statistical analysis of relationships
   - Visualization of correlations
   - Interpretation of results

## Notebook Structure

The analysis is documented in `Correlation_BondsYield_and_Political_climate.ipynb`, which includes:
- Data import and preprocessing
- Exploratory data analysis
- Sentiment analysis
- Correlation calculations
- Visualization of results

## Results

The analysis revealed several key findings:

1. **Data Processing and Handling Missing Values**:
   - Identified and addressed NaN values in the dataset
   - Implemented forward-fill method to handle missing values
   - Rationale for forward-fill approach:
     - Tweet volume remains substantial during weekends
     - Bond trends are relatively smooth
     - Weekend sentiment data shows significant relation to market movements
     - Preserves temporal sequence reflecting actual information available to market participants

2. **Sentiment Analysis and Data Integration**:
   - Successfully processed and combined Twitter data
   - Implemented sentiment scoring system
   - Created daily sentiment aggregates
   - Integrated sentiment scores with bond yield data

3. **Linear Regression Analysis**:
   - Model successfully fitted with sentiment scores as predictor (X) and bond yields as target (y)
   - Key findings from the regression analysis:
     - Regression coefficient: -5.01057341
     - Intercept: 4.31725049
     - Negative correlation confirmed between public climate and bond yields

4. **Key Insights**:
   - For every unit increase in sentiment score (towards political stability), the 10-year bond yield decreases by approximately 5.01 units
   - The intercept value of 4.31725049 represents the expected bond yield when sentiment is neutral
   - The negative correlation suggests that improved political climate sentiment is associated with lower bond yields
   - The model provides a quantitative measure of the relationship between political sentiment and market behavior

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Data sources: Twitter API and UK government bond data
- Libraries: pandas, numpy, matplotlib, seaborn, textblob, nltk, statsmodels, scikit-learn
