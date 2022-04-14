---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: '7.2 Visualizing the World: An Introduction to Visualization'
parent_type: CourseSection
parent_uid: 274ac6b9-daf6-cd65-874e-c643ab327953
title: '7.2 Visualizing the World: An Introduction to Visualization'
uid: a7c29773-2c9a-e308-c35b-598232cd91c6
---

*   [\<Video 5: Advanced Scatterplots Using ggplot]({{< baseurl >}}/pages/visualization/visualizing-the-world-an-introduction-to-visualization/video-5-advanced-scatterplots-using-ggplot)
*   [7.2.1Video 1: The Power of Visualizations]({{< baseurl >}}/pages/visualization/visualizing-the-world-an-introduction-to-visualization)
*   [7.2.2Quick Question]({{< baseurl >}}/pages/visualization/visualizing-the-world-an-introduction-to-visualization/quick-question-505)
*   [7.2.3Video 2: The World Health Organization (WHO)]({{< baseurl >}}/pages/visualization/visualizing-the-world-an-introduction-to-visualization/video-2-the-world-health-organization-who)
*   [7.2.4Quick Question]({{< baseurl >}}/pages/visualization/visualizing-the-world-an-introduction-to-visualization/quick-question-510)
*   [7.2.5Video 3: What is Data Visualization?]({{< baseurl >}}/pages/visualization/visualizing-the-world-an-introduction-to-visualization/video-3-what-is-data-visualization)
*   [7.2.6Quick Question]({{< baseurl >}}/pages/visualization/visualizing-the-world-an-introduction-to-visualization/quick-question-515)
*   [7.2.7Video 4: Basic Scatterplots Using ggplot]({{< baseurl >}}/pages/visualization/visualizing-the-world-an-introduction-to-visualization/video-4-basic-scatterplots-using-ggplot)
*   [7.2.8Quick Question]({{< baseurl >}}/pages/visualization/visualizing-the-world-an-introduction-to-visualization/quick-question-526)
*   [7.2.9Video 5: Advanced Scatterplots Using ggplot]({{< baseurl >}}/pages/visualization/visualizing-the-world-an-introduction-to-visualization/video-5-advanced-scatterplots-using-ggplot)
*   [7.2.10Quick Question]({{< baseurl >}}/pages/visualization/visualizing-the-world-an-introduction-to-visualization/quick-question-531)
*   [\>The Analytical Policeman: Visualization for Law and Order]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order)

Quick Question
--------------

Create the fertility rate versus population under 15 plot again:

ggplot(WHO, aes(x = FertilityRate, y = Under15)) + geom\_point()

Now, color the points by the Region variable.

Note: You can add scale\_color\_brewer(palette="Dark2") to your plot if you are having a hard time distinguishing the colors (this color palette is often better if you are colorblind). To use this option, you should just add scale\_color\_brewer(palette="Dark2") to your plotting command right after geom\_point().

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Africa&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Americas&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Eastern Mediterranean&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Europe&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;South-East Asia&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Western Pacific&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can color the points by region if you adjust the command to the following:

ggplot(WHO, aes(x = FertilityRate, y = Under15, color=Region)) + geom\_point()

Most of the countries in Europe have a very low fertility rate and a very low percentage of the population under 15.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackVideo 5: Advanced Scatterplots Using ggplot]({{< baseurl >}}/pages/visualization/visualizing-the-world-an-introduction-to-visualization/video-5-advanced-scatterplots-using-ggplot)
*   [ContinueThe Analytical Policeman: Visualization for Law and Order]({{< baseurl >}}/pages/visualization/the-analytical-policeman-visualization-for-law-and-order)