# MechaCar Statistical Analysis

## Overview

The purpose of this analysis is to analyze some data on the MechaCar's production to help the manufacturing team. I am using two datsets containing information related to the miles per gallon and the suspension coils of the MechaCar. I used R in RStudio and the dplyr library to run statistical analysis on the datasets.

## Linear Regression to Predict MPG

Using the miles per gallon dataset, I preformed a multiple linear regression to see if it could predict the miles per gallon (mpg) dependent variable by using the vehicle length, vehicle weight, spoiler angle, ground clearance, and all wheel drive (AWD) independent variables. 

#### Miles Per Gallon Linear Regression

![liner_reg_summary](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/liner_reg_summary.png)

- According to our results, vehicle length and ground clearance (as well as intercept) are statistically unlikely to provide random amounts of variance to the linear model. In other words the vehicle length and ground clearance have a significant impact on mpg.
- Additionally the p-value of our linear regression analysis is 5.35e-11, which is much smaller than our assumed significance level of 0.05%. Therefore, we can state that there is sufficient evidence to reject our null hypothesis, which means that the slope of our linear model is not zero.
- R-squared of approximately 0.71. This indicates that the multiple linear regression will predict 71% of mpg observations.

## Summary Statistics on Suspension Coils

The design specification for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch (PSI). We want to confirm that the manufacturing data meets this design specification for all manufacturing lots in total and each lot individually.

First I loaded then suspension coils dataset; comprised of 150 different vehicles ID, 3 different lot numbers, and corresponding PSI levels for each vehicle. Then I created two summary tables to look at the mean, median, variance, and standard deviation of data. The first table looked at of the data as a whole, while the second table looked specific at each of the three different lots that the MechaCars were divided into. Here are the two tables.

#### Total Summary Table

![total_sum_table](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/total_sum_table.png)

#### Lot Summary Table

![lot_sum_table](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/lot_sum_table.png)

Looking at the total summary table, the average variance across the lots is approximately 76.23 PSI meaning that is does meet the design specification. When looking at the lots individualy, lots 1 and 2 meet the design specification at a varaince of approximately 1.14 PSI and 10.13 PSI respectfully, but the third lot does not. Lot 3's variance is approximately 220.01 PSI, exceeding the design specification by more than double the alotted amount. 

Therefore, the manufacturing team should revisit its approach with vehicle allocation to these lots in order to normalize distributions or they could work with only the cars in lots 1 and 2 compared to those in lot 3.

## T-Tests on Suspension Coils

In this section, I wanted to determine if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 pounds per square inch. In order to do this, I used R's t.test() function to find four different p-values. Using a significance level of 0.05 percent

#### All Manufacturing lots

![all_lots_t_test](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/all_lots_t_test.png)

Looking at all lots, our p-value of 0.06 is above the significance level. Therefore, we do not have sufficient evidence to reject that there is a statistical difference between All Manufactuting lots and the population mean. The two means are statistically **similar**.

#### Lot 1

![lot_1_t_test](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/lot_1_t_test.png)

Looking lot 1, our p-value of 1.0 is above the significance level. Therefore, we do not have sufficient evidence to reject that there is a statistical difference between Lot 1 and the population mean. The two means are statistically **similar**.

#### Lot 2

![lot_2_t_test](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/lot_2_t_test.png)

Looking lot 2, our p-value of 0.61 is above the significance level. Therefore, we do not have sufficient evidence to reject that there is a statistical difference between Lot 2 and the population mean. The two means are statistically **similar**.

#### Lot 3

![lot_3_t_test](https://github.com/PSWil/MechaCar_Statistical_Analysis/blob/main/resources/lot_3_t_test.png)

Looking lot 3, our p-value of 0.042 is below the significance level. There is sufficient statistical evidence to reject that there is a statistical difference between Lot 3 and the population mean. The two means are statistically **different**.

## Study Design: MechaCar vs Competition

To ensure the new MechaCar prototype is a success, we should evaluate how it stands up to the competition. Lets design a potential study that will provide statistical insight to how the MechaCar performs vs competition.

#### Metrics
- I want to test both city and highway fuel efficiencies.

#### Hypothesis
- Null Hypothesis, MechaCar has similar fuel efficiency on the highway and in the city as other models. 
- Alternative Hypothesis, MechaCar does not have similar fuel efficiency on the highway and in the city as other models.

#### Statistical Tests
- I would use an ANOVA test to complete this analysis for both types of fuel efficiencies. Also I would use the ggplot2 library to show the potential spread between different cars using a boxplot.

#### Data
- In addition to the highway MPG and city MPG of MechaCar, I would need fuel efficiency data from at roughly 50 other models of cars to create a sample population that most accurately reflects the greater population.

