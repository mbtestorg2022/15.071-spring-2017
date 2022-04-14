---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: '4.2 Judge, Jury, and Classifier: An Introduction to Trees '
parent_type: CourseSection
parent_uid: 11f9b44d-c296-0689-414b-8c313764a18d
title: '4.2 Judge, Jury, and Classifier: An Introduction to Trees '
uid: 8f336b6d-3260-d3a1-28f2-88e99dda1c42
---

*   [\<Video 4: CART in R]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/video-4-cart-in-r)
*   [4.2.1Video 1: The Supreme Court]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees)
*   [4.2.2Quick Question]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-253)
*   [4.2.3Video 2: CART]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/video-2-cart)
*   [4.2.4Quick Question]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-258)
*   [4.2.5Video 3: Splitting and Predictions]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/video-3-splitting-and-predictions)
*   [4.2.6Quick Question]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-267)
*   [4.2.7Video 4: CART in R]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/video-4-cart-in-r)
*   [4.2.8Quick Question]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-281)
*   [4.2.9Video 5: Random Forests]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/video-5-random-forests)
*   [4.2.10Quick Question]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-297)
*   [4.2.11Video 6: Cross-Validation]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/video-6-cross-validation)
*   [4.2.12Quick Question]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-306)
*   [4.2.13Video 7: The Model v. The Experts]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/video-7-the-model-v-the-experts)
*   [\>Video 5: Random Forests]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/video-5-random-forests)

Quick Question
--------------

Compute the AUC of the CART model from the previous video, using the following command in your R console:

as.numeric(performance(pred, "auc")@y.values)

What is the AUC?

Exercise 1

&nbsp;Numerical Response&nbsp;

Now, recall that in Video 4, our tree had 7 splits. Let's see how this changes if we change the value of minbucket.

First build a CART model that is similar to the one we built in Video 4, except change the minbucket parameter to 5. Plot the tree.

How many splits does the tree have?

Exercise 2

&nbsp;Numerical Response&nbsp;

Now build a CART model that is similar to the one we built in Video 4, except change the minbucket parameter to 100. Plot the tree.

How many splits does the tree have?

Exercise 3

&nbsp;Numerical Response&nbsp;

*   [BackVideo 4: CART in R]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/video-4-cart-in-r)
*   [ContinueVideo 5: Random Forests]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/video-5-random-forests)