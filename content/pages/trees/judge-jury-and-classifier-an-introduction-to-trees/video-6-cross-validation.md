---
content_type: page
parent_title: '4.2 Judge, Jury, and Classifier: An Introduction to Trees '
parent_uid: 11f9b44d-c296-0689-414b-8c313764a18d
title: '4.2 Judge, Jury, and Classifier: An Introduction to Trees '
uid: aed8634b-040d-d1af-7abb-68e999cb9c43
---

*   [\<Quick Question]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-297)
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
*   [\>Quick Question]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-306)

Video 6: Cross-Validation
-------------------------

**Important Note:** In this video, we install and load two new packages so that we can perform cross-validation: "caret", and "e1071". You may need to additionally install and load the following packages for cross-validation to work on your computer: "class" and "ggplot2". If you receive an error message after trying to load caret and e1071, please try installing and loading these two additional packages.

{{< resource 2c3b5765-3e27-972f-2133-56dd1c0025e1 >}}

Cross-Validation for Random Forests
-----------------------------------

You might be wondering why we used cross-validation on our CART model, but not on our random forest model. According to the creaters of the random forest algorithm, the model is not very sensitive to the parameters and therefore does not easily overfit to the training set. You can read more on [the Random Forests website](https://www.stat.berkeley.edu/~breiman/RandomForests/cc_home.htm). 

However, if you are interested in experimenting with the parameters of the random forest model more, you can read about the parameters and cross-validation for random forests in the ![This resource may not render correctly in a screen reader.](/images/inacessible.gif)[documentation for the randomForest package (PDF)](http://cran.r-project.org/web/packages/randomForest/randomForest.pdf).

*   [BackQuick Question]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-297)
*   [ContinueQuick Question]({{< baseurl >}}/pages/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-306)