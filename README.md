# Strength of Concrete Prediction
This problem was originally proposed by Prof. I-Cheng Yeh, Department of Information Management, Chung-Hua University, Hsin Chu, Taiwan, in 2007. It is related to his research in 1998 on how to predict compression strength in a concrete structure .

The conventional process of testing the compressive strength of concrete involves casting several cubes for the respective grade and observing the concrete's strength over 7 to 28 days.

Various combinations of concrete components are selected, cubes for each combination are cast, and its test strength at 7, 14, and 28 days is noted. This is a time-consuming and rather tedious process.

This project aims to predict the compressive strength of concrete with maximum accuracy and lowest error (evaluation metrics MAE) for various quantities of constituent components as the input. The concrete cube exhibits behavioral differences in its compressive strengths for cubes that are cured or not cured. Curing is maintaining moisture to ensure uninterrupted hydration of concrete.

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
2. The coefficients of the regression model using the formula provided to us:

$$ Concrete \ Strength = \beta_{0} \ + \ \beta_{1}*cement \ + \ \beta_{2}*slag \ + \ \beta_{3}*fly \ ash  \ + \ \beta_{4}*water \ + $$ 
$$ \beta_{5}*superplasticizer \ + \ \beta_{6}*coarse \ aggregate \ + \ \beta_{7}*fine \ aggregate \ + \ \beta_{8}*age $$

## Data Dictionary:
- "cement" - Portland cement in kg/m3
- "slag" - Blast furnace slag in kg/m3
- "fly_ash" - Fly ash in kg/m3
- "water" - Water in liters/m3
- "superplasticizer" - Superplasticizer additive in kg/m3
- "coarse_aggregate" - Coarse aggregate (gravel) in kg/m3
- "fine_aggregate" - Fine aggregate (sand) in kg/m3
- "age" - Age of the sample in days
- "strength" - Concrete compressive strength in megapascals (MPa).

***Acknowledgments**: I-Cheng Yeh, "Modeling of the strength of high-performance concrete using artificial neural networks," Cement and Concrete Research, Vol. 28, No. 12, pp. 1797-1808 (1998)*.

## Key Insights
- The dataset has 1030 entries, 9 columns, 2 types of variables(float & int), and is not normally distributed
- strength has a positive correlation with cement, superplasticizer, and age meaning when the values of cement, superplasticizer, and age increase, strength increases as well
- water has a  negative correlation with superplasticizer and aggregates meaning the more there is water the less there is superplasticizer and aggregates 
- superplasticizer has a positive correlation with fly_ash meaning the more superplasticizer the more fly_ash
- The strength on some days:
  - Day 1:  9.452715959999999
  - Day 7:  25.181843362178792
  - Day 14:  28.751037994193553
  - Day 28:  36.41040808733174
- Random Forest Regressor was the best model with a coefficient of determination(R²) of 90% and a Mean Absolute Error(MAE) of 3.7 meaning that, on average, the model's predictions deviate by 3.7 MPa from the actual strength.
- Age, cement, and water were the three features that contributed to the prediction.
  
## Recommendation
- Add More Data: The decreasing trend in validation error suggests that adding more data could improve the model’s performance.
