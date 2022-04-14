---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 7 Visualization
parent_type: CourseSection
parent_uid: ab87d151-cf8c-fe95-c873-e816df164d38
title: 7.5 Assignment 7
uid: 056c6914-368d-638a-59e4-cebbc43acfe5
---

*   [\<Video 7: Using Line Charts Instead]({{< baseurl >}}/pages/visualization/the-good-the-bad-and-the-ugly-visualization-recitation-recitation/video-7-using-line-charts-instead)
*   [7.5.1Visualizing Attributes of Parole Violators]({{< baseurl >}}/pages/visualization/assignment-7)
*   [\>Linear Optimization]({{< baseurl >}}/pages/linear-optimization)

Visualizing Attributes of Parole Violators
------------------------------------------

In the crime lecture, we saw how we can use heatmaps to give a 2-dimensional representation of 3-dimensional data: we made heatmaps of crime counts by time of the day and day of the week. In this problem, we'll learn how to use histograms to show counts by one variable, and then how to visualize 3 dimensions by creating multiple histograms.

We'll use the parole data [parole (CSV)]({{< baseurl >}}/resources/parole) from Unit 3. Before, we used this data to predict parole violators. Now, let's try to get a little more insight into this dataset using histograms. As a reminder, the variables in this dataset are:

*   **male** = 1 if the parolee is male, 0 if female
*   **race** = 1 if the parolee is white, 2 otherwise
    
*   **age** = the parolee's age in years at the time of release from prison
    
*   **state** = a code for the parolee's state. 2 is Kentucky, 3 is Louisiana, 4 is Virginia, and 1 is any other state. These three states were selected due to having a high representation in the dataset.
    
*   **time.served** = the number of months the parolee served in prison (limited by the inclusion criteria to not exceed 6 months).
    
*   **max.sentence** = the maximum sentence length for all charges, in months (limited by the inclusion criteria to not exceed 18 months).
    
*   **multiple.offenses** = 1 if the parolee was incarcerated for multiple offenses, 0 otherwise.
    
*   **crime** = a code for the parolee's main crime leading to incarceration. 2 is larceny, 3 is drug-related crime, 4 is driving-related crime, and 1 is any other crime.
    
*   **violator** \= 1 if the parolee violated the parole, and 0 if the parolee completed the parole without violation.
    

Problem 1.1 - Loading the Data
------------------------------

Using the read.csv function, load the dataset parole.csv and call it parole. Since male, state, and crime are all unordered factors, convert them to factor variables using the following commands:

parole$male = as.factor(parole$male)

parole$state = as.factor(parole$state)

parole$crime = as.factor(parole$crime)

What fraction of parole violators are female?

Exercise 1

&nbsp;Numerical Response&nbsp;

Problem 1.2 - Loading the Data
------------------------------

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Larceny&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Drug-related crime&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Driving-related crime&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Other&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

This can be found by using table:

table(parole$state, parole$crime)

The code 2 corresponds to Kentucky, and the most common crime is 3, which corresponds to Drug-related crime.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.1 - Creating a Basic Histogram
----------------------------------------

Recall from lecture that in ggplot, we need to specify the dataset, the aesthetic, and the geometry. To create a histogram, the geometry will be geom\_histogram. The data we'll use is parole, and the aesthetic will be the map from a variable to the x-axis of the histogram.

Create a histogram to find out the distribution of the age of parolees, by typing the following command in your R console (you might need to load the ggplot2 package first by typing library(ggplot2) in your R console):

ggplot(data = parole, aes(x = age)) + geom\_histogram()

By default, geom\_histogram divides the data into 30 bins. Change the width of the bins to 5 years by adding the argument "binwidth = 5" to geom\_histogram.

Note that by default, histograms create bins where the left endpoint is included in the bin, but the right endpoint isn't. So the first bin in this histogram represents parolees who are between 15 and 19 years old. The last bin in this histogram represents parolees who are between 65 and 69 years old.

{{< quiz_multiple_choice questionId="Q3_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;20-24&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;25-29&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;30-34&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;35-39&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can generate the histogram with a bin width of 5 with the command:

ggplot(data = parole, aes(x = age)) + geom\_histogram(binwidth=5)

The tallest bar corresponds to the age bracket with the most parolees, which is 20-24.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.2 - Creating a Basic Histogram
----------------------------------------

{{< quiz_multiple_choice questionId="Q4_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Changes the fill color of the bars&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Changes the background color of the plot&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Changes the outline color of the bars&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Changes the color of the axis labels &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can generate the histogram by typing:

ggplot(data = parole, aes(x = age)) + geom\_histogram(binwidth=5, color="blue")

Adding the color argument changes the outline color of the bars.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.1 - Adding Another Dimension
--------------------------------------

Now suppose we are interested in seeing how the age distribution of male parolees compares to the age distribution of female parolees.

One option would be to create a heatmap with age on one axis and male (a binary variable in our data set) on the other axis. Another option would be to stick with histograms, but to create a separate histogram for each gender. ggplot has the ability to do this automatically using the facet\_grid command.

To create separate histograms for male and female, type the following command into your R console:

ggplot(data = parole, aes(x = age)) + geom\_histogram(binwidth = 5) + facet\_grid(male ~ .)

The histogram for female parolees is shown at the top, and the histogram for male parolees is shown at the bottom.

{{< quiz_multiple_choice questionId="Q5_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;20-24&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;25-29&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;30-34&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;35-39&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Looking at the histogram at the top, we can see that the tallest bar corresponds to the age bracket 35-39.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.2 - Adding Another Dimension
--------------------------------------

{{< quiz_multiple_choice questionId="Q6_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Creates histograms of the male variable, sorted by the different values of age.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Puts the histograms side-by-side instead of on top of each other. &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;This doesn't change anything - the plot looks exactly the same as it did before.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can create the new plot with the command:

ggplot(data = parole, aes(x = age)) + geom\_histogram(binwidth = 5) + facet\_grid(.~male)

This puts the plots side-by-side instead of on top of each other.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.3 - Adding Another DImension
--------------------------------------

An alternative to faceting is to simply color the different groups differently. To color the data points by group, we need to tell ggplot that a property of the data (male or not male) should be translated to an aesthetic property of the histogram. We can do this by setting the fill parameter within the aesthetic to male.

Run the following command in your R console to produce a histogram where data points are colored by group:

ggplot(data = parole, aes(x = age, fill = male)) + geom\_histogram(binwidth = 5)

Since we didn't specify colors to use, ggplot will use its default color selection. Let's change this by defining our own color palette. First, type in your R console:

colorPalette = c("#000000", "#E69F00", "#56B4E9", "#009E73", "#F0E442", "#0072B2", "#D55E00", "#CC79A7")

This is actually a colorblind-friendly palette, desribed on this [Cookbook for R page](http://www.cookbook-r.com/Graphs/Colors_(ggplot2)/). Now, generate your histogram again, using colorPalette, with the following command:

ggplot(data = parole, aes(x = age, fill = male)) + geom\_histogram(binwidth = 5) + scale\_fill\_manual(values=colorPalette)

{{< quiz_multiple_choice questionId="Q7_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Orange&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Black&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

From the previous question, we saw that the female parolee histogram was much smaller than the male parolee histogram. So it looks like the female histogram is the black-colored one. We can also read this from the legend.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.4 - Adding Another Dimension
--------------------------------------

Coloring the groups differently is a good way to see the breakdown of age by sex within the single, aggregated histogram. However, the bars here are stacked, meaning that the height of the orange bars in each age bin represents the total number of parolees in that age bin, not just the number of parolees in that group.

An alternative to a single, stacked histogram is to create two histograms and overlay them on top of each other. This is a simple adjustment to our previous command.

We just need to:

1) Tell ggplot not to stack the histograms by adding the argument position="identity" to the geom\_histogram function.

2) Make the bars semi-transparent so we can see both colors by adding the argument alpha=0.5 to the geom\_histogram function.

Redo the plot, making both of these changes.

{{< quiz_multiple_choice questionId="Q8_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;15-19&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;20-24&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;25-29&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;30-34&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;35-39&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;40-44&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;45-49&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;50-54&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;55-59&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;60-64&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;65-69&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

This plot can be generated with the following command:

ggplot(parole, aes(x = age, fill = male)) + geom\_histogram(binwidth = 5, position = "identity", alpha = 0.5) + scale\_fill\_manual(values=colorPalette)

If you look at the plot, you can see that there are no female parolees in the age groups 15-19, 55-59, and 65-69 (the bars have height zero).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 4.1 - Time Served
-------------------------

Now let's explore another aspect of the data: the amount of time served by parolees. Create a basic histogram like the one we created in Problem 2, but this time with time.served on the x-axis. Set the bin width to one month.

{{< quiz_multiple_choice questionId="Q9_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Between 2 and 3 months&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Between 3 and 4 months&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Between 4 and 5 months&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Between 5 and 6 months&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can create this histogram with the following command:

ggplot(data = parole, aes(x = time.served)) + geom\_histogram(binwidth = 1)

The highest bar corresponds to between 4 and 5 months.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 4.2 - Time Served
-------------------------

{{< quiz_multiple_choice questionId="Q10_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Between 2.1 and 2.2 months&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Between 3.0 and 3.1 months&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Between 4.2 and 4.3 months &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Between 4.8 and 4.9 months&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can change the binwidth by using the following command:

ggplot(data = parole, aes(x = time.served)) + geom\_histogram(binwidth = .1)

Now, the highest bar corresponds to between 3.0 and 3.1 months.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Be careful when choosing the binwidth - it can significantly affect the interpretation of a histogram! When visualizing histograms, it is always a good idea to vary the bin size in order to understand the data at various granularities.

Problem 4.3 - Time Served
-------------------------

Now, suppose we suspect that it is unlikely that each type of crime has the same distribution of time served. To visualize this, change the binwidth back to 1 month, and use facet\_grid to create a separate histogram of time.served for each value of the variable crime.

{{< quiz_multiple_choice questionId="Q11_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Larceny&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Drug-related&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Driving-related&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Other&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

This histogram can be generated using the command:

ggplot(data = parole, aes(x = time.served)) + geom\_histogram(binwidth = 1) + facet\_grid(crime ~ .){{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q12_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Larceny&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Drug-related&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Driving-related&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Other&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

This histogram can be generated using the command:

ggplot(data = parole, aes(x = time.served)) + geom\_histogram(binwidth = 1) + facet\_grid(crime ~ .){{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 4.4 - Time Served
-------------------------

Now, instead of faceting the histograms, overlay them. Remember to set the position and alpha parameters so that the histograms are not stacked. Also, make sure to indicate that the fill aesthetic should be "crime".

{{< quiz_multiple_choice questionId="Q13_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;With four different groups, it can be hard to tell them apart when they are overlayed. &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;ggplot doesn't let us overlay plots with more than two groups.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Overlaying the plots doesn't allow us to observe which crime type is the most common.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can generate this plot with the following command:

ggplot(data=parole, aes(x=time.served, fill=crime)) + geom\_histograph(binwidth=1, position="identity", alpha=0.5)

While overlaying the plots is allowed and lets us observe some attributes of the plots like the most common crime type, it can be hard to tell them apart and if they have similar values it can be hard to read.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackVideo 7: Using Line Charts Instead]({{< baseurl >}}/pages/visualization/the-good-the-bad-and-the-ugly-visualization-recitation-recitation/video-7-using-line-charts-instead)
*   [ContinueLinear Optimization]({{< baseurl >}}/pages/linear-optimization)