Lab 1: Data Visualization, Preprocessing, and Statistical Analysis
Purpose
The purpose of this lab is to explore the process of cleaning, visualizing, and performing statistical analysis on a real-world dataset using Python. This includes handling missing values, outlier detection and removal, data scaling, discretization, and correlation analysis. The lab is performed in a Jupyter Notebook or Google Colab environment, reinforcing practical skills for data mining and big data analysis.

Dataset
The dataset used is Mobile Phone Usage Statistics by country. It contains information such as country name, usage value (number of mobile phone users), date of information, ranking, and region.

Process and Key Steps
1. Data Loading and Initial Inspection
The CSV file was loaded using pandas.read_csv().

The dataset contained an encoding issue (Byte Order Mark, BOM) which was fixed by specifying encoding='utf-8-sig'.

Initial data was inspected with .head() and .info() to understand the structure.

2. Data Cleaning
The value column had numbers stored as strings with commas (e.g., "1,810,000,000"), so commas were removed and the column converted to numeric type.

Missing values were detected using .isnull().sum().

Missing value entries were filled with the median value to avoid bias from extreme values.

Rows missing the region value were dropped, as this information was critical for analysis.

3. Outlier Detection and Removal
Outliers were detected using the Interquartile Range (IQR) method.

Values outside 1.5 * IQR from Q1 and Q3 were considered outliers and removed to improve data quality.

4. Data Sampling and Reduction
To optimize processing, 80% of the cleaned data was sampled randomly for further analysis.

Less relevant columns such as slug were dropped to simplify the dataset.

5. Data Scaling and Discretization
The value column was scaled between 0 and 1 using Min-Max scaling to normalize the data.

The usage values were discretized into three categories: 'Low', 'Medium', and 'High' based on usage ranges, improving interpretability.

6. Data Visualization
Histograms were plotted to show the distribution of mobile phone usage.

Bar charts highlighted the top 10 countries by mobile phone usage.

Scatter plots showed the relationship between ranking and usage, colored by region.

7. Statistical Analysis
Summary statistics like mean, median, mode, range, variance, and standard deviation were calculated.

A correlation matrix heatmap was generated for numeric columns to identify relationships.

Key Insights
Countries such as China and India lead in mobile phone usage by a significant margin.

The distribution of usage values is skewed, and outlier removal helped create a more uniform dataset for analysis.

Scaling and discretization made it easier to interpret mobile phone usage levels categorically.

Some regions showed stronger correlations between ranking and usage than others.

Challenges Faced
The dataset included a BOM (Byte Order Mark) character in the header that initially caused column naming issues.

Mobile usage values were stored as strings with commas, requiring data cleaning before numerical operations.

Managing missing values and deciding on filling strategies vs. row removal required careful consideration.

Outlier detection required understanding IQR and ensuring that removal didn’t exclude valid data points.

Conclusion
This lab provided practical experience in cleaning messy real-world data, exploring it visually, and conducting basic statistical analysis. The steps taken to preprocess data significantly impact the quality and usefulness of insights generated through data mining.
