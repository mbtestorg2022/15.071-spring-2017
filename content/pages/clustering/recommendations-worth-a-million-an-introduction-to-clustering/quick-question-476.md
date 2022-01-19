---
content_type: page
parent_title: '6.2 Recommendations Worth a Million: An Introduction to Clustering '
parent_uid: b091b1be-c85a-85e0-60a8-3b7905c9dcce
title: '6.2 Recommendations Worth a Million: An Introduction to Clustering '
uid: 4d3cfab6-9136-623b-888a-5451d2fad159
---

*   [<Video 7: Hierarchical Clustering in R]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/video-7-hierarchical-clustering-in-r)
*   [6.2.1Video 1: Introduction to Netflix]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering)
*   [6.2.2Quick Question]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/quick-question-433)
*   [6.2.3Video 2: Recommendation Systems]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/video-2-recommendation-systems)
*   [6.2.4Quick Question]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/quick-question-438)
*   [6.2.5Video 3: Movie Data and Clustering]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/video-3-movie-data-and-clustering)
*   [6.2.6Quick Question]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/quick-question-446)
*   [6.2.7Video 4: Computing Distances]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/video-4-computing-distances)
*   [6.2.8Quick Question]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/quick-question-451)
*   [6.2.9Video 5: Hierarchical Clustering]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/video-5-hierarchical-clustering)
*   [6.2.10Quick Question]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/quick-question-458)
*   [6.2.11Video 6: Getting the Data]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/video-6-getting-the-data)
*   [6.2.12Quick Question]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/quick-question-466)
*   [6.2.13Video 7: Hierarchical Clustering in R]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/video-7-hierarchical-clustering-in-r)
*   [6.2.14Quick Question]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/quick-question-476)
*   [6.2.15Video 8: The Analytics Edge of Recommendation Systems]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/video-8-the-analytics-edge-of-recommendation-systems)
*   [\>Video 8: The Analytics Edge of Recommendation Systems]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/video-8-the-analytics-edge-of-recommendation-systems)

Quick Question
--------------

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Action&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Adventure&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Animation&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Children's&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Comedy&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Crime&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Documentary&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Drama&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Fantasy&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Film Noir&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Horror&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Musical&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Mystery&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Romance&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Sci-Fi&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Thriller&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;War&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Western&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can redo the cluster grouping with just two clusters by running the following command:

clusterGroups = cutree(clusterMovies, k = 2)

Then, by using the tapply function just like we did in the video, you can see the average value in each genre and cluster. It turns out that all of the movies in the second cluster belong to the drama genre.

Alternatively, you can use colMeans or lapply as explained below Video 7.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackVideo 7: Hierarchical Clustering in R]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/video-7-hierarchical-clustering-in-r)
*   [ContinueVideo 8: The Analytics Edge of Recommendation Systems]({{< baseurl >}}/pages/clustering/recommendations-worth-a-million-an-introduction-to-clustering/video-8-the-analytics-edge-of-recommendation-systems)