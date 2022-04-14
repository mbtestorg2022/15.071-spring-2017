---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: '3.2 Modeling the Expert: An Introduction to Logistic Regression'
parent_type: CourseSection
parent_uid: 3063320a-4175-6b8a-4fa9-892f61b52c0d
title: '3.2 Modeling the Expert: An Introduction to Logistic Regression'
uid: d9817f81-c4ac-257a-ed44-548eaa714059
---

*   [\<Video 6: ROC Curves]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-6-roc-curves)
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
*   [\>Video 7: Interpreting the Model]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-7-interpreting-the-model)

Quick Question
--------------

This question will ask about the following ROC curve:

![]({{< resource_file 27296a79-a843-0f35-b099-68891f4d55bc >}})

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;t = 0.2&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;t = 0.3&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;t = 0.7&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;t = 0.8&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The threshold 0.7 is best to identify a small group of patients who are receiving the worst care with high confidence, since at this threshold we make very few false positive mistakes, and identify about 35% of the true positives. The threshold t = 0.8 is not a good choice, since it makes about the same number of false positives, but only identifies 10% of the true positives. The thresholds 0.2 and 0.3 both identify more of the true positives, but they make more false positive mistakes, so our confidence decreases.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;t = 0.2&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;t = 0.3&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;t = 0.7&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;t = 0.8&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The threshold 0.3 is the best choice in this scenerio. The threshold 0.2 also identifies over half of the patients receiving poor care, but it makes many more false positive mistakes. The thresholds 0.7 and 0.8 don't identify at least half of the patients receiving poor care.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackVideo 6: ROC Curves]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-6-roc-curves)
*   [ContinueVideo 7: Interpreting the Model]({{< baseurl >}}/pages/logistic-regression/modeling-the-expert-an-introduction-to-logistic-regression/video-7-interpreting-the-model)