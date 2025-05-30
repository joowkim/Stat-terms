# Stat terms
---------------  

### Estimated beta coefficient interpretation  
There is sufficient evidence at the 0.05 level to conclude that a predictor variable is statistically significant or is significantly related to the reponse variable.   
[reference: Penn State State501]


### Extrapolation  
beyond the "scopte of the model" when estimating a mean Uy or to predict a new response y_new for x values int in the range of the sample data  
[Penn State Stat501 lesson-12.8](https://online.stat.psu.edu/stat501/lesson/12/12.8)


### The CLT
The Central Limit Theorem of probability states that the sum of many small, independent RVs will be a RV that approximates what is called a *normal distribution*.  
[reference](Regression and Other Stories)


### P-value
The *p-value* gives us the probability that we don't have a representative sample; it is the probability of getting a test statistic as large or larger than what we actually observed if *H_0* were true.  
[reference](DOE lecture notes from KU)  

The probability of obtaining at least the same result under the null hypothesis.  
[reference](DOE lecture notes from KU)  


### Standard error  
The standard deviation of an estimate statistic
[reference](Regression and Other Stories)   


The standard error of the mean is a measure of the uncertainty of our estimate of the population mean. If the standard error is large, then we are less confident of our estimate of the mean. Conversely, if the standard error is small, then we are more confident in our estimate.  
[Penn State Stat501](https://online.stat.psu.edu/stat505/lesson/5/5.1)

When the standard deviation of a statistic (funcation of RV) is estimated from data, the result called the standard error of statistic.  
[reference](Basic practice of statistics - Moore 6th ed. p438 and https://youtu.be/kNHrOEavGuI)  

The standard error of the some estimated beta coefficient 0.1521, tells us the estimated standard deviation of the sample slope from one sample to another.  

In repeated sampling, our calculated slope based on a random sample will vary from one sample to another. A typical difference between the calculated sample slope and the population slope is estimated to be 0.1521 (estimated beta coefficient is 1.1667 and std error 0.1521)  
[reference](Texas A&M lecture notes)  


### Interpretation of regression coefficients  
The safest interpretation of a regression is as a comparison For example   
 1. earnings = -26 + 0.6 x height + 10.6 x male + error  
   1.1. Comparing two people with the same height but different sex, the man's earnings will be, on average, $10,600 more than the woman's in the fitted model.  
 2. kid_score = 26 + 0.6 x mom_iq + error  
   2.1. between groups of children whose mothers' IQ differed by 10 points-these childeren would be expected to have scores that differed by 6 points on average.  
   2.2. Differing in maternal IQ by 1 point  we expect to see that the group with higer maternal IQ achieves 0.6 points more on average.  
 3. kids_score = 26 + 6 x mom_hs + 0.6 x mom_iq + error  
   3.1. The coefficient of maternal high school completion. Comparing kids whose mothers have the same IQ, but who differed in whether they completed high school, the model predicts an expected difference of 6 in their test scores.  
   3.2. The coefficient of maternal IQ. Comparing kids with the same value of mom_hs, but whose mothers differ by 1 points in IQ, we would expect to see a difference of 0.6 points in the child's test score.  

When comparing two kids whose mothers have the same level of education, the kid whose mother is x IQ points higher is predicted to have a test score that is 6x higher, on average.

We interpret regression slopes as comparisons of individulas that differ in one predictor while being at the same levels of the other predictors.  
[reference](Regression and Other Stories) 

Y = -129.1667 + 1.1667 * Height  
If a person's height increase by 1 cm, their weight is expected to in crease by 1.1667, according to our model. We don't know for sure that if x increases by 1,
y increases by slope in the *population*; remember our slope is calculated based on only a sample of data. (expected, according to our model, predcited and on average)  
[reference](Texas A&M lecture notes)  

What is the change in the mean response for a 1-unit change in X?
[referene](DOE lecture notes from KU)


### Interpretation of logistic regression coefficients  

when x_1 is increased by 1, then the odds ratio(?) is incresed/decreased by a factor of e^b_hat_1.

- Coefficient is positive -> Success class (the response variable) and the coefficient are positively correlated
- Coefficient is negative -> Success class and the coefficient are negatively correlated.

[03_Logistic_Regression_Part_3_Kor from Prof Kang lecture](https://www.youtube.com/watch?v=3sZx4O2aQs8&list=PLetSlH8YjIfWKLpMp-r6enJvnk6L93wz2&index=10)

### Multiple comparison problem  

Suppose there are 8 individual hypothesis tests are conducted on beta_1 = 0, beta_2 = 0, beta_3 = 0 ... beta_8 = 0 using alaph = 0.05 for each test. What is the probability taht at least one type 1 error (reject H_0, but H_0 is really true) happends in the 8 tests? This probability would be difficult to find, but we can approximate it by assuming independence among the tests.  

Using the binomial distribution - success meaning type 1 error occurs.  
P(success) = 0.05, P(failure) = 0.95
#of trails = 8, #of type 1 error happens = x>=1  
``` 1 - pbinom(0, 8, 0.05)``` which is 0.3366. So there is a 33.66% probability of making at least one type 1 error.  
[reference](Chris Builder - Multiple regression lecture notes Class #16)  

**Family wise error rate**

The probability of rejecting at least one of the null hypotheses when all of the H_0's are true.

https://online.stat.psu.edu/stat505/lesson/7/7.1/7.1.2

### Interpreting the interaction term
The effet of the levels of FactorA depends upon what level of factorB  
[referece](https://online.stat.psu.edu/stat502/lesson/4/4.1)  

logit(pi) = b_0 + b_1 * x_1 + b_2 * x_2 + b_3 * x_1 * x_2  
The effect of x_1 on the response depends on the level of x_2  
[referece] (Analysis of Cateogorical Data course by Chris Bilder)


## PCA  
To find a set of orthogonal bases to preserve the variance of the original data  
[reference](https://youtu.be/bEX6WPMiLvo)   


## Interpretation of CI   
A confidence interval doesn't mean there is 95% probability of the true value or parameters being in that interval. It simply means if we conducted this same survey over and over and used the same method to construct the CI 95% of thoese CIs would cover the true parameter (95 out of 100). We are "confident" in the process of constructing the interval. Noth that the true parameters or values are within any given interval.  
[reference](Stat 835 lecture note from KUMC)  


## Sensitivity and Specificity  
Let X denote the true state of a subject 1 = diseased, 2 = not diseased.  
Let Y denote the result of the test 1 = positive, 2 = negative.  

Sensitivity = P(Y=1 | X=1)  (TP / TP + FN)   
Specificity = P(Y=2 | X=2)  (TN / TN + FP)  

Positive Predictive Value P(X=1 | Y=1)  
Negative Predictive Value P(X=2 | Y=2)  
[reference](Introduction to categorical data analysis by Agresti)  


### miscellaneous
e-05 notation  
1.1e-05 is to be read as 1.1 × 10−5, or 0.000011, and 2e-16 = 2 × 10−16   
There's not sufficient evidence to indicate a difference in the proportion.   


## Power
The term power has a special meaning in statistics. It is the probability of detecting something if it is there, also called the true positive rate.

Conventionally, experimentalists aim for a power of 80% (or more) when planning experiments. This means that if the same experiment is run many times, about 20% of the time it will fail to yield significant results even though it should.

https://web.stanford.edu/class/bios221/book/01-chap.html

## IV, DV transformation interpretation

https://stats.libretexts.org/Bookshelves/Advanced_Statistics/Intermediate_Statistics_with_R_(Greenwood)/07%3A_Simple_linear_regression_inference/7.06%3A_Transformations_part_II_-_Impacts_on_SLR_interpretations_-_log(y)_log(x)_and_both_log(y)_and_log(x)

https://stats.oarc.ucla.edu/other/mult-pkg/faq/general/faqhow-do-i-interpret-a-regression-model-when-some-variables-are-log-transformed/

## Experimental unit vs observational unit

 > The experimental unit is the subject of the experiment. It is the entity to which the treatment factor levels are assigned. The observational unit is the entity on which the response measurements are taken.

 https://byuistats.github.io/Math326_Quarto4/experimental_units.html

20:00

 https://www.youtube.com/watch?v=wiJHp7solao


 ## constrast options in R

```
In R, when you’re fitting a linear model using the lm() or aov()function, the contrasts argument allows you to specify how categorical variables should be encoded into dummy variables for regression analysis.

By default, R uses treatment contrasts, where one level of the categorical variable is chosen as the reference level, and the coefficients for the other levels are compared to this reference level. However, you can change this behavior using the contrasts argument to specify different types of contrasts, such as “contr.sum”, “contr.poly”, “contr.helmert”, etc., each of which results in a different encoding of the categorical variables.

For example, if you have a categorical variable “gender” with levels “male” and “female” and you want to use sum contrasts where the coefficients represent the sum of the response variable for each level compared to the overall mean [which is how we have defined effects in this class], you would specify contrasts = list(gender = contr.sum) in the aov() function.

> Contr.sum: Contrasts sum to zero. Useful for testing specific hypotheses, as it directly compares each group to the overall mean.

> Contr.treatment: Default behavior in R. One level is chosen as the reference, and the coefficients represent differences from this reference level.

> Contr.poly: Polynomial contrasts. Useful for ordinal categorical variables where you want to model linear, quadratic, cubic, etc., trends.

> Contr.helmert: Helmert contrasts. Each level is compared to the mean of subsequent levels.

> Contr.SAS: Similar to Helmert contrasts, but with a different ordering of coefficients.
```

```
## for car::Anova
options(contrasts = c("contr.sum", "contr.poly"))

The default contrasts in R (in case you need to revert back) is options(contrasts = c("contr.treatment", "contr.poly")).
```

From https://byuistats.github.io/Math326_Quarto4/unbalanced.html - footnotes

# FDR

https://www.publichealth.columbia.edu/research/population-health-methods/false-discovery-rate