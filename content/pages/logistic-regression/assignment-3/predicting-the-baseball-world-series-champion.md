---
content_type: page
learning_resource_types:
- Assignments
ocw_type: CourseSection
parent_title: 3.5 Assignment 3
parent_type: CourseSection
parent_uid: d4a650ea-930c-2c8c-0f98-9b353a5a342e
title: 3.5 Assignment 3
uid: 3b462833-7389-a83d-6609-7f7597856e56
---

*   [\<Assignment 3]({{< baseurl >}}/pages/logistic-regression/assignment-3)
*   [3.5.1Popularity of Music Records]({{< baseurl >}}/pages/logistic-regression/assignment-3)
*   [3.5.2Predicting the Baseball World Series Champion]({{< baseurl >}}/pages/logistic-regression/assignment-3/predicting-the-baseball-world-series-champion)
*   [\>Trees]({{< baseurl >}}/pages/trees)

Predicting the Baseball World Series Champion
---------------------------------------------

Last week, in the Moneyball lecture, we discussed how regular season performance is not strongly correlated with winning the World Series in baseball. In this homework question, we'll use the same data to investigate how well we can predict the World Series winner at the beginning of the playoffs.

To begin, load the dataset [baseball (CSV)]({{< baseurl >}}/resources/baseball-1) into R using the read.csv function, and call the data frame "baseball". This is the same data file we used during the Moneyball lecture, and the data comes from [Baseball-Reference.com](http://www.baseball-reference.com/).

As a reminder, this dataset contains data concerning a baseball team's performance in a given year. It has the following variables:

*   **Team**: A code for the name of the team
*   **League**: The Major League Baseball league the team belongs to, either AL (American League) or NL (National League)
*   **Year**: The year of the corresponding record
*   **RS**: The number of runs scored by the team in that year
*   **RA**: The number of runs allowed by the team in that year
*   **W**: The number of regular season wins by the team in that year
*   **OBP**: The on-base percentage of the team in that year
*   **SLG**: The slugging percentage of the team in that year
*   **BA**: The batting average of the team in that year
*   **Playoffs**: Whether the team made the playoffs in that year (1 for yes, 0 for no)
*   **RankSeason**: Among the playoff teams in that year, the ranking of their regular season records (1 is best)
*   **RankPlayoffs**: Among the playoff teams in that year, how well they fared in the playoffs. The team winning the World Series gets a RankPlayoffs of 1.
*   **G**: The number of games a team played in that year
*   **OOBP**: The team's opponents' on-base percentage in that year
*   **OSLG**: The team's opponents' slugging percentage in that year

Problem 1.1 - Limiting to Teams Making the Playoffs
---------------------------------------------------

Each row in the baseball dataset represents a team in a particular year.

How many team/year pairs are there in the whole dataset?

Exercise 1

&nbsp;Numerical Response&nbsp;

Problem 1.2 - Limiting to Teams Making the Playoffs
---------------------------------------------------

Though the dataset contains data from 1962 until 2012, we removed several years with shorter-than-usual seasons. Using the table() function, identify the total number of years included in this dataset.

Exercise 2

&nbsp;Numerical Response&nbsp;

Problem 1.3 - Limiting to Teams Making the Playoffs
---------------------------------------------------

Because we're only analyzing teams that made the playoffs, use the subset() function to **replace baseball** with a data frame limited to teams that made the playoffs (so your subsetted data frame should still be called "baseball"). How many team/year pairs are included in the new dataset?

Exercise 3

&nbsp;Numerical Response&nbsp;

Problem 1.4 - Limiting to Teams Making the Playoffs
---------------------------------------------------

{{< quiz_multiple_choice questionId="Q4_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;2&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;4&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;6&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;8&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;10&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;12&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Using table(baseball$Year), we can see at least one season had 2, 4, 8, and 10 contenders. A fancier approach would be to use table(table(baseball$Year)).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.1 - Adding an Important Predictor
-------------------------------------------

It's much harder to win the World Series if there are 10 teams competing for the championship versus just two. Therefore, we will add the predictor variable NumCompetitors to the baseball data frame. NumCompetitors will contain the number of total teams making the playoffs in the year of a particular team/year pair. For instance, NumCompetitors should be 2 for the 1962 New York Yankees, but it should be 8 for the 1998 Boston Red Sox.

We start by storing the output of the table() function that counts the number of playoff teams from each year:

PlayoffTable = table(baseball$Year)

You can output the table with the following command:

PlayoffTable

We will use this stored table to look up the number of teams in the playoffs in the year of each team/year pair.

{{< quiz_multiple_choice questionId="Q5_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Vector of years stored as numbers (type num)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Vector of years stored as strings (type chr)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Vector of frequencies stored as numbers (type num)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Vector of frequencies stored as strings (type chr)&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

From the call str(names(PlayoffTable)) we see PlayoffTable has names of type chr, which are the years of the teams in the dataset.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.2 - Adding an Important Predictor
-------------------------------------------

{{< quiz_multiple_choice questionId="Q6_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;PlayoffTable(1990, 2001)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;PlayoffTable(c(1990, 2001))&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;PlayoffTable("1990", "2001")&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;PlayoffTable(c("1990", "2001"))&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;PlayoffTable\[1990, 2001\]&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;PlayoffTable\[c(1990, 2001)\]&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;PlayoffTable\["1990", "2001"\]&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;PlayoffTable\[c("1990", "2001")\]&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Because PlayoffTable is an object and not a function, we look up elements in it with square brackets instead of parentheses. We build the vector of years to be passed with the c() function. Because the names of PlayoffTable are strings and not numbers, we need to pass "1990" and "2001".{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.3 - Adding an Important Predictor
-------------------------------------------

{{< quiz_multiple_choice questionId="Q7_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;baseball$NumCompetitors = PlayoffTable(baseball$Year)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;baseball$NumCompetitors = PlayoffTable\[baseball$Year\]&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;baseball$NumCompetitors = PlayoffTable(as.character(baseball$Year))&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;baseball$NumCompetitors = PlayoffTable\[as.character(baseball$Year)\]&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Because PlayoffTable is an object and not a function, we look up elements in it with square brackets instead of parentheses. as.character() is needed to convert the Year variable in the dataset to a string, which we know from the previous parts is needed to look up elements in a table. If you're not sure what a function does, remember you can look it up with the ? function. For instance, you could type ?as.character to look up information about as.character.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.4 - Adding an Important Predictor
-------------------------------------------

Add the NumCompetitors variable to your baseball data frame. How many playoff team/year pairs are there in our dataset from years where 8 teams were invited to the playoffs?

Exercise 8

&nbsp;Numerical Response&nbsp;

Problem 3.1 - Bivariate Models for Predicting World Series Winner
-----------------------------------------------------------------

In this problem, we seek to predict whether a team won the World Series; in our dataset this is denoted with a RankPlayoffs value of 1. Add a variable named WorldSeries to the baseball data frame, by typing the following command in your R console:

baseball$WorldSeries = as.numeric(baseball$RankPlayoffs == 1)

WorldSeries takes value 1 if a team won the World Series in the indicated year and a 0 otherwise. How many observations do we have in our dataset where a team did NOT win the World Series?

Exercise 9

&nbsp;Numerical Response&nbsp;

Problem 3.2 - Bivariate Models for Predicting World Series Winner
-----------------------------------------------------------------

{{< quiz_multiple_choice questionId="Q10_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Year&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;RS&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;RA&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;W&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;OBP&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;SLG&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;BA&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;RankSeason&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;OOBP&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;OSLG&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;NumCompetitors&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;League&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The results come from building each bivariate model and looking at its summary. For instance, the result for the variable Year can be obtained by running summary(glm(WorldSeries~Year, data=baseball, family="binomial")). You can save time on repeated model building by using the up arrow in your R terminal. The W and SLG variables were both nearly significant, with p = 0.0577 and 0.0504, respectively.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 4.1 - Multivariate Models for Predicting World Series Winner
--------------------------------------------------------------------

In this section, we'll consider multivariate models that combine the variables we found to be significant in bivariate models. Build a model using all of the variables that you found to be significant in the bivariate models. How many variables are significant in the combined model?

Exercise 11

&nbsp;Numerical Response&nbsp;

Problem 4.2 - Multivariate Models for Predicting World Series Winner
--------------------------------------------------------------------

{{< quiz_multiple_choice questionId="Q12_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Year/RA&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Year/RankSeason&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Year/NumCompetitors&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;RA/RankSeason&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;RA/NumCompetitors&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;RankSeason/NumCompetitors&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

To test the correlation between two variables, use a command like cor(baseball$Year, baseball$RA). While every pair was at least moderately correlated, the only strongly correlated pair was Year/NumCompetitors, with correlation coefficient 0.914.

As a shortcut, you can compute all pair-wise correlations between these variables with:

cor(baseball\[c(“Year”, “RA”, “RankSeason”, “NumCompetitors”)\]){{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 4.3 - Multivariate Models for Predicting World Series Winner
--------------------------------------------------------------------

{{< quiz_multiple_choice questionId="Q13_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Year&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;RA&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;RankSeason&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;NumCompetitors&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Year/RA&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Year/RankSeason&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Year/NumCompetitors&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;RA/RankSeason&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;RA/NumCompetitors&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;RankSeason/NumCompetitors&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The two-variable models can be built with the following commands:

Model1 = glm(WorldSeries ~ Year + RA, data=baseball, family=binomial)

Model2 = glm(WorldSeries ~ Year + RankSeason, data=baseball, family=binomial)

Model3 = glm(WorldSeries ~ Year + NumCompetitors, data=baseball, family=binomial)

Model4 = glm(WorldSeries ~ RA + RankSeason, data=baseball, family=binomial)

Model5 = glm(WorldSeries ~ RA + NumCompetitors, data=baseball, family=binomial)

Model6 = glm(WorldSeries ~ RankSeason + NumCompetitors, data=baseball, family=binomial)

None of the models with two independent variables had both variables significant, so none seem promising as compared to a simple bivariate model. Indeed the model with the lowest AIC value is the model with just NumCompetitors as the independent variable.

This seems to confirm the claim made by Billy Beane in Moneyball that all that matters in the Playoffs is luck, since NumCompetitors has nothing to do with the quality of the teams!{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackAssignment 3]({{< baseurl >}}/pages/logistic-regression/assignment-3)
*   [ContinueTrees]({{< baseurl >}}/pages/trees)