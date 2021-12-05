# MechaCar Statistical Analysis

## Overview

The purpose of this analysis is to analyze some data on the MechaCar's production to help the manufacturing team. I am using two datsets containing information related to the miles per gallon and the suspension coils of the MechaCar. I used R in RStudio and the dplyr library to run statistical analysis on the datasets.

## Linear Regression to Predict MPG

In order to identify variables that have a significant effect on MPG, I used the miles per gallon dataset. I then preformed a multiple linear regression to see if it could predict the miles per gallon (mpg) dependent variable by using the vehicle length, vehicle weight, spoiler angle, ground clearance, and all wheel drive (AWD) independent variables. 

### Miles Per Gallon Linear Regression

![liner_reg_summary](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/liner_reg_summary.png)

- According to our results, vehicle length and ground clearance (as well as intercept) are statistically unlikely to provide random amounts of variance to the linear model. In other words the vehicle length and ground clearance have a significant impact on mpg.
- In addition, the p-value of our linear regression analysis is 5.35e-11, which is much smaller than our assumed significance level of 0.05%. Therefore, we can state that there is sufficient evidence to reject our null hypothesis, which means that the slope of our linear model is not zero.
- R-squared of approximately 0.71. This indicates that the multiple linear regression will predict 71% of mpg observations.

## Summary Statistics on Suspension Coils

In this section, I loaded in the suspension coils dataset. It was comprised of 150 different vehicles ID, 3 different lot numbers, and corresponding PSI levels for each vehicle. From there I created two summary tables to look at the mean, median, variance, and standard deviation of data. The first table looked at of the data as a whole, while the second table looked specific at each of the three different lots that the MechaCars were divided into. Here are the two tables.
By completing this analysis I want to answer one question:

### Total Summary Table

![total_sum_table](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/total_sum_table.png)

### Lot Summary Table

![lot_sum_table](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/lot_sum_table.png)

Looking at the total summary, the current variance is approximately 76.23 PSI meaning that is does meet the design specification. When looking at the lots individuals, the first two lotas meet the design specification at a varaince of approximately 1.14 PSI and 10.13 PSI respectfully, but the third lot does not. This is becasue the third lot's variance is approximately 220.01 PSI, exceeding the design specification by more than double the alotted amount. Therefore, the manufacturing team should work with the cars in lots 1 and 2 compared to those in lot 3.

## T-Tests on Suspension Coils

In this section, I wanted to determine if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 pounds per square inch. In order to do this, I used R's t.test() function to find four different p-values. The question that I wanted to answer by doing this was:

By using a significance level of 95%, meaning that 95% of the time this tests results would be true, I tested to see if any of the four groups had a statistical difference from the mean of 1,500 PSI. After running the tests, all four p-values where much greater than .05 meaning that I would fail to reject that there is a statistical difference between the four groups and the population mean.

Here is a breakdown of each of the four tests:

### All Manufacturing lots

![all_lots_t_test](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/all_lots_t_test.png)

### Lot 1

![lot_1_t_test](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/lot_1_t_test.png)

### Lot 2

![lot_2_t_test](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/lot_2_t_test.png)

### Lot 3

![lot_3_t_test](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/lot_3_t_test.png)


## Study Design: MechaCar vs Competition

In this section, I am comparing how the MechaCar performs with the competition. I am not preforming any tests in R, I am talking about how I would go about completing this analysis. In order to do this I want to answer four different questions which are:

What metric or metrics are you going to test?
What is the null hypothesis or alternative hypothesis?
What statistical test would you use to test the hypothesis? And why?
What data is needed to run the statistical test?
The answer to these questions are:

The metrics I want to test are city and highway fuel efficiencies.
Null Hypothesis is that all of the cars in the same class have the same fuel efficienies. THe Alternative Hypothesis is that they are not all the same.
I would use an ANOVA test to complete this analysis for both types of fuel efficiencies. Also I would use the ggplot2 library to show the potential spread between different cars using a boxplot.
I would need fuel efficiency data from 50 individual cars to create a sample size of data for each car in the class type. For example, if there was 10 cars in the class type, I would have a top of 500 data points collected for each fuel efficiency type.

