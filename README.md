# heart-disease-prediction
My final project for Comp Sci 320

  Heart disease becomes one of the leading factors of human death in the United States, and the
number of Americans who die from heart disease is up to 655,000 persons per year (Heart Disease Facts,
2020, p.1). It is worthy to talk about heart disease, so we can then find a way to treat it. Our goal in this
project is to understand the age effect on heart disease and find the most related quantitative health
indicator to indicate the presence of heart disease. It will help researchers to well focus on some specific
parts of the body and treat this kind of disease effectively.
  The dataset is from https://archive.ics.uci.edu/ml/datasets/Heart+Disease at the University of
California Irvine, but I get it from https://query.data.world/s/tvlbtu4hlweclxx5cxdzvjposlsmmu. The size
of the dataset is 270 rows × 14 columns, and the data is collected from 270 patients with or without heart
disease. It contains 13 independent predictive variables or column attributes.
  I select seven features for my analysis to investigate the relationship with heart disease: (1) Age,
(2) Sex, (3) BP, which means blood pressure, (4) Cholesterol, (5) Max HR, (6) ST depression, (7) Heart
Disease (previously happened). ST depression is often a sign of myocardial ischemia, of which coronary
insufficiency is a major cause.
  I also add both “pc1” and “predicted_result” two columns. The “pc1” combines BP, Cholesterol,
Max HR as the single most important principle component. The “predicted_result” is a prediction of heart
disease based on these five factors (including Age, BP, Cholesterol, Max HR, and ST depression).
  In Figure One, we can see how people with the presence of heart disease are related to age and
sex. The first figure has an age value on the x-axis and the percentage of people with heart disease on the
y-axis. The blue line in the figure means the percentage of males with heart disease, while the red line is
related to the percentage of females with heart disease. It presents the distribution of heart disease in
different ages and sex. It can easily show the effect of both age and sex on heart disease.
  For Figure Two, this graph is a PCA plot that plots the first components of the PCA transformed
data and ST depression. The first component contains BP, Cholesterol, and Max HR. I add one more
column, which is named “pc1”. There are BP, Cholesterol, and Max HR columns that all vary together,
and I intend to find out whether there is a positive relationship between the first component and “ST
depression”. I also divide those data into males and females in order to see whether ST depression can be
affected by sex or three health indicators, including BP, Cholesterol, and Max HR. There is no clear
division on the difference of sex, which means that there is no relationship with a different sex. The plot
shows the slightly positive relationship between the first principal component and St depression. After I
counted the explained_variance_ratio of PCA, it got 0.76, which means that this PCA is capturing a large
proportion of the covariance.
  Figure Three shows the coefficient weights for each of the features used by the regression
model. I use logistic regression to predict whether the patient will encounter a heart disease or not based
on their current health situation. The score of this logistic regression model is 0.6764705882352942,
which means that approximately 67.65% variance can be explained by the model. After adding
StandardScaler() to my model, the score remains unchanged but the coefficient of the model can be
standardized. StandardScaler() means standardizing features by removing the mean and scaling to unit
variance. We can clearly see that the most important factor for predicting whether heart disease will occur
is the value of ST depression, while the Max HR shows the greatest negative weight (about -0.62369246)
on a prediction of heart disease. The higher the ST depression is, the more likely the heart disease will
happen. This plot shows weight for different health indicators, and we can say that Age is the least likely
factor (weight -0.04446253) for predicting heart disease.
  In conclusion, my logistic regression model can be used to predict whether heart disease will
happen based on different health indicators of patients. We can learn the effects of each different feature
through figures. ST depression is the most significant indicator for whether heart disease will happen or
not. Overall, the analysis of those independent predictive variables can provide a more accurate way for
researchers to treat heart disease and avoid becoming more severe
