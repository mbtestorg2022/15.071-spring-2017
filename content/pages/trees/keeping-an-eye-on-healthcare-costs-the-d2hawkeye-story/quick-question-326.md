---
content_type: page
parent_title: '4.3 Keeping an Eye on Healthcare Costs: The D2Hawkeye Story '
parent_uid: 52a221dd-c011-90a4-45b1-a393b15cb810
title: '4.3 Keeping an Eye on Healthcare Costs: The D2Hawkeye Story '
uid: c679795e-ed4f-1bd8-079e-7f008721cf38
---

*   [\<Video 4: Error Measures]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/video-4-error-measures)
*   [4.3.1Video 1: The Story of D2Hawkeye]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story)
*   [4.3.2Quick Question]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/quick-question-311)
*   [4.3.3Video 2: Claims Data]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/video-2-claims-data)
*   [4.3.4Quick Question]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/quick-question-316)
*   [4.3.5Video 3: The Variables]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/video-3-the-variables)
*   [4.3.6Quick Question]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/quick-question-321)
*   [4.3.7Video 4: Error Measures]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/video-4-error-measures)
*   [4.3.8Quick Question]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/quick-question-326)
*   [4.3.9Video 5: CART to Predict Cost]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/video-5-cart-to-predict-cost)
*   [4.3.10Quick Question]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/quick-question-337)
*   [4.3.11Video 6: Claims Data in R]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/video-6-claims-data-in-r)
*   [4.3.12Quick Question]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/quick-question-342)
*   [4.3.13Video 7: Baseline Method and Penalty Matrix]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/video-7-baseline-method-and-penalty-matrix)
*   [4.3.14Quick Question]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/quick-question-349)
*   [4.3.15Video 8: Predicting Healthcare Cost in R]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/video-8-predicting-healthcare-cost-in-r)
*   [4.3.16Quick Question]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/quick-question-357)
*   [4.3.17Video 9: Results]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/video-9-results)
*   [\>Video 5: CART to Predict Cost]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/video-5-cart-to-predict-cost)

Quick Question
--------------

The image below shows the penalty error matrix that we discussed in the previous video.

![]({{< resource_file 2d20a1e4-50f8-bd62-006b-f8e20477eb64 >}})

We can interpret this matrix as follows. Suppose the actual outcome for an observation is 3, and we predict 2. We find 3 on the top of the matrix, and go down to the second row (since we forecasted 2). The penalty error for this mistake is 2. If for another observation we predict (forecast) 4, but the actual outcome is 1, that is a penalty error of 3.

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;We predict 5 (very high cost), but the actual outcome is 1 (very low cost).&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;We predict 1 (very low cost), but the actual outcome is 5 (very high cost).&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The highest cost is 8, which occurs when the forecast is 1 (very low cost), but the actual cost is 5 (very high cost). It would be much worse for us to ignore an actual high cost observation than to accidentally predict high cost for someone who turns out to be low cost.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Mistakes where we predict one cost bucket HIGHER than the actual outcome.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Mistakes where we predict one cost bucket LOWER than the actual outcome.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

We are happier with mistakes where we predict one cost bucket higher than the actual outcome, since this just means we are being a little overly cautious.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackVideo 4: Error Measures]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/video-4-error-measures)
*   [ContinueVideo 5: CART to Predict Cost]({{< baseurl >}}/pages/trees/keeping-an-eye-on-healthcare-costs-the-d2hawkeye-story/video-5-cart-to-predict-cost)