---
content_type: page
parent_title: '5.2 Turning Tweets into Knowledge: An Introduction to Text Analytics'
parent_uid: aea3bc9c-07f7-3648-65c4-6fec93dd8515
title: '5.2 Turning Tweets into Knowledge: An Introduction to Text Analytics'
uid: 5e8b108b-e5fd-9320-8fe7-cd8bd5420c69
---

*   [<Video 3: Creating the Dataset]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-3-creating-the-dataset)
*   [5.2.1Video 1: Twitter]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics)
*   [5.2.2Video 2: Text Analytics]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-2-text-analytics)
*   [5.2.3Quick Question]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/quick-question-362)
*   [5.2.4Video 3: Creating the Dataset]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-3-creating-the-dataset)
*   [5.2.5Quick Question]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/quick-question-367)
*   [5.2.6Video 4: Bag of Words]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-4-bag-of-words)
*   [5.2.7Quick Question]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/quick-question-373)
*   [5.2.8Video 5: Pre-Processing in R]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-5-pre-processing-in-r)
*   [5.2.9Quick Question]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/quick-question-383)
*   [5.2.10Video 6: Bag of Words in R]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-6-bag-of-words-in-r)
*   [5.2.11Quick Question]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/quick-question-390)
*   [5.2.12Video 7: Predicting Sentiment]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-7-predicting-sentiment)
*   [5.2.13Quick Question]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/quick-question-395)
*   [5.2.14Video 8: Conclusion]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-8-conclusion)
*   [\>Video 4: Bag of Words]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-4-bag-of-words)

Quick Question
--------------

For each tweet, we computed an overall score by averaging all five scores assigned by the Amazon Mechanical Turk workers. However, Amazon Mechanical Turk workers might make significant mistakes when labeling a tweet. The mean could be highly affected by this.

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;An overall score equal to the median (middle) score&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;An overall score equal to the majority score&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;An overall score equal to the minimum score&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The correct answer is the first one - the median would capture the typical opinion of the workers and tends to be less affected by significant mistakes. The majority score might not have given a score to all tweets because they might not all have a majority score (consider a tweet with scores 0, 0, 1, 1, and 2). The minimum score does not necessarily capture the typical opinion and could be highly affected by mistakes (consider a tweet with scores -2, 1, 1, 1, 1).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackVideo 3: Creating the Dataset]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-3-creating-the-dataset)
*   [ContinueVideo 4: Bag of Words]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-4-bag-of-words)