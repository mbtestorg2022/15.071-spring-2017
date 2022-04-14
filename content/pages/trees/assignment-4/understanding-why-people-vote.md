---
content_type: page
learning_resource_types:
- Assignments
ocw_type: CourseSection
parent_title: 4.5 Assignment 4
parent_type: CourseSection
parent_uid: 11ad34c8-1083-2b18-6afa-cd57f2616109
title: 4.5 Assignment 4
uid: e4031315-c29e-d0c6-413f-d2bd77d67b94
---

*   [\<Assignment 4]({{< baseurl >}}/pages/trees/assignment-4)
*   [4.5.1Predicting Earnings from Census Data]({{< baseurl >}}/pages/trees/assignment-4)
*   [4.5.2Understanding Why People Vote]({{< baseurl >}}/pages/trees/assignment-4/understanding-why-people-vote)
*   [4.5.3State Data Revisted]({{< baseurl >}}/pages/trees/assignment-4/state-data-revisted)
*   [\>State Data Revisted]({{< baseurl >}}/pages/trees/assignment-4/state-data-revisted)

Understanding Why People Vote
-----------------------------

In August 2006 three researchers (Alan Gerber and Donald Green of Yale University, and Christopher Larimer of the University of Northern Iowa) carried out a large scale field experiment in Michigan, USA to test the hypothesis that one of the reasons people vote is social, or extrinsic, pressure. To quote the first paragraph of their ![This resource may not render correctly in a screen reader.](/images/inacessible.gif)[2008 research paper (PDF)](https://web.archive.org/web/20150714044111/http://web.calstatela.edu/faculty/blawson/gerber%20green%20larimer%202008.pdf):

> Among the most striking features of a democratic political system is the participation of millions of voters in elections. Why do large numbers of people vote, despite the fact that ... "the casting of a single vote is of no significance where there is a multitude of electors"? One hypothesis is adherence to social norms. Voting is widely regarded as a citizen duty, and citizens worry that others will think less of them if they fail to participate in elections. Voters' sense of civic duty has long been a leading explanation of vote turnout...

In this homework problem we will use both logistic regression and classification trees to analyze the data they collected.

The Data
--------

The researchers grouped about 344,000 voters into different groups randomly - about 191,000 voters were a "control" group, and the rest were categorized into one of four "treatment" groups. These five groups correspond to five binary variables in the dataset.

1.  "Civic Duty" (variable **civicduty**) group members were sent a letter that simply said "DO YOUR CIVIC DUTY — VOTE!"
2.  "Hawthorne Effect" (variable **hawthorne**) group members were sent a letter that had the "Civic Duty" message plus the additional message "YOU ARE BEING STUDIED" and they were informed that their voting behavior would be examined by means of public records.
3.  "Self" (variable **self**) group members received the "Civic Duty" message as well as the recent voting record of everyone in that household and a message stating that another message would be sent after the election with updated records.
4.  "Neighbors" (variable **neighbors**) group members were given the same message as that for the "Self" group, except the message not only had the household voting records but also that of neighbors - maximizing social pressure.
5.  "Control" (variable **control**) group members were not sent anything, and represented the typical voting situation.

Additional variables include **sex** (0 for male, 1 for female), **yob** (year of birth), and the dependent variable **voting** (1 if they voted, 0 otherwise).

Problem 1.1 - Exploration and Logistic Regression
-------------------------------------------------

We will first get familiar with the data. Load the CSV file [gerber (CSV - 6.2MB)]({{< baseurl >}}/resources/gerber) into R. What proportion of people in this dataset voted in this election?

Exercise 1

&nbsp;Numerical Response&nbsp;

Problem 1.2 - Exploration and Logistic Regression
-------------------------------------------------

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Civic Duty&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Hawthorne Effect&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Self&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Neighbors&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

There are several ways to get this answer. One is to use the tapply function, and compute the mean value of "voting", sorted by whether or not the people were in each group:

tapply(gerber$voting, gerber$civicduty, mean)

tapply(gerber$voting, gerber$hawthorne, mean)

tapply(gerber$voting, gerber$self, mean)

tapply(gerber$voting, gerber$neighbors, mean)

The variable with the largest value in the "1" column has the largest fraction of people voting in their group - this is the Neighbors group.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 1.3 - Exploration and Logistic Regression
-------------------------------------------------

{{< quiz_multiple_choice questionId="Q3_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Civic Duty&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Hawthorne Effect&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Self&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Neighbors&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can build the logistic regression model with the following command:

LogModel = glm(voting ~ civicduty + hawthorne + self + neighbors, data=gerber, family="binomial")

If you look at the output of summary(LogModel), you can see that all of the variables are significant.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 1.4 - Exploration and Logistic Regression
-------------------------------------------------

Using a threshold of **0.3**, what is the accuracy of the logistic regression model? (When making predictions, you don't need to use the newdata argument since we didn't split our data.)

Exercise 4

&nbsp;Numerical Response&nbsp;

Problem 1.5 - Exploration and Logistic Regression
-------------------------------------------------

Using a threshold of **0.5**, what is the accuracy of the logistic regression model?

Exercise 5

&nbsp;Numerical Response&nbsp;

Problem 1.6 - Exploration and Logistic Regression
-------------------------------------------------

{{< quiz_multiple_choice questionId="Q6_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Even though all of the variables are significant, this is a weak predictive model.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;The model's accuracy doesn't improve over the baseline, but the AUC is high, so this is a strong predictive model.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can compute the AUC with the following commands (if your model's predictions are called "predictLog"):

library(ROCR)

ROCRpred = prediction(predictLog, gerber$voting)

as.numeric(performance(ROCRpred, "auc")@y.values)

Even though all of our variables are significant, our model does not improve over the baseline model of just predicting that someone will not vote, and the AUC is low. So while the treatment groups do make a difference, this is a weak predictive model.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.1 - Trees
-------------------

We will now try out trees. Build a CART tree for _voting_ using all data and the same four treatment variables we used before. Don't set the option _method="class"_ - we are actually going to create a regression tree here. We are interested in building a tree to explore the fraction of people who vote, or the probability of voting. We’d like CART to split our groups if they have different probabilities of voting. If we used method=‘class’, CART would only split if one of the groups had a probability of voting above 50% and the other had a probability of voting less than 50% (since the predicted outcomes would be different). However, with regression trees, CART will split even if both groups have probability less than 50%.

Leave all the parameters at their default values. You can use the following command in R to build the tree:

```
CARTmodel = rpart(voting ~ civicduty + hawthorne + self + neighbors, data=gerber)
```

{{< quiz_multiple_choice questionId="Q7_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Only the "Neighbors" variable is used in the tree - it is the only one with a big enough effect.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;All variables are used - they all make a difference.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;No variables are used (the tree is only a root node) - none of the variables make a big enough effect to be split on.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

If you plot the tree, with prp(CARTmodel), you should just see one leaf! There are no splits in the tree, because none of the variables make a big enough effect to be split on.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.2 - Trees
-------------------

Now build the tree using the command:

```
CARTmodel2 = rpart(voting ~ civicduty + hawthorne + self + neighbors, data=gerber, cp=0.0)
```

{{< quiz_multiple_choice questionId="Q8_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Civic duty is the first split, neighbor is the last.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Neighbor is the first split, civic duty is the last.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can plot the tree with prp(CARTmodel2).

We saw in Problem 1 that the highest fraction of voters was in the Neighbors group, followed by the Self group, followed by the Hawthorne group, and lastly the Civic Duty group. And we see here that the tree detects this trend.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.3 - Trees
-------------------

Using only the CART tree plot, determine what fraction (a number between 0 and 1) of "Civic Duty" people voted:

Exercise 9

&nbsp;Numerical Response&nbsp;

Problem 2.4 - Trees
-------------------

Make a new tree that includes the "sex" variable, again with cp = 0.0. Notice that sex appears as a split that is of secondary importance to the treatment group.

{{< quiz_multiple_choice questionId="Q10_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Men (0)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Women (1)&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can generate the new tree using the command:

CARTmodel3 = rpart(voting ~ civicduty + hawthorne + self + neighbors + sex, data=gerber, cp=0.0)

Then, if you plot the tree with prp(CARTmodel3), you can see that there is a split on the "sex" variable after every treatment variable split. For the control group, which corresponds to the bottom left, sex = 0 (male) corresponds to a higher voting percentage.

For the civic duty group, which corresponds to the bottom right, sex = 0 (male) corresponds to a higher voting percentage.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q11_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Men (0)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Women (1)&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can generate the new tree using the command:

CARTmodel3 = rpart(voting ~ civicduty + hawthorne + self + neighbors + sex, data=gerber, cp=0.0)

Then, if you plot the tree with prp(CARTmodel3), you can see that there is a split on the "sex" variable after every treatment variable split. For the control group, which corresponds to the bottom left, sex = 0 (male) corresponds to a higher voting percentage.

For the civic duty group, which corresponds to the bottom right, sex = 0 (male) corresponds to a higher voting percentage.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.1 - Interaction Terms
-------------------------------

We know trees can handle "nonlinear" relationships, e.g. "in the 'Civic Duty' group **and** female", but as we will see in the next few questions, it is possible to do the same for logistic regression. First, let's explore what trees can tell us some more.

Let's just focus on the "Control" treatment group. Create a regression tree using **just the "control" variable**, then create another tree with the "control" and "sex" variables, both with cp=0.0.

In the "control" only tree, what is the absolute value of the difference in the predicted probability of voting between being in the control group versus being in a different group? You can use the absolute value function to get answer, i.e. abs(Control Prediction - Non-Control Prediction). Add the argument "digits = 6" to the prp command to get a more accurate estimate.

Exercise 12

&nbsp;Numerical Response&nbsp;

Problem 3.2 - Interaction Terms
-------------------------------

{{< quiz_multiple_choice questionId="Q13_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Men, by a margin of more than 0.001&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Women, by a margin of more than 0.001&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;They are affected about the same (change in probability within 0.001 of each other).&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can plot the second tree using the command:

prp(CARTsex, digits=6)

The first split says that if control = 1, go left. Then, if sex = 1 (female) predict 0.290456, and if sex = 0 (male) predict 0.302795. On the other side of the tree, where control = 0, if sex = 1 (female) predict 0.334176, and if sex = 0 (male) predict 0.345818. So for women, not being in the control group increases the fraction voting by 0.04372. For men, not being in the control group increases the fraction voting by 0.04302. So men and women are affected about the same.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.3 - Interaction Terms
-------------------------------

{{< quiz_multiple_choice questionId="Q14_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Coefficient is negative, reflecting that women are less likely to vote&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Coefficient is negative, reflecting that women are more likely to vote&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Coefficient is positive, reflecting that women are less likely to vote&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Coefficient is positive, reflecting that women are more likely to vote&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can create the logistic regression model by using the following command:

LogModelSex = glm(voting ~ control + sex, data=gerber, family="binomial")

If you look at the summary of the model, you can see that the coefficient for the "sex" variable is -0.055791. This means that women are less likely to vote, since women have a larger value in the sex variable, and a negative coefficient means that larger values are predictive of 0.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.4 - Interaction Terms
-------------------------------

The regression tree calculated the percentage voting exactly for every one of the four possibilities (Man, Not Control), (Man, Control), (Woman, Not Control), (Woman, Control). Logistic regression has attempted to do the same, although it wasn't able to do as well because it can't consider exactly the joint possibility of being a women and in the control group.

We can quantify this precisely. Create the following dataframe (this contains all of the possible values of sex and control), and evaluate your logistic regression using the predict function (where "LogModelSex" is the name of your logistic regression model that uses both control and sex):

`Possibilities = data.frame(sex=c(0,0,1,1),control=c(0,1,0,1)) predict(LogModelSex, newdata=Possibilities, type="response")`

The four values in the results correspond to the four possibilities in the order they are stated above ( (Man, Not Control), (Man, Control), (Woman, Not Control), (Woman, Control) ). What is the **absolute difference** between the tree and the logistic regression for the **(Woman, Control)** case? Give an answer with five numbers after the decimal point.

Exercise 15

&nbsp;Numerical Response&nbsp;

Problem 3.5 - Interaction Terms
-------------------------------

So the difference is not too big for this dataset, but it is there. We're going to add a new term to our logistic regression now, that is the **combination of the "sex" and "control" variables** - so if this new variable is 1, that means the person is a woman AND in the control group. We can do that with the following command:

```
 `LogModel2 = glm(voting ~ sex + control + sex:control, data=gerber, family="binomial")` 

```

{{< quiz_multiple_choice questionId="Q16_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;If a person is a woman or in the control group, the chance that she voted goes up.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;If a person is a woman and in the control group, the chance that she voted goes up.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;If a person is a woman or in the control group, the chance that she voted goes down.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;If a person is a woman and in the control group, the chance that she voted goes down.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

This coefficient is negative, so that means that a value of 1 in this variable decreases the chance of voting. This variable will have variable 1 if the person is a woman and in the control group.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.6 - Interaction Terms
-------------------------------

Run the same code as before to calculate the average for each group:

predict(LogModel2, newdata=Possibilities, type="response")

Now what is the difference between the logistic regression model and the CART model for the (Woman, Control) case? Again, give your answer with five numbers after the decimal point.

Exercise 17

&nbsp;Numerical Response&nbsp;

Problem 3.7 - Interaction Terms
-------------------------------

{{< quiz_multiple_choice questionId="Q18_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Yes&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;No&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

We should not use all possible interaction terms in a logistic regression model due to overfitting. Even in this simple problem, we have four treatment groups and two values for sex. If we have an interaction term for every treatment variable with sex, we will double the number of variables. In smaller data sets, this could quickly lead to overfitting.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackAssignment 4]({{< baseurl >}}/pages/trees/assignment-4)
*   [ContinueState Data Revisted]({{< baseurl >}}/pages/trees/assignment-4/state-data-revisted)