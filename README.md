# An Examination of Food Insecurity and Food Deserts in the United States
This project is a comprehensive analysis of the issue of food access in the US. Current literature is reviewed and used to inform the methods used in our analysis. The main source of data on this subject is taken from the Food Access Research Atlas, provided by the USDA, with supplemental sources on the Supplemental Nutrition Assistance Program (SNAP) also taken from government sources. This data is cleaned and prepared, then explored through machine learning models such as random forest and logistic regression models, mapping with GeoPandas, statistical testing, and visualizations. Below are very brief summaries of our findings, but the pdf in this repository shows the full report.

### Important Conclusions from Literature
- 13.5% of the U.S. population is classified as food insecure.
- Trends of food insecurity in the U.S. show spikes during economic events like the Great Recession and COVID-19.
- The efficacy of SNAP has been called into question. There are maximum benefit amounts, yet no consideration for pricing differences across the country.
- The clearest gaps seen in current research are indications that using area-based data instead of looking at the needs of individual households is not ideal.

### Data Cleaning and Preparation
- The central dataset has 147 variables, so we utilized exploratory data analysis to narrow down the most important variables for our predictive models.
- Difficult values such as null values were identified and taken care of as necessary.
- Several instances of joining datasets were used in order to facilitate mapping with GIS data.
- For machine learning classification models, artificial resampling was required because of skewed representation of the minority class in the data.

### Mapping
- Nation-wide mapping shows the intersection of low food access and low vehicle access, indicating areas that are in the greatest need.
- Mapping of major cities shows clear visible correlations between certain demographics and low access areas.
- This city-wide mapping also shows patterns related to SNAP usage seen in current literature as well as showing new patterns such as the significance of vehicle access.

### An Examination of SNAP
- Our data visualizations show steep increases in program costs and benefits during times of financial hardship, but no increases in costs relating to research, education, or employment which may explain the many problems discussed in current literature.
- Our testing shows statistically significant increases in SNAP usage in these low access areas indicating that resources are being directed towards these areas of need.
- Other visualizations show that, while there are significant differences based on location, the need for SNAP benefits is seen in large numbers everywhere and only looking at this problem from a geographic viewpoint would be a mistake.
- A random forest regression model created to predict SNAP usage yielded an $R^{2}$ value of 0.71. The importance values of each variable in this model were then analyzed and the most significant predictors SNAP usage were a flag for low vehicle access and the population of children in the area.  
  
### Attempting to Predict Low-Access Areas
- We used several machine learning models to test how effective it is to predict the occurence of "food deserts", which in this dataset are the areas classified as low-income, low-access.
- Our K-Nearest Neighbors (KNN) model, hyperparameterized with a grid search cross validation, yielded an accuracy of 62.29%.
- A random forest classification model, again hyperparameterized with a grid search cross validation, yielded an accuracy of 85.54% with an area under the ROC curve of 0.93. Additionally, a plot of variable importance for this model showed that the most important predictive variables were median household income, poverty rate, and SNAP usage.
- Linear and logistic regression models created using the most important variables seen above yielded accuracies of 80.47% and 80.71%, respectively.
