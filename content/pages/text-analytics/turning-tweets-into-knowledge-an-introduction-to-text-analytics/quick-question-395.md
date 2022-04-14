---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: '5.2 Turning Tweets into Knowledge: An Introduction to Text Analytics'
parent_type: CourseSection
parent_uid: aea3bc9c-07f7-3648-65c4-6fec93dd8515
title: '5.2 Turning Tweets into Knowledge: An Introduction to Text Analytics'
uid: c08c448d-ba2f-6d4e-4aa3-a930b6c97c07
---

*   [\<Video 7: Predicting Sentiment]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-7-predicting-sentiment)
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
*   [\>Video 8: Conclusion]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-8-conclusion)

Quick Question
--------------

In the previous video, we used CART and Random Forest to predict sentiment. Let's see how well logistic regression does. Build a logistic regression model (using the training set) to predict "Negative" using all of the independent variables. You may get a warning message after building your model - don't worry (we explain what it means in the explanation).

Now, make predictions using the logistic regression model:

predictions = predict(tweetLog, newdata=testSparse, type="response")

where "tweetLog" should be the name of your logistic regression model. You might also get a warning message after this command, but don't worry, it is due to the same problem as the previous warning message.

Build a confusion matrix (with a threshold of 0.5) and compute the accuracy of the model. What is the accuracy?

Exercise 1

&nbsp;Numerical Response&nbsp;

Is this worse or better than the baseline model accuracy of 84.5%? Think about the properties of logistic regression that might make this the case!

*   [BackVideo 7: Predicting Sentiment]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-7-predicting-sentiment)
*   [ContinueVideo 8: Conclusion]({{< baseurl >}}/pages/text-analytics/turning-tweets-into-knowledge-an-introduction-to-text-analytics/video-8-conclusion)