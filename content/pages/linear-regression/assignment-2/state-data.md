---
content_type: page
learning_resource_types:
- Assignments
ocw_type: CourseSection
parent_title: 2.5 Assignment 2
parent_type: CourseSection
parent_uid: d3823600-300c-0300-0e79-696e835f8f2f
title: 2.5 Assignment 2
uid: 609cf352-3750-f69e-cb54-c706f04a68c5
---

*   [\<Detecting Flu Epidemics via Search Engine Query Data]({{< baseurl >}}/pages/linear-regression/assignment-2/detecting-flu-epidemics-via-search-engine-query-data)
*   [2.5.1Climate Change]({{< baseurl >}}/pages/linear-regression/assignment-2)
*   [2.5.2Reading Test Scores]({{< baseurl >}}/pages/linear-regression/assignment-2/reading-test-scores)
*   [2.5.3Detecting Flu Epidemics via Search Engine Query Data]({{< baseurl >}}/pages/linear-regression/assignment-2/detecting-flu-epidemics-via-search-engine-query-data)
*   [2.5.4State Data]({{< baseurl >}}/pages/linear-regression/assignment-2/state-data)
*   [\>Logistic Regression]({{< baseurl >}}/pages/logistic-regression)

State Data
----------

We often take data for granted. However, one of the hardest parts about analyzing a problem you're interested in can be to find good data to answer the questions you want to ask. As you're learning R, though, there are many datasets that R has built in that you can take advantage of.

In this problem, we will be examining the "state" dataset, which has data from the 1970s on all fifty US states. For each state, the dataset includes the population, per capita income, illiteracy rate, murder rate, high school graduation rate, average number of frost days, area, latitude and longitude, division the state belongs to, region the state belongs to, and two-letter abbreviation.

Load the dataset and convert it to a data frame by running the following two commands in R:

data(state)

statedata = cbind(data.frame(state.x77), state.abb, state.area, state.center,  state.division, state.name, state.region)

If you can't access the state dataset in R, here is a CSV file with the same data that you can load into R using the read.csv function: [statedata (CSV)]({{< baseurl >}}/resources/statedata).

After you have loaded the data into R, inspect the data set using the command: str(statedata)

This dataset has 50 observations (one for each US state) and the following 15 variables:

*   **Population** - the population estimate of the state in 1975
*   **Income** - per capita income in 1974
*   **Illiteracy** - illiteracy rates in 1970, as a percent of the population
*   **Life.Exp** - the life expectancy in years of residents of the state in 1970
*   **Murder** - the murder and non-negligent manslaughter rate per 100,000 population in 1976 
*   **HS.Grad** - percent of high-school graduates in 1970
*   **Frost** - the mean number of days with minimum temperature below freezing from 1931–1960 in the capital or a large city of the state
*   **Area** - the land area (in square miles) of the state
*   **state.abb** - a 2-letter abreviation for each state
*   **state.area** - the area of each state, in square miles
*   **x** - the longitude of the center of the state
*   **y** - the latitude of the center of the state
*   **state.division** - the division each state belongs to (New England, Middle Atlantic, South Atlantic, East South Central, West South Central, East North Central, West North Central, Mountain, or Pacific)
*   **state.name** - the full names of each state
*   **state.region** - the region each state belong to (Northeast, South, North Central, or West)

Problem 1.1 - Data Exploration
------------------------------

We begin by exploring the data. Plot all of the states' centers with latitude on the y axis (the "y" variable in our dataset) and longitude on the x axis (the "x" variable in our dataset). The shape of the plot should look like the outline of the United States! Note that Alaska and Hawaii have had their coordinates adjusted to appear just off of the west coast.

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;statedata$y&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;statedata$x&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;I used a different variable name.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

To generate the described plot, you should type plot(statedata$x, statedata$y) in your R console. The first variable here is statedata$x.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 1.2 - Data Exploration
------------------------------

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;West&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;North Central&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;South&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Northeast&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can find the average high school graduation rate of all states in each of the regions by typing the following command in your R console:

tapply(statedata$HS.Grad, statedata$state.region, mean)

The highest value is for the West region.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 1.3 - Data Exploration
------------------------------

Now, make a boxplot of the murder rate by region (for more information about creating boxplots in R, type ?boxplot in your console).

{{< quiz_multiple_choice questionId="Q3_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Northeast&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;South&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;North Central&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;West&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

To generate the boxplot, you should type boxplot(statedata$Murder ~ statedata$state.region) in your R console. You can see that the region with the highest median murder rate (the one with the highest solid line in the box) is the South.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 1.4 - Data Exploration
------------------------------

{{< quiz_multiple_choice questionId="Q4_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Delaware&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Rhode Island&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Maine&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;New York&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The correct answer is New York. If you first use the subset command:

NortheastData = subset(statedata, state.region == "Northeast")

You can then look at NortheastData$Murder together with NortheastData$state.abb to identify the outlier.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.1 - Predicting Life Expectancy - An Initial Model
-----------------------------------------------------------

We would like to build a model to predict life expectancy by state using the state statistics we have in our dataset.

Build the model with all potential variables included (Population, Income, Illiteracy, Murder, HS.Grad, Frost, and Area). Note that you should use the variable "Area" in your model, NOT the variable "state.area".

What is the coefficient for "Income" in your linear regression model?

Exercise 5

&nbsp;Numerical Response&nbsp;

Problem 2.2 - Predicting Life Expectancy - An Initial Model
-----------------------------------------------------------

{{< quiz_multiple_choice questionId="Q6_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;For a one unit increase in income, predicted life expectancy increases by |x|&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;For a one unit increase in income, predicted life expectancy decreases by |x|&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;For a one unit increase in predicted life expectancy, income decreases by |x|&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;For a one unit increase in predicted life expectancy, income increases by |x|&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

If we increase income by one unit, then our model’s prediction will increase by the coefficient of income, x. Because x is negative, this is the same as predicted life expectancy decreasing by |x|.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.3 - Predicting Life Expectancy - An Initial Model
-----------------------------------------------------------

Now plot a graph of life expectancy vs. income using the command:

plot(statedata$Income, statedata$Life.Exp)

{{< quiz_multiple_choice questionId="Q7_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Life expectancy is somewhat positively correlated with income.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Life expectancy is somewhat negatively correlated with income.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Life expectancy is not correlated with income.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Although the point in the lower right hand corner of the plot appears to be an outlier, we observe a positive linear relationship in the plot.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.4 - Predicting Life Expectancy - An Initial Model
-----------------------------------------------------------

{{< quiz_multiple_choice questionId="Q8_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Income is not related to life expectancy.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Multicollinearity&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Although income is an insignificant variable in the model, this does not mean that there is no association between income and life expectancy. However, in the presence of all of the other variables, income does not add statistically significant explanatory power to the model. This means that multicollinearity is probably the issue.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.1 - Predicting Life Expectancy - Refining the Model and Analyzing Predictions
---------------------------------------------------------------------------------------

Recall that we discussed the principle of simplicity: that is, a model with fewer variables is preferable to a model with many unnnecessary variables. Experiment with removing independent variables from the original model. Remember to use the significance of the coefficients to decide which variables to remove (remove the one with the largest "p-value" first, or the one with the "t value" closest to zero), and to remove them one at a time (this is called "backwards variable selection"). This is important due to multicollinearity issues - removing one insignificant variable may make another previously insignificant variable become significant.

{{< quiz_multiple_choice questionId="Q9_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Income, HS.Grad, Frost, Murder&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;HS.Grad, Population, Income, Frost&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Frost, Murder, HS.Grad, Illiteracy&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Population, Murder, Frost, HS.Grad&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

We would eliminate the variable "Area" first (since it has the highest p-value, or probability, with a value of 0.9649), by adjusting our lm command to the following:

LinReg = lm(Life.Exp ~ Population + Income + Illiteracy + Murder + HS.Grad + Frost, data=statedata)

Looking at summary(LinReg) now, we would choose to eliminate "Illiteracy" since it now has the highest p-value of 0.9340, using the following command:

LinReg = lm(Life.Exp ~ Population + Income + Murder + HS.Grad + Frost, data=statedata)

Looking at summary(LinReg) again, we would next choose to eliminate "Income", since it has a p-value of 0.9153. This gives the following four variable model:

LinReg = lm(Life.Exp ~ Population + Murder + HS.Grad + Frost, data=statedata)

This model with 4 variables is a good model. However, we can see that the variable "Population" is not quite significant. In practice, it would be up to you whether or not to keep the variable "Population" or eliminate it for a 3-variable model. Population does not add much statistical significance in the presence of murder, high school graduation rate, and frost days. However, for the remainder of this question, we will analyze the 4-variable model.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.2 - Predicting Life Expectancy - Refining the Model and Analyzing Predictions
---------------------------------------------------------------------------------------

{{< quiz_multiple_choice questionId="Q10_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;We expect the "Multiple R-squared" value of the simplified model to be slightly worse than that of the initial model. It can't be better than the "Multiple R-squared" value of the initial model.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;We expect the "Multiple R-squared" value of the simplified model to be slightly better than that of the initial model. It can't be worse than the "Multiple R-squared" value of the initial model. &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;We expect the "Multiple R-squared" of the simplified model to be about the same as the intial model (we have no way of knowing if it will be slightly worse or slightly better than the Multiple R-squared of the intial model).&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

When we remove insignificant variables, the "Multiple R-squared" will always be worse, but only slightly worse. This is due to the nature of a linear regression model. It is always possible for the regression model to make a coefficient zero, which would be the same as removing the variable from the model. The fact that the coefficient is not zero in the intial model means it must be helping the R-squared value, even if it is only a very small improvement. So when we force the variable to be removed, it will decrease the R-squared a little bit. However, this small decrease is worth it to have a simpler model.

On the contrary, when we remove insignificant variables, the "Adjusted R-squred" will frequently be better. This value accounts for the complexity of the model, and thus tends to increase as insignificant variables are removed, and decrease as insignificant variables are added.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.3 - Predicting Life Expectancy - Refining the Model and Analyzing Predictions
---------------------------------------------------------------------------------------

Using the simplified 4 variable model that we created, we'll now take a look at how our predictions compare to the actual values.

Take a look at the vector of predictions by using the predict function (since we are just looking at predictions on the training set, you don't need to pass a "newdata" argument to the predict function).

{{< quiz_multiple_choice questionId="Q11_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;South Carolina&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Mississippi&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Alabama&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Georgia&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

If your simplified 4-variable model is called "LinReg", you can answer this question by typing

sort(predict(LinReg))

in your R console. The first state listed has the lowest predicted life expectancy, which is Alabama.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q12_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;South Carolina&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Mississippi&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Alabama&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Georgia&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can find the row number of the state with the lowest life expectancy by typing which.min(statedata$Life.Exp) into your R console. This returns 40. The 40th state name in the vector statedata$state.name is South Carolina.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.4 - Predicting Life Expectancy - Refining the Model and Analyzing Predictions
---------------------------------------------------------------------------------------

{{< quiz_multiple_choice questionId="Q13_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Massachusetts&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Maine&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Washington&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Hawaii&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

If your simplified 4-variable model is called "LinReg", you can answer this question by typing "sort(predict(LinReg))" in your R console. The last state listed has the highest predicted life expectancy, which is Washington.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q14_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Massachusetts&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Maine&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Washington&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Hawaii&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can find the row number of the state with the highest life expectancy by typing which.max(statedata$Life.Exp) into your R console. This returns 11. The 11th state name in the vector statedata$state.name is Hawaii.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.5 - Predicting Life Expectancy - Refining the Model and Analyzing Predictions
---------------------------------------------------------------------------------------

Take a look at the vector of residuals (the difference between the predicted and actual values).

{{< quiz_multiple_choice questionId="Q15_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Maine&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Florida&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Indiana&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Illinois&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can look at the sorted list of absolute errors by typing

sort(abs(model$residuals))

into your R console (where "model" is the name of your model). Alternatively, you can compute the residuals manually by typing

sort(abs(statedata$Life.Exp - predict(model)))

in your R console. The smallest absolute error is for Indiana.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q16_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Hawaii&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Maine&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Texas&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;South Carolina&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can look at the sorted list of absolute errors by typing

sort(abs(model$residuals))

into your R console (where "model" is the name of your model). Alternatively, you can compute the residuals manually by typing

sort(abs(statedata$Life.Exp - predict(model)))

in your R console. The largest absolute error is for Hawaii.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackDetecting Flu Epidemics via Search Engine Query Data]({{< baseurl >}}/pages/linear-regression/assignment-2/detecting-flu-epidemics-via-search-engine-query-data)
*   [ContinueLogistic Regression]({{< baseurl >}}/pages/logistic-regression)