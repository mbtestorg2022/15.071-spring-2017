---
content_type: page
learning_resource_types:
- Assignments
ocw_type: CourseSection
parent_title: 2.5 Assignment 2
parent_type: CourseSection
parent_uid: d3823600-300c-0300-0e79-696e835f8f2f
title: 2.5 Assignment 2
uid: f590aa02-4205-ae29-1d85-5ec56a16b4a4
---

*   [\<Assignment 2]({{< baseurl >}}/pages/linear-regression/assignment-2)
*   [2.5.1Climate Change]({{< baseurl >}}/pages/linear-regression/assignment-2)
*   [2.5.2Reading Test Scores]({{< baseurl >}}/pages/linear-regression/assignment-2/reading-test-scores)
*   [2.5.3Detecting Flu Epidemics via Search Engine Query Data]({{< baseurl >}}/pages/linear-regression/assignment-2/detecting-flu-epidemics-via-search-engine-query-data)
*   [2.5.4State Data]({{< baseurl >}}/pages/linear-regression/assignment-2/state-data)
*   [\>Detecting Flu Epidemics via Search Engine Query Data]({{< baseurl >}}/pages/linear-regression/assignment-2/detecting-flu-epidemics-via-search-engine-query-data)

Reading Test Scores
-------------------

The Programme for International Student Assessment (PISA) is a test given every three years to 15-year-old students from around the world to evaluate their performance in mathematics, reading, and science. This test provides a quantitative way to compare the performance of students from different parts of the world. In this homework assignment, we will predict the reading scores of students from the United States of America on the 2009 PISA exam.

The datasets [pisa2009train (CSV)]({{< baseurl >}}/resources/pisa2009train) and [pisa2009test (CSV)]({{< baseurl >}}/resources/pisa2009test) contain information about the demographics and schools for American students taking the exam, derived from [2009 PISA Public-Use Data Files](http://nces.ed.gov/pubsearch/pubsinfo.asp?pubid=2011038) distributed by the United States National Center for Education Statistics (NCES). While the datasets are not supposed to contain identifying information about students taking the test, by using the data you are bound by the [NCES data use agreement]({{< baseurl >}}/resources/nces_data_use_agreement), which prohibits any attempt to determine the identity of any student in the datasets.

Each row in the datasets pisa2009train.csv and pisa2009test.csv represents one student taking the exam. The datasets have the following variables:

**grade:** The grade in school of the student (most 15-year-olds in America are in 10th grade)

**male:** Whether the student is male (1/0)

**raceeth:** The race/ethnicity composite of the student

**preschool:** Whether the student attended preschool (1/0)

**expectBachelors:** Whether the student expects to obtain a bachelor's degree (1/0)

**motherHS:** Whether the student's mother completed high school (1/0)

**motherBachelors:** Whether the student's mother obtained a bachelor's degree (1/0)

**motherWork:** Whether the student's mother has part-time or full-time work (1/0)

**fatherHS:** Whether the student's father completed high school (1/0)

**fatherBachelors:** Whether the student's father obtained a bachelor's degree (1/0)

**fatherWork:** Whether the student's father has part-time or full-time work (1/0)

**selfBornUS:** Whether the student was born in the United States of America (1/0)

**motherBornUS:** Whether the student's mother was born in the United States of America (1/0)

**fatherBornUS:** Whether the student's father was born in the United States of America (1/0)

**englishAtHome:** Whether the student speaks English at home (1/0)

**computerForSchoolwork:** Whether the student has access to a computer for schoolwork (1/0)

**read30MinsADay:** Whether the student reads for pleasure for 30 minutes/day (1/0)

**minutesPerWeekEnglish:** The number of minutes per week the student spend in English class

**studentsInEnglish:** The number of students in this student's English class at school

**schoolHasLibrary:** Whether this student's school has a library (1/0)

**publicSchool:** Whether this student attends a public school (1/0)

**urban:** Whether this student's school is in an urban area (1/0)

**schoolSize:** The number of students in this student's school

**readingScore:** The student's reading score, on a 1000-point scale

Problem 1.1 - Dataset size
--------------------------

Load the training and testing sets using the read.csv() function, and save them as variables with the names pisaTrain and pisaTest.

How many students are there in the training set?

Exercise 1

&nbsp;Numerical Response&nbsp;

Problem 1.2 - Summarizing the dataset
-------------------------------------

Using tapply() on pisaTrain, what is the average reading test score of males?

Exercise 2

&nbsp;Numerical Response&nbsp;

Of females?

Exercise 3

&nbsp;Numerical Response&nbsp;

Problem 1.3 - Locating missing values
-------------------------------------

{{< quiz_multiple_choice questionId="Q4_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;grade&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;male&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceeth&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;preschool&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;expectBachelors&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;motherHS&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;motherBachelors&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;motherWork&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;fatherHS&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;fatherBachelors&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;fatherWork&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;selfBornUS&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;motherBornUS&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;fatherBornUS&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;englishAtHome&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;computerForSchoolwork&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;read30MinsADay&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;minutesPerWeekEnglish&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;studentsInEnglish&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;schoolHasLibrary&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;publicSchool&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;urban&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;schoolSize&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;readingScore&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

We can read which variables have missing values from summary(pisaTrain). Because most variables are collected from study participants via survey, it is expected that most questions will have at least one missing value.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 1.4 - Removing missing values
-------------------------------------

Linear regression discards observations with missing data, so we will remove all such observations from the training and testing sets. Later in the course, we will learn about imputation, which deals with missing data by filling in missing values with plausible information.

Type the following commands into your R console to remove observations with any missing value from pisaTrain and pisaTest:

pisaTrain = na.omit(pisaTrain)

pisaTest = na.omit(pisaTest)

How many observations are now in the training set?

Exercise 5

&nbsp;Numerical Response&nbsp;

How many observations are now in the testing set?

Exercise 6

&nbsp;Numerical Response&nbsp;

Problem 2.1 - Factor variables
------------------------------

Factor variables are variables that take on a discrete set of values, like the "Region" variable in the WHO dataset from the second lecture of Unit 1. This is an unordered factor because there isn't any natural ordering between the levels. An ordered factor has a natural ordering between the levels (an example would be the classifications "large," "medium," and "small").

{{< quiz_multiple_choice questionId="Q7_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;grade&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;male&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceeth&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Male only has 2 levels (1 and 0). There is no natural ordering between the different values of raceeth, so it is an unordered factor. Meanwhile, we can order grades (8, 9, 10, 11, 12), so it is an ordered factor.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q8_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;grade&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;male&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;raceeth&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Male only has 2 levels (1 and 0). There is no natural ordering between the different values of raceeth, so it is an unordered factor. Meanwhile, we can order grades (8, 9, 10, 11, 12), so it is an ordered factor.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.2 - Unordered factors in regression models
----------------------------------------------------

To include unordered factors in a linear regression model, we define one level as the "reference level" and add a binary variable for each of the remaining levels. In this way, a factor with n levels is replaced by n-1 binary variables. The reference level is typically selected to be the most frequently occurring level in the dataset.

As an example, consider the unordered factor variable "color", with levels "red", "green", and "blue". If "green" were the reference level, then we would add binary variables "colorred" and "colorblue" to a linear regression problem. All red examples would have colorred=1 and colorblue=0. All blue examples would have colorred=0 and colorblue=1. All green examples would have colorred=0 and colorblue=0.

Now, consider the variable "raceeth" in our problem, which has levels "American Indian/Alaska Native", "Asian", "Black", "Hispanic", "More than one race", "Native Hawaiian/Other Pacific Islander", and "White". Because it is the most common in our population, we will select White as the reference level.

{{< quiz_multiple_choice questionId="Q9_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;raceethAmerican Indian/Alaska Native&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethAsian&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethBlack&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethHispanic&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethMore than one race&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethNative Hawaiian/Other Pacific Islander&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;raceethWhite&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

We create a binary variable for each level except the reference level, so we would create all these variables except for raceethWhite.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.3 - Example unordered factors
---------------------------------------

Consider again adding our unordered factor race to the regression model with reference level "White".

{{< quiz_multiple_choice questionId="Q10_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;raceethAmerican Indian/Alaska Native&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;raceethAsian&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethBlack&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethHispanic&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethMore than one race&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethNative Hawaiian/Other Pacific Islander&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

An Asian student will have raceethAsian set to 1 and all other raceeth binary variables set to 0. Because "White" is the reference level, a white student will have all raceeth binary variables set to 0.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q11_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;raceethAmerican Indian/Alaska Native&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethAsian&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethBlack&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethHispanic&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethMore than one race&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;raceethNative Hawaiian/Other Pacific Islander&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

An Asian student will have raceethAsian set to 1 and all other raceeth binary variables set to 0. Because "White" is the reference level, a white student will have all raceeth binary variables set to 0.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.1 - Building a model
------------------------------

Because the race variable takes on text values, it was loaded as a factor variable when we read in the dataset with read.csv() -- you can see this when you run str(pisaTrain) or str(pisaTest). However, by default R selects the first level alphabetically ("American Indian/Alaska Native") as the reference level of our factor instead of the most common level ("White"). Set the reference level of the factor by typing the following two lines in your R console:

pisaTrain$raceeth = relevel(pisaTrain$raceeth, "White")

pisaTest$raceeth = relevel(pisaTest$raceeth, "White")

Now, build a linear regression model (call it lmScore) using the training set to predict readingScore using all the remaining variables.

It would be time-consuming to type all the variables, but R provides the shorthand notation "readingScore ~ ." to mean "predict readingScore using all the other variables in the data frame." The period is used to replace listing out all of the independent variables. As an example, if your dependent variable is called "Y", your independent variables are called "X1", "X2", and "X3", and your training data set is called "Train", instead of the regular notation:

LinReg = lm(Y ~ X1 + X2 + X3, data = Train)

You would use the following command to build your model:

LinReg = lm(Y ~ ., data = Train)

What is the Multiple R-squared value of lmScore on the training set?

Exercise 12

&nbsp;Numerical Response&nbsp;

Note that this R-squared is lower than the ones for the models we saw in the lectures and recitation. This does not necessarily imply that the model is of poor quality. More often than not, it simply means that the prediction problem at hand (predicting a student's test score based on demographic and school-related variables) is more difficult than other prediction problems (like predicting a team's number of wins from their runs scored and allowed, or predicting the quality of wine from weather conditions).

Problem 3.2 - Computing the root-mean squared error of the model
----------------------------------------------------------------

What is the training-set root-mean squared error (RMSE) of lmScore?

Exercise 13

&nbsp;Numerical Response&nbsp;

Problem 3.3 - Comparing predictions for similar students
--------------------------------------------------------

{{< quiz_multiple_choice questionId="Q14_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;\-59.09&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;\-29.54&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;0&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;29.54&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;59.09&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;The difference cannot be determined without more information about the two students&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The coefficient 29.54 on grade is the difference in reading score between two students who are identical other than having a difference in grade of 1. Because A and B have a difference in grade of 2, the model predicts that student A has a reading score that is 2\*29.54 larger.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.4 - Interpreting model coefficients
---------------------------------------------

{{< quiz_multiple_choice questionId="Q15_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Predicted average reading score of an Asian student&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Difference between the average reading score of an Asian student and the average reading score of a white student&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Difference between the average reading score of an Asian student and the average reading score of all the students in the dataset&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Predicted difference in the reading score between an Asian student and a white student who is otherwise identical&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The only difference between an Asian student and white student with otherwise identical variables is that the former has raceethAsian=1 and the latter has raceethAsian=0. The predicted reading score for these two students will differ by the coefficient on the variable raceethAsian.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.5 - Identifying variables lacking statistical significance
--------------------------------------------------------------------

{{< quiz_multiple_choice questionId="Q16_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;grade&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;male&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;raceeth&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;preschool&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;expectBachelors&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;motherHS&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;motherBachelors&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;motherWork&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;fatherHS&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;fatherBachelors&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;fatherWork&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;selfBornUS&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;motherBornUS&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;fatherBornUS&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;englishAtHome&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;computerForSchoolwork&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;read30MinsADay&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;minutesPerWeekEnglish&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;studentsInEnglish&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;schoolHasLibrary&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;publicSchool&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;urban&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;schoolSize&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

From summary(lmScore), we can see which variables were significant at the 0.05 level. Because several of the binary variables generated from the race factor variable are significant, we should not remove this variable.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 4.1 - Predicting on unseen data
---------------------------------------

Using the "predict" function and supplying the "newdata" argument, use the lmScore model to predict the reading scores of students in pisaTest. Call this vector of predictions "predTest". Do not change the variables in the model (for example, do not remove variables that we found were not significant in the previous part of this problem). Use the summary function to describe the test set predictions.

What is the range between the maximum and minimum predicted reading score on the test set?

Exercise 17

&nbsp;Numerical Response&nbsp;

Problem 4.2 - Test set SSE and RMSE
-----------------------------------

What is the sum of squared errors (SSE) of lmScore on the testing set?

Exercise 18

&nbsp;Numerical Response&nbsp;

What is the root-mean squared error (RMSE) of lmScore on the testing set?

Exercise 19

&nbsp;Numerical Response&nbsp;

Problem 4.3 - Baseline prediction and test-set SSE
--------------------------------------------------

What is the predicted test score used in the baseline model? Remember to compute this value using the training set and not the test set.

Exercise 20

&nbsp;Numerical Response&nbsp;

What is the sum of squared errors of the baseline model on the testing set? HINT: We call the sum of squared errors for the baseline model the total sum of squares (SST).

Exercise 21

&nbsp;Numerical Response&nbsp;

Problem 4.4 - Test-set R-squared
--------------------------------

What is the test-set R-squared value of lmScore?

Exercise 22

&nbsp;Numerical Response&nbsp;

*   [BackAssignment 2]({{< baseurl >}}/pages/linear-regression/assignment-2)
*   [ContinueDetecting Flu Epidemics via Search Engine Query Data]({{< baseurl >}}/pages/linear-regression/assignment-2/detecting-flu-epidemics-via-search-engine-query-data)