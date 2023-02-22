## My tips on the data preparation for ML from data cleaning to splitting data

1. Observe the data:
  - Check the size of the data and make sure it's appropriate for the analysis.
  - Check for missing values and duplicate values in the data and handle them accordingly.
  - Use df.info() to identify the data types of each column in the dataset and determine if any data transformations will be needed.
  - Check for skewed data and determine if log transformation is needed to correct it.

2. Exploratory Data Analysis (EDA):
  - Use df.hist() to plot a histogram of the data and visually inspect the distribution of the variables.
  - Use a heatmap of sns.heatmap(df.corr()) to identify any correlations between variables.
  - Consider log transformation for any right-skewed data.
  - Feature Engineering:

3. Convert categorical variables into ordinal variables if necessary.
  - Add new columns of percentages or age if needed.
  - Combine columns if necessary to simplify the data.
  - Convert float to int if necessary using .astype(int).

4. Handle outliers:
  - Identify any data points that are significantly different from the others in the dataset.
  - Determine if these outliers should be removed or handled in a different way.

5. Feature selection:
  - Use the heatmap of df.corr() to identify any unnecessary features that can be removed from the data.
  - Log transformation to unskew the data
  
6. Prepare the data for modeling:
  - Split the data into training and testing sets.
  - Use the training data to build the model and the testing data to evaluate the performance of the model.
 
7. Feature Scaling - Normalization / Standardization:
  - Normalize or standardize the data after splitting it into training and testing sets.
  - Only use the training data to calculate the normalization or standardization parameters to avoid bias in the evaluation of the model.

    - The **fit(data)** method is used to compute the mean and std dev for a given feature to be used further for scaling. The fit function computes the formulation to transform the column based on **[Standard scaling](https://www.geeksforgeeks.org/data-pre-processing-wit-sklearn-using-standard-and-minmax-scaler/)** but doesn’t apply the actual transformation. The computation is stored as a fit object. The fit method doesn’t return anything.
    - The **transform(data)** method is used to perform scaling using mean and std dev calculated using the .fit() method. Using the transform method we can use the same mean and variance as it is calculated from our training data to transform our test data. The transform method takes advantage of the fit object in the fit() method and applies the actual transformation onto the column.
    - The **fit_transform()** method does both fits and transform.
