---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: '1.3 Working with Data: An Introduction to R '
parent_type: CourseSection
parent_uid: 1ac933da-13d1-3dfa-2e38-03abf2d6971f
title: '1.3 Working with Data: An Introduction to R '
uid: 64119b70-3f1d-42bf-97ce-9f87d64a094c
---

*   [\<Video 6: Data Analysis - Plots and Summary Tables]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-6-data-analysis-plots-and-summary-tables)
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
*   [\>Video 7: Saving with Script Files]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-7-saving-with-script-files)

Quick Question
--------------

Use the tapply function to find the average child mortality rate of countries in each region.

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Africa&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Americas&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Eastern Mediterranean&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Europe&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;South-East Asia&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Western Pacific&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can find the average child mortaility rate of countries in each region by using the following command:

tapply(WHO$ChildMortality, WHO$Region, mean)

The output tells us that Europe has the lowest average child mortality rate across all countries, with an average of 10.05.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackVideo 6: Data Analysis - Plots and Summary Tables]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-6-data-analysis-plots-and-summary-tables)
*   [ContinueVideo 7: Saving with Script Files]({{< baseurl >}}/pages/an-introduction-to-analytics/working-with-data-an-introduction-to-r/video-7-saving-with-script-files)