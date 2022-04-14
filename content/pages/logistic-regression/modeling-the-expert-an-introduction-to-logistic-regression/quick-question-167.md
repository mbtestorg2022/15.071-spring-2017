---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: '3.2 Modeling the Expert: An Introduction to Logistic Regression'
parent_type: CourseSection
parent_uid: 3063320a-4175-6b8a-4fa9-892f61b52c0d
title: '3.2 Modeling the Expert: An Introduction to Logistic Regression'
uid: 8c080206-9993-5e2b-b0c5-0c4cd73fd74c
---

*   [\<Video 4: Logistic Regression in R]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-4-logistic-regression-in-r)
*   [3.2.1Video 1: Replicating Expert Assessment]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression)
*   [3.2.2Video 2: Building the Dataset]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-2-building-the-dataset)
*   [3.2.3Quick Question]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/quick-question-144)
*   [3.2.4Video 3: Logistic Regression]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-3-logistic-regression)
*   [3.2.5Quick Question]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/quick-question-152)
*   [3.2.6Video 4: Logistic Regression in R]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-4-logistic-regression-in-r)
*   [3.2.7Quick Question]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/quick-question-167)
*   [3.2.8Video 5: Thresholding]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-5-thresholding)
*   [3.2.9Quick Question]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/quick-question-188)
*   [3.2.10Video 6: ROC Curves]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-6-roc-curves)
*   [3.2.11Quick Question]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/quick-question-200)
*   [3.2.12Video 7: Interpreting the Model]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-7-interpreting-the-model)
*   [3.2.13Quick Question]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/quick-question-208)
*   [3.2.14Video 8: The Analytics Edge]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-8-the-analytics-edge)
*   [\>Video 5: Thresholding]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-5-thresholding)

Quick Question
--------------

In R, create a logistic regression model to predict "PoorCare" using the independent variables "StartedOnCombination" and "ProviderCount". Use the training set we created in the previous video to build the model.

Note: If you haven't already loaded and split the data in R, please run these commands in your R console to load and split the data set. Remember to first navigate to the directory where you have saved "quality.csv".

quality = read.csv("quality.csv")

install.packages("caTools")

library(caTools)

set.seed(88)

split = sample.split(quality$PoorCare, SplitRatio = 0.75)

qualityTrain = subset(quality, split == TRUE)

qualityTest = subset(quality, split == FALSE)

Then recall that we built a logistic regression model to predict PoorCare using the R command:

QualityLog = glm(PoorCare ~ OfficeVisits + Narcotics, data=qualityTrain, family=binomial)

You will need to adjust this command to answer this question, and then look at the summary(QualityLog) output.

What is the coefficient for "StartedOnCombination"?

Exercise 1

&nbsp;Numerical Response&nbsp;

Quick Question
--------------

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Poor Care&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Good Care&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The coefficient value is positive, meaning that positive values of the variable make the outcome of 1 more likely. This corresponds to Poor Care.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackVideo 4: Logistic Regression in R]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-4-logistic-regression-in-r)
*   [ContinueVideo 5: Thresholding]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-5-thresholding)