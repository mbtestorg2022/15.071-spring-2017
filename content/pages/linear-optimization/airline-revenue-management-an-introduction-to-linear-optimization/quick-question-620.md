---
content_type: page
parent_title: '8.2 Airline Revenue Management: An Introduction to Linear Optimization '
parent_uid: 2900efa7-1aff-756d-feba-74c6d16f2d3d
title: '8.2 Airline Revenue Management: An Introduction to Linear Optimization '
uid: 866b08a8-38d4-f694-786a-619e9ebff44b
---

*   [\<Video 7: Connecting Flights]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-7-connecting-flights)
*   [8.2.1Video 1: Introduction]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization)
*   [8.2.2Video 2: A Single Flight]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-2-a-single-flight)
*   [8.2.3Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-581)
*   [8.2.4Video 3: The Problem Formulation]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-3-the-problem-formulation)
*   [8.2.5Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-590)
*   [8.2.6Video 4: Solving the Problem]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-4-solving-the-problem)
*   [8.2.7Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-598)
*   [8.2.8Video 5: Visualizing the Problem]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-5-visualizing-the-problem)
*   [8.2.9Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-606)
*   [8.2.10Video 6: Sensitivity Analysis]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-6-sensitivity-analysis)
*   [8.2.11Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-614)
*   [8.2.12Video 7: Connecting Flights]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-7-connecting-flights)
*   [8.2.13Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-620)
*   [8.2.14Video 8: The Edge of Revenue Management]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-8-the-edge-of-revenue-management)
*   [\>Video 8: The Edge of Revenue Management]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-8-the-edge-of-revenue-management)

Quick Question
--------------

In this quick question, we'll perform some sensitivity analysis on the connecting flights problem.

Previously, we said that American Airlines could market their fares to increase demand. It costs $200 in advertising to increase demand by one unit.

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Yes. American Airlines should market the discount fares from JFK to DFW to increase demand by 50.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Yes. American Airlines should market the discount fares from JFK to DFW to increase demand by 10.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;No. American Airlines should not market the discount fares from JFK to DFW because even though the revenue increases, it does not exceed the costs.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;No. American Airlines should not market the discount fares from JFK to DFW because the revenue does not increase at all by increasing the demand for these tickets.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can answer this question without re-solving the model by noticing that we are not meeting the demand for discount fares from JFK to DFW at all. The demand could increase by 100, and we still would not offer more than 11 discount fares.

Alternatively, you could change the demand for discount fares, and re-solve the model. The solution does not change, regardless of how much you increase the demand.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Yes. American Airlines should market the regular fares from JFK to LAX to increase demand by 50.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Yes. American Airlines should market the regular fares from JFK to LAX to increase demand by 10.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;No. American Airlines should not market the regular fares from JFK to LAX because even though the revenue increases, it does not exceed the costs.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;No. American Airlines should not market the regular fares from JFK to LAX because the revenue does not increase at all by increasing the demand for these tickets.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

In the current solution, we are meeting the demand for regular tickets from JFK to LAX. If we increase the demand by 10, we offer 10 more regular tickets, but our revenue only increases by $140, which does not exceed the cost of $2000. If we increase the demand by 50, to 130, we only offer 91 seats. Therefore, American Airlines should not market the regular fares from JFK to LAX because even though the revenue increases, it does not exceed the costs.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackVideo 7: Connecting Flights]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-7-connecting-flights)
*   [ContinueVideo 8: The Edge of Revenue Management]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-8-the-edge-of-revenue-management)