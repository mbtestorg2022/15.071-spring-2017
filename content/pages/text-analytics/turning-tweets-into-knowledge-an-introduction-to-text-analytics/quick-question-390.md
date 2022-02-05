---
content_type: page
parent_title: '5.2 Turning Tweets into Knowledge: An Introduction to Text Analytics'
parent_uid: aea3bc9c-07f7-3648-65c4-6fec93dd8515
title: '5.2 Turning Tweets into Knowledge: An Introduction to Text Analytics'
uid: ef17614f-a013-2a73-a771-05ff3c4311af
---

*   [\<Video 6: Bag of Words in R]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-6-bag-of-words-in-r)
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
*   [\>Video 7: Predicting Sentiment]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-7-predicting-sentiment)

Quick Question
--------------

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;app&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;buy&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;freak&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;ipad&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;iphon&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;itun&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;like&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;love&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;new&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;think&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

To answer this question, you need to run the following command in R:

findFreqTerms(frequencies, lowfreq=100)

This outputs the words that appear at least 100 times in our tweets. They are "iphon", "itun", and "new".{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackVideo 6: Bag of Words in R]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-6-bag-of-words-in-r)
*   [ContinueVideo 7: Predicting Sentiment]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-7-predicting-sentiment)