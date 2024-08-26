# Strenght of Concrete Prediction
This problem was originally proposed by Prof. I-Cheng Yeh, Department of Information Management Chung-Hua University, Hsin Chu, Taiwan in 2007. It is related to his research in 1998 about how to predict compression strength in a concrete structure.

The conventional process of testing the compressive strength of concrete involves casting several cubes for the respective grade and observing the strength of the concrete over a period of time ranging from 7 to 28 days.

Various combinations of the components of concrete are selected and cubes for each combination is casted and its test strength at 7, 14 and 28 days is noted dow. This is a time consuming and rather tedious process.

This project aims to predict the compressive strength of concrete with maximum accuracy and lowest error (evaluation metrics MAE) , for various quantities of constituent components as the input. The conrete cube exhibits behavioral differences in their compressive strengths for cubes that are cured/not cured. Curing is the process of maintaining the moisture to ensure uninterrupted hydration of concrete.

The concrete strength increases if the concrete cubes are cured periodically. The rate of increase in strength is described here.

Time % Of Total Strength Achieved [1] [2]

* 1 day 16%
* 3 days 40%
* 7 days 65%
* 14 days 90%
* 28 days 99%

At 28 days, concrete achieves 99% of the strength. Thus usual measurements of strength are taken at 28 days[1] 

The goals of this case are:

1. The average strength of the concrete samples at 1, 7, 14, and 28 days of age.
2. The coefficients of regression model using the formula that provided us:

$$ Concrete \ Strength = \beta_{0} \ + \ \beta_{1}*cement \ + \ \beta_{2}*slag \ + \ \beta_{3}*fly \ ash  \ + \ \beta_{4}*water \ + $$ 
$$ \beta_{5}*superplasticizer \ + \ \beta_{6}*coarse \ aggregate \ + \ \beta_{7}*fine \ aggregate \ + \ \beta_{8}*age $$
