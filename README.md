# matplotlib-challenge

This challenge centers around the effectiveness of different drug regimens to treat the growth of tumors. I used Python to create and manipulate Pandas dataframes based on two CSV files (located in the Data folder), that track various datapoints for test subjects in clinical trials. I plotted the resulting outputs using both Pandas and Matplotlib.

## Data Preparation
I used Pandas to merge test result data with meta data regarding the test mice. This initial merge includes every timepoint measurement for every mouse -  making it the most comprehensive. However, as there were multiple test data entries per mouse, I also dropped duplicates to find 249 unique mouse ID's. 

## Summary Statistics
Using groupby on the Drug Regimen column, I calculated mean, median, variance, standard deviation, and SEM for the tumor volume for each treatment and created a dataframe. I was able to create a dataframe with the same statistics using aggregation.

## Bar and Pie Charts
I created bar charts representing the number of timepoints measured per mouse per drug regmin using Pandas as well as PyPlot. Then I created pie charts to view gender distribution of mice in the experiment using Pandas as well as PyPlot.

## Quartiles, Outliers, and Box Plot
I used groupby Mouse ID to get the maximum Timpoint per mouse. I reset the index of those results before performing an inner join (merge) with the comprehensive dataframe I'd created earlier on so that I would have all relevant datapoints for each mouse at their final timepoint. I then used .loc to extract only those mice in the top performing drug regimens: Capomulin, Ramicane, Infubinol, and Ceftamin.

I used a for-loop to gather final tumor volume data for each regimen and stored those values in a list. This list made it easy to create a box-and-whisker plot illustrating the distrubution of tumor volume for each treatment group. In addition to this qualitative method, I also calculated the IQR quantitatively using the 1.5xIQR rule. 

## Line and Scatter Plots
I used Pandas .loc to extract tumor volume over time on an individual mouse - Mouse ID 1509. This mouse was on the most effective drug regimen: Capomulin. Using Pandas plotting, I created a line plot to show the growth and decline in volume of the tumor over time. I used PyPlot to create a scatter plot comparing the weight of the test subject mice on Capomulin with their relative tumor volumes.

## Correlation and Regression
Using Pearson's r, I calculated the correlation coefficient between Capomulin-treated mouse weight and relative tumor size, which came to 0.53. I calculated the linear regression model for this data as well and plotted it over the existing Mouse Weight Vs. Tumor Volume scatterplot.
