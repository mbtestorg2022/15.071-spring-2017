---
content_type: page
parent_title: '7.3 The Analytical Policeman: Visualization for Law and Order'
parent_uid: 716f78f6-1fe6-c5f4-7370-d7a3c4127827
title: '7.3 The Analytical Policeman: Visualization for Law and Order'
uid: e685ba71-8462-a41f-dc85-159d8c6cd469
---

*   [\<Video 3: A Line Plot]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/video-3-a-line-plot)
*   [7.3.1Video 1: Predictive Policing]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order)
*   [7.3.2Quick Question]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/quick-question-540)
*   [7.3.3Video 2: Visualizing Crime Over Time]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/video-2-visualizing-crime-over-time)
*   [7.3.4Quick Question]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/quick-question-545)
*   [7.3.5Video 3: A Line Plot]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/video-3-a-line-plot)
*   [7.3.6Quick Question]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/quick-question-550)
*   [7.3.7Video 4: A Heatmap]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/video-4-a-heatmap)
*   [7.3.8Quick Question]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/quick-question-559)
*   [7.3.9Video 5: A Geographical Hot Spot Map]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/video-5-a-geographical-hot-spot-map)
*   [7.3.10Quick Question]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/quick-question-567)
*   [7.3.11Video 6: A Heatmap on the United States]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/video-6-a-heatmap-on-the-united-states)
*   [7.3.12Quick Question]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/quick-question-575)
*   [7.3.13Video 7: The Analytics Edge]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/video-7-the-analytics-edge)
*   [\>Video 4: A Heatmap]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/video-4-a-heatmap)

Quick Question
--------------

Create a new line plot, like the one in Video 3, but add the argument "linetype=2". So the geom\_line part of the plotting command should look like:

geom\_line(aes(group=1), linetype=2)

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Makes the line thicker&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Changes the color of the line to blue&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Makes the line dashed&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Makes the line lighter in color&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The linetype parameter makes the line dashed, and the alpha parameter makes the line lighter in color, or more transparent. The two plots can be generated with the following commands:

ggplot(WeekdayCounts, aes(x = Var1, y = Freq)) + geom\_line(aes(group=1), linetype=2) + xlab("Day of the Week") + ylab("Total Motor Vehicle Thefts")

ggplot(WeekdayCounts, aes(x = Var1, y = Freq)) + geom\_line(aes(group=1), alpha=0.3) + xlab("Day of the Week") + ylab("Total Motor Vehicle Thefts"){{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Makes the line thicker&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Changes the color of the line to blue&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Makes the line dashed&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Makes the line lighter in color&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The linetype parameter makes the line dashed, and the alpha parameter makes the line lighter in color, or more transparent. The two plots can be generated with the following commands:

ggplot(WeekdayCounts, aes(x = Var1, y = Freq)) + geom\_line(aes(group=1), linetype=2) + xlab("Day of the Week") + ylab("Total Motor Vehicle Thefts")

ggplot(WeekdayCounts, aes(x = Var1, y = Freq)) + geom\_line(aes(group=1), alpha=0.3) + xlab("Day of the Week") + ylab("Total Motor Vehicle Thefts"){{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackVideo 3: A Line Plot]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/video-3-a-line-plot)
*   [ContinueVideo 4: A Heatmap]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order/video-4-a-heatmap)