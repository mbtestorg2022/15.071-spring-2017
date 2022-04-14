---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 5 Text Analytics
parent_type: CourseSection
parent_uid: 5847ad87-9afe-cf3e-9b93-c20cffe87acf
title: 5.5 Assignment 5
uid: 81eae0fd-28f2-8733-6b79-2210ba33dfbb
---

*   [\<Video 8: Predictive Coding Today]({{< baseurl >}}/pages/text-analytics/predictive-coding-bringing-text-analytics-to-the-courtroom-recitation/video-8-predictive-coding-today)
*   [5.5.1Separating Spam from Ham (Part 1)]({{< baseurl >}}/pages/text-analytics/assignment-5)
*   [5.5.2Detecting Vandalism on Wikipedia]({{< baseurl >}}/pages/text-analytics/assignment-5/detecting-vandalism-on-wikipedia)
*   [5.5.3Automating Reviews in Medicine]({{< baseurl >}}/pages/text-analytics/assignment-5/automating-reviews-in-medicine)
*   [\>Detecting Vandalism on Wikipedia]({{< baseurl >}}/pages/text-analytics/assignment-5/detecting-vandalism-on-wikipedia)

Separating Spam From Ham
------------------------

Nearly every email user has at some point encountered a "spam" email, which is an unsolicited message often advertising a product, containing links to malware, or attempting to scam the recipient. Roughly 80-90% of more than 100 billion emails sent each day are spam emails, most being sent from botnets of malware-infected computers. The remainder of emails are called "ham" emails.

As a result of the huge number of spam emails being sent across the Internet each day, most email providers offer a spam filter that automatically flags likely spam messages and separates them from the ham. Though these filters use a number of techniques (e.g. looking up the sender in a so-called "Blackhole List" that contains IP addresses of likely spammers), most rely heavily on the analysis of the contents of an email via text analytics.

In this homework problem, we will build and evaluate a spam filter using a publicly available dataset first described in the 2006 conference paper "Spam Filtering with Naive Bayes — Which Naive Bayes?" by V. Metsis, I. Androutsopoulos, and G. Paliouras. The "ham" messages in this dataset come from the inbox of former Enron Managing Director for Research Vincent Kaminski, one of the inboxes in the Enron Corpus. One source of spam messages in this dataset is the SpamAssassin corpus, which contains hand-labeled spam messages contributed by Internet users. The remaining spam was collected by Project Honey Pot, a project that collects spam messages and identifies spammers by publishing email address that humans would know not to contact but that bots might target with spam. The full dataset we will use was constructed as roughly a 75/25 mix of the ham and spam messages.

The dataset contains just two fields:

*   **text**: The text of the email.
*   **spam**: A binary variable indicating if the email was spam.

Problem 1.1 - Loading the Dataset
---------------------------------

Begin by loading the dataset [emails (CSV - 8.5MB)]({{< baseurl >}}/resources/emails) into a data frame called emails (don't open the file with Excel; import into R directly to avoid errors). Remember to pass the stringsAsFactors=FALSE option when loading the data.

How many emails are in the dataset?

Exercise 1

&nbsp;Numerical Response&nbsp;

Problem 1.2 - Loading the Dataset
---------------------------------

How many of the emails are spam?

Exercise 2

&nbsp;Numerical Response&nbsp;

Problem 1.3 - Loading the Dataset
---------------------------------

Which word appears at the beginning of every email in the dataset? Respond as a lower-case word with punctuation removed.

Exercise 3

&nbsp;Text Response&nbsp; Answer:subject

Problem 1.4 - Loading the Dataset
---------------------------------

{{< quiz_multiple_choice questionId="Q4_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;No -- the word appears in every email so this variable would not help us differentiate spam from ham.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Yes -- the number of times the word appears might help us differentiate spam from ham.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

We know that each email has the word "subject" appear at least once, but the frequency with which it appears might help us differentiate spam from ham. For instance, a long email chain would have the word "subject" appear a number of times, and this higher frequency might be indicative of a ham message.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 1.5 - Loading the Dataset
---------------------------------

The nchar() function counts the number of characters in a piece of text. How many characters are in the longest email in the dataset (where longest is measured in terms of the maximum number of characters)?

Exercise 5

&nbsp;Numerical Response&nbsp;

Problem 2.1 - Preparing the Corpus
----------------------------------

Follow the standard steps to build and pre-process the corpus:

1) Build a new corpus variable called corpus.

2) Using tm\_map, convert the text to lowercase.

3) Using tm\_map, remove all punctuation from the corpus.

4) Using tm\_map, remove all English stopwords from the corpus.

5) Using tm\_map, stem the words in the corpus.

6) Build a document term matrix from the corpus, called dtm.

If the code length(stopwords("english")) does not return 174 for you, then please run the line of code in [stopwords (TXT) file]({{< baseurl >}}/resources/stopwords-2), which will store the standard stop words in a variable called sw. When removing stop words, use tm\_map(corpus, removeWords, sw) instead of tm\_map(corpus, removeWords, stopwords("english")).

How many terms are in dtm?

Exercise 6

&nbsp;Numerical Response&nbsp;

Problem 2.2 - Preparing the Corpus
----------------------------------

To obtain a more reasonable number of terms, limit dtm to contain terms appearing in at least 5% of documents, and store this result as spdtm (don't overwrite dtm, because we will use it in a later step of this homework). How many terms are in spdtm?

Exercise 7

&nbsp;Numerical Response&nbsp;

Problem 3.1 - Building machine learning models
----------------------------------------------

First, create a variable called "emailsSparse" from "spdtm" using the command "emailsSparse = as.data.frame(as.matrix(spdtm))" and ensure it has legal variable names with "names(emailsSparse) = make.names(names(emailsSparse))". Then, copy the dependent variable from the original data frame called "emails" to "emailsSparse" using the command "emailsSparse$spam = as.factor(emails$spam)".

Next, set the random seed to 123 and use the sample.split function to split emailsSparse 70/30 into a training set called "train" and a testing set called "test". Make sure to perform this step on emailsSparse instead of emails.

Explanation

These steps can be accomplished with:

emailsSparse = as.data.frame(as.matrix(spdtm))

names(emailsSparse) = make.names(names(emailsSparse))

emailsSparse$spam = as.factor(emails$spam)

set.seed(123)

library(caTools)

spl = sample.split(emailsSparse$spam, 0.7)

library(dplyr)

train = emailsSparse %>% filter(spl == TRUE)

test = emailsSparse %>% filter(spl == FALSE)

Using the training set, train the following two machine learning models. The models should predict the dependent variable "spam", using all other available variables as independent variables. Please be patient, as these models may take a few minutes to train.

1) A CART model called spamCART, using the default parameters to train the model (don't worry about adding minbucket or cp or specifying losses for false positives and false negatives). Remember to add the argument method="class" since this is a binary classification problem.

2) A random forest model called spamRF, using the default parameters to train the model (don't worry about specifying mtry or ntree or nodesize or the losses for false positives and false negatives). Directly before training the random forest model, set the random seed to 123 (even though we've already done this earlier in the problem, it's important to set the seed right before training the model so we all obtain the same results. Keep in mind though that on certain operating systems, your results might still be slightly different).

Explanation

These models can be trained with the following code:

library(rpart)

spamCART = rpart(spam~., data=train, method="class")

set.seed(123)

library(randomForest)

spamRF = randomForest(spam~., data=train)

Similar to logistic regression, CART and random forest can be told to give you predicted probabilities for classification problems. CART does this by returning the proportion of observations in the bucket of interest that fall into the relevant category, and random forest does this by returning the proportion of the trees that predict the relevant category. The following commands can be used to obtain predicted probabilities for the two fitted models on the training set:

predTrainCART = predict(spamCART)\[,2\]

predTrainRF = predict(spamRF, type="prob")\[,2\]

What is the training set accuracy of spamCART, using a threshold of 0.5 for predictions?

Exercise 8

&nbsp;Numerical Response&nbsp;

What is the training set accuracy of spamRF, using a threshold of 0.5 for predictions? (Remember that your answer might not match ours exactly, due to random behavior in the random forest algorithm on different operating systems.)

Exercise 9

&nbsp;Numerical Response&nbsp;

Problem 3.2 - Building Machine Learning Models
----------------------------------------------

How many of the word stems "enron", "hou", "vinc", and "kaminski" appear in the CART tree? These are word stems likely specific to the inbox of Vincent Kaminski, whose email we used as the ham observations in our dataset.

Exercise 10

&nbsp;Numerical Response&nbsp;

Problem 3.3 - Building Machine Learning Models
----------------------------------------------

What is the training set AUC of spamCART? Note that now that we have predicted probabilities from the CART model, we can compute AUC with the ROCR package just as we have for logistic regression.

Exercise 11

&nbsp;Numerical Response&nbsp;

Problem 3.4 - Building Machine Learning Models
----------------------------------------------

What is the training set AUC of spamRF?

Exercise 12

&nbsp;Numerical Response&nbsp;

Problem 4.1 - Evaluating on the Test Set
----------------------------------------

Obtain predicted probabilities for the testing set for each of the models, again ensuring that probabilities instead of classes are obtained. This can be achieved with the following code:

predTestCART = predict(spamCART, newdata=test)\[,2\]

predTestRF = predict(spamRF, newdata=test, type="prob")\[,2\]

What is the testing set accuracy of spamCART, using a threshold of 0.5 for predictions?

Exercise 13

&nbsp;Numerical Response&nbsp;

Problem 4.2 - Evaluating on the Test Set
----------------------------------------

What is the testing set AUC of spamCART?

Exercise 14

&nbsp;Numerical Response&nbsp;

Problem 4.3 - Evaluating on the Test Set
----------------------------------------

What is the testing set accuracy of spamRF, using a threshold of 0.5 for predictions?

Exercise 15

&nbsp;Numerical Response&nbsp;

Problem 4.4 - Evaluating on the Test Set
----------------------------------------

What is the testing set AUC of spamRF?

Exercise 16

&nbsp;Numerical Response&nbsp;

Problem 4.5 - Evaluating on the Test Set
----------------------------------------

{{< quiz_multiple_choice questionId="Q17_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;CART&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Random forest&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The random forest outperformed CART in both measures, obtaining an impressive AUC of 0.998 on the test set.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

You may note that we did not ask you to fit a logistic regression model to predict whether an email was spam or ham. This is in contrast to our usual approach of comparing all three models. If you in fact tried to train a logistic regression model in R using this dataset, you would get the following warning:

**glm.fit: algorithm did not converge** 

This warning indicates that R's logistic regression solution procedure has failed.

*   [BackVideo 8: Predictive Coding Today]({{< baseurl >}}/pages/text-analytics/predictive-coding-bringing-text-analytics-to-the-courtroom-recitation/video-8-predictive-coding-today)
*   [ContinueDetecting Vandalism on Wikipedia]({{< baseurl >}}/pages/text-analytics/assignment-5/detecting-vandalism-on-wikipedia)