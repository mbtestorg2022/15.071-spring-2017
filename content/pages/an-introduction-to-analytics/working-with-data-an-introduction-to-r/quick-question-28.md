---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: '1.3 Working with Data: An Introduction to R '
parent_type: CourseSection
parent_uid: 1ac933da-13d1-3dfa-2e38-03abf2d6971f
title: '1.3 Working with Data: An Introduction to R '
uid: 85a26423-d9d7-5842-c382-af54b0eaaadd
---

*   [\<Video 5: Data Analysis - Summary Statistics and Scatterplots]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-5-data-analysis-summary-statistics-and-scatterplots)
*   [1.3.1Download and Install R]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r)
*   [1.3.2Video 1: Why R?]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-1-why-r)
*   [1.3.3Quick Question]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/quick-question)
*   [1.3.4Video 2: Getting Started in R]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-2-getting-started-in-r)
*   [1.3.5Quick Question]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/quick-question-4)
*   [1.3.6Video 3: Vectors and Data Frames]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-3-vectors-and-data-frames)
*   [1.3.7Quick Question]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/quick-question-9)
*   [1.3.8Video 4: Loading Data Files]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-4-loading-data-files)
*   [1.3.9Quick Question]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/quick-question-20)
*   [1.3.10Video 5: Data Analysis - Summary Statistics and Scatterplots]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-5-data-analysis-summary-statistics-and-scatterplots)
*   [1.3.11Quick Question]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/quick-question-28)
*   [1.3.12Video 6: Data Analysis - Plots and Summary Tables]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-6-data-analysis-plots-and-summary-tables)
*   [1.3.13Quick Question]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/quick-question-40)
*   [1.3.14Video 7: Saving with Script Files]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-7-saving-with-script-files)
*   [\>Video 6: Data Analysis - Plots and Summary Tables]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-6-data-analysis-plots-and-summary-tables)

Quick Question
--------------

Please answer the following questions using the entire data frame WHO (and not one of the subsets we have created in R).

What is the mean value of the "Over60" variable?

Exercise 1

&nbsp;Numerical Response&nbsp;

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Japan&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;United Arab Emirates (UAE)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Sierra Leone&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Cuba&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Luxembourg&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Mali&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

To get this value, you should type which.min(WHO$Over60) in your R console. The output is 183. Then, to see the name of the 183rd country in your data frame, type WHO$Country\[183\] in your R console. The output is United Arab Emirates.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q3_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Japan&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;United Arab Emirates (UAE)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Sierra Leone&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Cuba&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Luxembourg&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Mali&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

To get this value, you should type which.max(WHO$LiteracyRate) in your R console. The output is 44. Then, to see the name of the 44th country in your data frame, type WHO$Country\[44\] in your R console. The output is Cuba.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackVideo 5: Data Analysis - Summary Statistics and Scatterplots]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-5-data-analysis-summary-statistics-and-scatterplots)
*   [ContinueVideo 6: Data Analysis - Plots and Summary Tables]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-6-data-analysis-plots-and-summary-tables)