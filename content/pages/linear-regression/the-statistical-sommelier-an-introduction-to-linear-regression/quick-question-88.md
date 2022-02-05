---
content_type: page
parent_title: '2.2 The Statistical Sommelier: An Introduction to Linear Regression'
parent_uid: 4495fb48-3934-3c33-23b2-2ef2104af559
title: '2.2 The Statistical Sommelier: An Introduction to Linear Regression'
uid: 20a0ee2d-c563-bbc1-243a-facac65c21f3
---

*   [\<Video 5: Understanding the Model]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/video-5-understanding-the-model)
*   [2.2.1Video 1: Predicting the Quality of Wine]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression)
*   [2.2.2Quick Question]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/quick-question-46)
*   [2.2.3Video 2: One-Variable Linear Regression]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/video-2-one-variable-linear-regression)
*   [2.2.4Quick Question]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/quick-question-54)
*   [2.2.5Video 3: Multiple Linear Regression]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/video-3-multiple-linear-regression)
*   [2.2.6Quick Question]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/quick-question-73)
*   [2.2.7Video 4: Linear Regression in R]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/video-4-linear-regression-in-r)
*   [2.2.8Quick Question]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/quick-question-78)
*   [2.2.9Video 5: Understanding the Model]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/video-5-understanding-the-model)
*   [2.2.10Quick Question]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/quick-question-88)
*   [2.2.11Video 6: Correlation and Multicollinearity]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/video-6-correlation-and-multicollinearity)
*   [2.2.12Quick Question]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/quick-question-96)
*   [2.2.13Video 7: Making Predictions]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/video-7-making-predictions)
*   [2.2.14Quick Question]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/quick-question-101)
*   [2.2.15Video 8: Comparing the Model to the Experts]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/video-8-comparing-the-model-to-the-experts)
*   [\>Video 6: Correlation and Multicollinearity]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/video-6-correlation-and-multicollinearity)

Quick Question
--------------

Use the dataset wine.csv to create a linear regression model to predict Price using HarvestRain and WinterRain as independent variables, like you did in the previous quick question. Using the summary output of this model, answer the following questions:

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Yes&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;No&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;I can't answer this question using the summary output.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can create the model and look at the summary output with the following command:

model = lm(Price ~ WinterRain + HarvestRain, data=wine)

summary(model)

From the summary output, you can see that HarvestRain is significant (two stars), but WinterRain is not (no stars).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Yes&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;No&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;I can't answer this question using the summary output.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can create the model and look at the summary output with the following command:

model = lm(Price ~ WinterRain + HarvestRain, data=wine)

summary(model)

From the summary output, you can see that HarvestRain is significant (two stars), but WinterRain is not (no stars).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Note that you will need to answer both questions before checking your answers.

*   [BackVideo 5: Understanding the Model]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/video-5-understanding-the-model)
*   [ContinueVideo 6: Correlation and Multicollinearity]({{< baseurl >}}/pages/linear-regression/the-statistical-sommelier-an-introduction-to-linear-regression/video-6-correlation-and-multicollinearity)