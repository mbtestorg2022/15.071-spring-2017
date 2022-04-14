---
content_type: page
learning_resource_types:
- Assignments
ocw_type: CourseSection
parent_title: 4.5 Assignment 4
parent_type: CourseSection
parent_uid: 11ad34c8-1083-2b18-6afa-cd57f2616109
title: 4.5 Assignment 4
uid: 1ec4de19-6088-678e-c051-d69160bc733a
---

*   [\<Understanding Why People Vote]({{< baseurl >}}/pages/trees/assignment-4/understanding-why-people-vote)
*   [4.5.1Predicting Earnings from Census Data]({{< baseurl >}}/pages/trees/assignment-4)
*   [4.5.2Understanding Why People Vote]({{< baseurl >}}/pages/trees/assignment-4/understanding-why-people-vote)
*   [4.5.3State Data Revisted]({{< baseurl >}}/pages/trees/assignment-4/state-data-revisted)
*   [\>Text Analytics]({{< baseurl >}}/pages/text-analytics)

State Data Revisited
--------------------

We will be revisiting the "state" dataset from one of the optional problems in Unit 2. This dataset has, for each of the fifty U.S. states, the population, per capita income, illiteracy rate, murder rate, high school graduation rate, average number of frost days, area, latitude and longitude, division the state belongs to, region the state belongs to, and two-letter abbreviation. This dataset comes from the U.S. Department of Commerce, Bureau of the Census.

Load the dataset into R and convert it to a data frame by running the following two commands in R:

```
data(state)
statedata = data.frame(state.x77)
```

If you can't access the state dataset in R, here is a CSV file with the same data that you can load into R using the read.csv function: [statedataSimple (CSV)]({{< baseurl >}}/resources/statedatasimple).  Be sure to call the output of the read.csv function "statedata".

After you have loaded the data into R, inspect the data set using the command: str(statedata)

This dataset has 50 observations (one for each US state) and the following 8 variables:

*   **Population** - the population estimate of the state in 1975
*   **Income** - per capita income in 1974
*   **Illiteracy** - illiteracy rates in 1970, as a percent of the population
*   **Life.Exp** - the life expectancy in years of residents of the state in 1970
*   **Murder** - the murder and non-negligent manslaughter rate per 100,000 population in 1976 
*   **HS.Grad** - percent of high-school graduates in 1970
*   **Frost** - the mean number of days with minimum temperature below freezing from 1931–1960 in the capital or a large city of the state
*   **Area** - the land area (in square miles) of the state

We will try to build a model for life expectancy using regression trees, and employ cross-validation to improve our tree's performance.

Problem 1.1 - Linear Regression Models
--------------------------------------

Let's recreate the **linear regression** models we made in the previous homework question. First, predict _Life.Exp_ using all of the other variables as the independent variables (_Population, Income, Illiteracy, Murder, HS.Grad, Frost, Area_ ). Use the entire dataset to build the model.

What is the **adjusted** R-squared of the model?

Exercise 1

&nbsp;Numerical Response&nbsp;

Problem 1.2 - Linear Regression Models
--------------------------------------

Calculate the sum of squared errors (SSE) between the predicted life expectancies using this model and the actual life expectancies:

Exercise 2

&nbsp;Numerical Response&nbsp;

Problem 1.3 - Linear Regression Models
--------------------------------------

Build a second **linear regression** model using just _Population, Murder, Frost, and HS.Grad_ as independent variables (the best 4 variable model from the previous homework). What is the **adjusted** R-squared for this model?

Exercise 3

&nbsp;Numerical Response&nbsp;

Problem 1.4 - Linear Regression Models
--------------------------------------

Calculate the sum of squared errors again, using this reduced model:

Exercise 4

&nbsp;Numerical Response&nbsp;

Problem 1.5 - Linear Regression Models
--------------------------------------

{{< quiz_multiple_choice questionId="Q5_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Trying different combinations of variables in linear regression is like trying different numbers of splits in a tree - this controls the complexity of the model.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Using many variables in a linear regression is **always** better than using just a few.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;The variables we removed were uncorrelated with _Life.Exp_&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The correct answer is the first one. Trying different combinations of variables in linear regression controls the complexity of the model. This is similar to trying different numbers of splits in a tree, which is also controlling the complexity of the model.

The second answer is incorrect because as we see here, a model with fewer variables actually has a higher adjusted R-squared. If your accuracy is just as good, a model with fewer variables is almost always better.

The third answer is incorrect because the variables we removed have non-zero correlations with the dependent variable Life.Exp. Illiteracy and Area are negatively correlated with Life.Exp, with correlations of -0.59 and -0.11. Income is positively correlated with Life.Exp, with a correlation of 0.34. These correlations can be computed by typing the following into your R console:

cor(statedata$Life.Exp, statedata$Income)

cor(statedata$Life.Exp, statedata$Illiteracy)

cor(statedata$Life.Exp, statedata$Area){{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.1 - CART Models
-------------------------

Let's now build a **CART model** to predict _Life.Exp_ using all of the other variables as independent variables (_Population, Income, Illiteracy, Murder, HS.Grad, Frost, Area_). We'll use the default _minbucket_ parameter, so don't add the _minbucket_ argument. Remember that in this problem we are not as interested in _predicting_ life expectancies for new observations as we are understanding how they relate to the other variables we have, so we'll use all of the data to build our model. You shouldn't use the method="class" argument since this is a regression tree.

{{< quiz_multiple_choice questionId="Q6_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Population&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Murder&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Frost&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;HS.Grad&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Area&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can create the tree in R by typing the following command:

CARTmodel = rpart(Life.Exp ~ ., data=statedata)

Be sure to load the "rpart" and "rpart.plot" packages with the library command if they are not already loaded.

You can then plot the tree by typing:

prp(CARTmodel)

We can see that the only variable used in the tree is "Murder".{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.2 - CART Models
-------------------------

Use the regression tree you just built to predict life expectancies (using the predict function), and calculate the sum-of-squared-errors (SSE) like you did for linear regression. What is the SSE?

Exercise 7

&nbsp;Numerical Response&nbsp;

Problem 2.3 - CART Models
-------------------------

The error is higher than for the linear regression models. One reason might be that we haven't made the tree big enough. Set the _minbucket_ parameter to 5, and recreate the tree.

{{< quiz_multiple_choice questionId="Q8_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Population&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Murder&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Frost&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;HS.Grad&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Area&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can create a tree with a minbucket value of 5 with the following command:

CARTmodel2 = rpart(Life.Exp ~ ., data=statedata, minbucket=5)

Then, if you plot the tree using prp(CARTmodel2), you can see that Murder, HS.Grad, and Area are all used in this new tree.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.4 - CART Models
-------------------------

{{< quiz_multiple_choice questionId="Q9_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Smaller&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Larger&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Since the tree now has more splits, it must be true that the default minbucket parameter was limiting the tree from splitting more before. So the default minbucket parameter must be larger than 5.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.5 - CART Models
-------------------------

What is the SSE of this tree?

Exercise 10

&nbsp;Numerical Response&nbsp;

This is much closer to the linear regression model's error. By changing the parameters we have improved the fit of our model.

Problem 2.6 - CART Models
-------------------------

Can we do even better? Create a tree that predicts _Life.Exp_ using **only** _Area_, with the _minbucket_ parameter to 1. What is the SSE of this newest tree?

Exercise 11

&nbsp;Numerical Response&nbsp;

Problem 2.7 - CART Models
-------------------------

{{< quiz_multiple_choice questionId="Q12_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Trees are much better than linear regression for this problem because they can capture nonlinearities that linear regression misses.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;We can build almost perfect models given the right parameters, even if they violate our intuition of what a good model should be.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Area is obviously a very meaningful predictor of life expectancy, given we were able to get such low error using just Area as our independent variable.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The correct answer is the second one. By making the minbucket parameter very small, we could build an almost perfect model using just one variable, that is not even our most significant variable. However, if you plot the tree using prp(CARTmodel3), you can see that the tree has 22 splits! This is not a very interpretable model, and will not generalize well.

The first answer is incorrect because our tree model that was not overfit performed similarly to the linear regression model. Trees only look better than linear regression here because we are overfitting the model to the data.

The third answer is incorrect because Area is not actually a very meaningful predictor. Without overfitting the tree, our model would not be very accurate only using Area.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.1 - Cross-validation
------------------------------

Adjusting the variables included in a linear regression model is a form of model tuning. In Problem 1 we showed that by removing variables in our linear regression model (tuning the model), we were able to maintain the fit of the model while using a simpler model. A rule of thumb is that simpler models are more interpretable and generalizeable. We will now tune our regression tree to see if we can improve the fit of our tree while keeping it as simple as possible.

Load the _caret_ library, and set the seed to 111. Set up the controls exactly like we did in the lecture (10-fold cross-validation) with _cp_ varying over the range 0.01 to 0.50 in increments of 0.01. Use the _train_ function to determine the best _cp_ value for a CART model using all of the available independent variables, and the entire dataset statedata. What value of cp does the train function recommend? (Remember that the train function tells you to pick the largest value of cp with the lowest error when there are ties, and explains this at the bottom of the output.)

Exercise 13

&nbsp;Numerical Response&nbsp;

Problem 3.2 - Cross-Validation
------------------------------

Create a tree with the value of _cp_ you found in the previous problem, all of the available independent variables, and the entire dataset "statedata" as the training data. Then plot the tree. You'll notice that this is actually quite similar to the first tree we created with the initial model. Interpret the tree: we predict the life expectancy to be 70 if the murder rate is greater than or equal to

Exercise 14

&nbsp;Numerical Response&nbsp;

and is less than

Exercise 15

&nbsp;Numerical Response&nbsp;

Problem 3.3 - Cross-Validation
------------------------------

Calculate the SSE of this tree:

Exercise 16

&nbsp;Numerical Response&nbsp;

Problem 3.4 - Cross-Validation
------------------------------

{{< quiz_multiple_choice questionId="Q17_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;The first model&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;The second model&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;The model we just made with the "best" cp&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The purpose of cross-validation is to pick the tree that will perform the best on a test set. So we would expect the model we made with the "best" cp to perform best on a test set.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.5 - Cross-Validation
------------------------------

At the end of Problem 2 we made a very complex tree using just Area. Use _train_ with the same parameters as before but just using Area as an independent variable to find the best cp value (set the seed to 111 first). Then build a new tree using just Area and this value of cp.

How many splits does the tree have?

Exercise 18

&nbsp;Numerical Response&nbsp;

Problem 3.6 - Cross-Validation
------------------------------

The lower left leaf (or bucket) corresponds to the lowest predicted Life.Exp of 70. Observations in this leaf correspond to states with area greater than or equal to

Exercise 19

&nbsp;Numerical Response&nbsp;

and area less than

Exercise 20

&nbsp;Numerical Response&nbsp;

Problem 3.7 - Cross-Validation
------------------------------

{{< quiz_multiple_choice questionId="Q21_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;The best model in this whole question is the first "Area tree" because it had the lowest SSE.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;The Area variable is not as predictive as Murder rate.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Cross-validation is intended to decrease the SSE for a model on the training data, compared to a tree that isn't cross-validated.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Cross-validation will always improve the SSE of a model on unseen data, compared to a tree that isn't cross-validated.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can calculate the SSE by first making predictions and then computing the SSE:

PredictionsCART5 = predict(CARTmodel5)

sum((statedata$Life.Exp - PredictionsCART5)^2)

The original Area tree was overfitting the data - it was uninterpretable. Area is not as useful as Murder - if it was, it would have been in the cross-validated tree. Cross-validation is not designed to improve the fit on the training data, but it won't necessarily make it worse either. Cross-validation cannot guarantee improving the SSE on unseen data, although it often helps.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackUnderstanding Why People Vote]({{< baseurl >}}/pages/trees/assignment-4/understanding-why-people-vote)
*   [ContinueText Analytics]({{< baseurl >}}/pages/text-analytics)