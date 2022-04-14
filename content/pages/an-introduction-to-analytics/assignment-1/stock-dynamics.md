---
content_type: page
learning_resource_types:
- Assignments
ocw_type: CourseSection
parent_title: 1.5 Assignment 1
parent_type: CourseSection
parent_uid: 0af41c2f-ca68-84fa-b36c-0a31155319b9
title: 1.5 Assignment 1
uid: 89ce47d2-7edc-dd9b-8a8c-be641a59b520
---

*   [\<Assignment 1]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1)
*   [1.5.1An Analytical Detective]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1)
*   [1.5.2Stock Dynamics]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1/stock-dynamics)
*   [1.5.3Demographics and Employment in the United States]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1/demographics-and-employment-in-the-united-states)
*   [1.5.4Internet Privacy Poll]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1/internet-privacy-poll)
*   [\>Demographics and Employment in the United States]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1/demographics-and-employment-in-the-united-states)

Stock Dynamics
--------------

A stock market is where buyers and sellers trade shares of a company, and is one of the most popular ways for individuals and companies to invest money. The size of the world stock market  is now estimated to be in the trillions. The largest stock market in the world is the New York Stock Exchange (NYSE), located in New York City. About 2,800 companies are listed on the NSYE. In this problem, we'll look at the monthly stock prices of five of these companies: [IBM](http://www.ibm.com/), [General Electric (GE)](http://www.ge.com/), [Procter and Gamble](http://www.pg.com/), [Coca Cola](http://www.coca-cola.com), and [Boeing](http://www.boeing.com). The data used in this problem comes from [Infochimps](http://infochimps.org/).

Download and read the following files into R, using the read.csv function: [IBMStock (CSV)]({{< baseurl >}}/resources/ibmstock), [GEStock (CSV)]({{< baseurl >}}/resources/gestock), [ProcterGambleStock (CSV)]({{< baseurl >}}/resources/proctergamblestock), [CocaColaStock (CSV)]({{< baseurl >}}/resources/cocacolastock), and [BoeingStock (CSV)]({{< baseurl >}}/resources/boeingstock). (Do not open these files in any spreadsheet software before completing this problem because it might change the format of the Date field.)

Call the data frames "IBM", "GE", "ProcterGamble", "CocaCola", and "Boeing", respectively. Each data frame has two variables, described as follows:

*   **Date**: the date of the stock price, always given as the first of the month.
*   **StockPrice**: the average stock price of the company in the given month.

In this problem, we'll take a look at how the stock dynamics of these companies have changed over time.

Problem 1.1 - Summary Statistics
--------------------------------

Before working with these data sets, we need to convert the dates into a format that R can understand. Take a look at the structure of one of the datasets using the str function. Right now, the date variable is stored as a factor. We can convert this to a "Date" object in R by using the following five commands (one for each data set):

IBM$Date = as.Date(IBM$Date, "%m/%d/%y")

GE$Date = as.Date(GE$Date, "%m/%d/%y")

CocaCola$Date = as.Date(CocaCola$Date, "%m/%d/%y")

ProcterGamble$Date = as.Date(ProcterGamble$Date, "%m/%d/%y")

Boeing$Date = as.Date(Boeing$Date, "%m/%d/%y")

The first argument to the as.Date function is the variable we want to convert, and the second argument is the format of the Date variable. We can just overwrite the original Date variable values with the output of this function. Now, answer the following questions using the str and summary functions.

Our five datasets all have the same number of observations. How many observations are there in each data set?

Exercise 1

&nbsp;Numerical Response&nbsp;

Problem 1.2 - Summary Statistics
--------------------------------

What is the earliest year in our datasets?

Exercise 2

&nbsp;Numerical Response&nbsp;

Problem 1.3 - Summary Statistics
--------------------------------

What is the latest year in our datasets?

Exercise 3

&nbsp;Numerical Response&nbsp;

Problem 1.4 - Summary Statistics
--------------------------------

What is the mean stock price of IBM over this time period?

Exercise 4

&nbsp;Numerical Response&nbsp;

Problem 1.5 - Summary Statistics
--------------------------------

What is the minimum stock price of General Electric (GE) over this time period?

Exercise 5

&nbsp;Numerical Response&nbsp;

Problem 1.6 - Summary Statistics
--------------------------------

What is the maximum stock price of Coca-Cola over this time period?

Exercise 6

&nbsp;Numerical Response&nbsp;

Problem 1.7 - Summary Statistics
--------------------------------

What is the median stock price of Boeing over this time period?

Exercise 7

&nbsp;Numerical Response&nbsp;

Problem 1.8 - Summary Statistics
--------------------------------

What is the standard deviation of the stock price of Procter & Gamble over this time period?

Exercise 8

&nbsp;Numerical Response&nbsp;

Problem 2.1 - Visualizing Stock Dynamics
----------------------------------------

Let's plot the stock prices to see if we can visualize trends in stock prices during this time period. Using the plot function, plot the Date on the x-axis and the StockPrice on the y-axis, for Coca-Cola.

This plots our observations as points, but we would really like to see a line instead, since this is a continuous time period. To do this, add the argument type="l" to your plot command, and re-generate the plot (the character is quotes is the letter l, for line). You should now see a line plot of the Coca-Cola stock price.

{{< quiz_multiple_choice questionId="Q9_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;1973&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;1980&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;1985&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;1995&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;2008&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can generate the plot using the command plot(CocaCola$Date, CocaCola$StockPrice, type="l"). Looking at the plot, the maximum value of the StockPrice is around 1973, and the minimum value of the StockPrice is around 1980.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q10_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;1973&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;1980&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;1985&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;1995&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;2008&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can generate the plot using the command plot(CocaCola$Date, CocaCola$StockPrice, type="l"). Looking at the plot, the maximum value of the StockPrice is around 1973, and the minimum value of the StockPrice is around 1980.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.2 - Visualizing Stock Dynamics
----------------------------------------

Now, let's add the line for Procter & Gamble too. You can add a line to a plot in R by using the lines function instead of the plot function. Keeping the plot for Coca-Cola open, type in your R console:

lines(ProcterGamble$Date, ProcterGamble$StockPrice)

Unfortunately, it's hard to tell which line is which. Let's fix this by giving each line a color. First, re-run the plot command for Coca-Cola, but add the argument col="red". You should see the plot for Coca-Cola show up again, but this time in red. Now, let's add the Procter & Gamble line (using the lines function like we did before), adding the argument col="blue". You should now see in your plot the Coca-Cola stock price in red, and the Procter & Gamble stock price in blue.

As an alternative choice to changing the colors, you could instead change the line type of the Procter & Gamble line by adding the argument lty=2. This will make the Procter & Gamble line dashed.

{{< quiz_multiple_choice questionId="Q11_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Coca-Cola&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Procter and Gamble&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can generate the combined plot for Coca-Cola and Procter & Gamble by using the following commands in R:

plot(CocaCola$Date, CocaCola$StockPrice, type="l", col="red")

lines(ProcterGamble$Date, ProcterGamble$StockPrice, col="blue")

Looking at the plot, around 2000 both stocks drop, but Procter and Gamble's stock drops more.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

To answer this question and the ones that follow, you may find it useful to draw a vertical line at a certain date. To do this, type the command

abline(v=as.Date(c("2000-03-01")), lwd=2)

in your R console, with the plot still open. This generates a vertical line at the date March 1, 2000. The argument lwd=2 makes the line a little thicker. You can change the date in this command to generate the vertical line in different locations.

Problem 2.3 - Visualizing Stock Dynamics
----------------------------------------

Answer these questions using the plot you generated in the previous problem.

{{< quiz_multiple_choice questionId="Q12_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Coca-Cola&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Procter and Gamble&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Looking at the plot generated by the commands:

plot(CocaCola$Date, CocaCola$StockPrice, type="l", col="red")

lines(ProcterGamble$Date, ProcterGamble$StockPrice, col="blue")

we can see that around 1983 the stock for Coca-Cola has an upward trend.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q13_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Coca-Cola&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Procter and Gamble&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Looking at the plot, the red line (for Coca-Cola) is generally lower than the blue line.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.1 - Visualizing Stock Dynamics 1995-2005
--------------------------------------------------

Let's take a look at how the stock prices changed from 1995-2005 for all five companies. In your R console, start by typing the following plot command:

plot(CocaCola$Date\[301:432\], CocaCola$StockPrice\[301:432\], type="l", col="red", ylim=c(0,210))

This will plot the CocaCola stock prices from 1995 through 2005, which are the observations numbered from 301 to 432. The additional argument, ylim=c(0,210), makes the y-axis range from 0 to 210. This will allow us to see all of the stock values when we add in the other companies.

Now, use the lines function to add in the other four companies, remembering to only plot the observations from 1995 to 2005, or \[301:432\]. You don't need the "type" or "ylim" arguments for the lines function, but remember to make each company a different color so that you can tell them apart. Some color options are "red", "blue", "green", "purple", "orange", and "black". To see all of the color options in R, type colors() in your R console.

(If you prefer to change the type of the line instead of the color, here are some options for changing the line type: lty=2 will make the line dashed, lty=3 will make the line dotted, lty=4 will make the line alternate between dashes and dots, and lty=5 will make the line long-dashed.)

Use this plot to answer the following four questions.

{{< quiz_multiple_choice questionId="Q14_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Coca-Cola&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Procter and Gamble&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;IBM&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;General Electric (GE)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Boeing&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can create the plot needed to answer the questions in this problem by typing the following commands into your R console:

plot(CocaCola$Date\[301:432\], CocaCola$StockPrice\[301:432\], type="l", col="red", ylim=c(0,210))

lines(ProcterGamble$Date\[301:432\], ProcterGamble$StockPrice\[301:432\], col="blue")

lines(IBM$Date\[301:432\], IBM$StockPrice\[301:432\], col="green")

lines(GE$Date\[301:432\], GE$StockPrice\[301:432\], col="purple")

lines(Boeing$Date\[301:432\], Boeing$StockPrice\[301:432\], col="orange")

You can add a vertical line to the plot at March 2000 by typing the following command:

abline(v=as.Date(c("2000-03-01")), lwd=2)

By looking at this plot, you can see that the stock for General Electric falls significantly more than the other stocks after the technology bubble burst.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.2 - Visualizing Stock Dynamics 1995-2005
--------------------------------------------------

{{< quiz_multiple_choice questionId="Q15_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Coca-Cola&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Procter and Gamble&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;IBM&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;General Electric (GE)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Boeing&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Looking at the plot (see the previous explanation for how to create the plot), you can see that IBM has the highest value, around 1999.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.3 - Visualizing Stock Dynamics 1995-2005
--------------------------------------------------

{{< quiz_multiple_choice questionId="Q16_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Coca-Cola&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Procter and Gamble&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;IBM&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;General Electric (GE)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Boeing&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can create vertical lines at September 1997 and November 1997 with the following commands:

abline(v=as.Date(c("1997-09-01")), lwd=2)

abline(v=as.Date(c("1997-11-01")), lwd=2)

Looking at the plot, two companies had a decreasing trend in stock prices from September 1997 to November 1997: Boeing and Procter & Gamble.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.4 - Visualizing Stock Dynamics 1995-2005
--------------------------------------------------

{{< quiz_multiple_choice questionId="Q17_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Coca-Cola&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Procter and Gamble&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;IBM&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;General Electric (GE)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Boeing&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Looking at the plot, you can see that Boeing is steadily increasing from 2004 to the beginning of 2006.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 4.1 - Monthly Trends
----------------------------

Lastly, let's see if stocks tend to be higher or lower during certain months. Use the tapply command to calculate the mean stock price of IBM, sorted by months. To sort by months, use

months(IBM$Date)

as the second argument of the tapply function.

{{< quiz_multiple_choice questionId="Q18_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;January&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;February&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;March&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;April&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;May&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;June&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;July&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;August&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;September&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;October&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;November&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;December&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The overall average stock price for IBM is 144.375, which can be computed using the command mean(IBM$StockPrice). Comparing the monthly averages to this, using the command tapply(IBM$StockPrice, months(IBM$Date), mean), we can see that the price has historically been higher than average January - May, and lower than average during the remaining months.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 4.2 - Monthly Trends
----------------------------

Repeat the tapply function from the previous problem for each of the other four companies, and use the output to answer the remaining questions.

{{< quiz_multiple_choice questionId="Q19_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;January&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;February&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;March&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;April&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;May&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;June&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;July&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;August&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;September&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;October&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;November&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;December&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

You can see the monthly average stock prices for GE and Coca-Cola by using the commands:

tapply(GE$StockPrice, months(GE$Date), mean)

tapply(CocaCola$StockPrice, months(CocaCola$Date), mean)

General Electric has an average stock price of 64.48 in April, which is higher than any other month. Coca-Cola has an average stock price of 62.69 in April, which is higher than any other month.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 4.3 - Monthly Trends
----------------------------

{{< quiz_multiple_choice questionId="Q20_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;December&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;January&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

IBM has an average price of 140.76 in December, and 150.24 in January, which can be seen with the command:

tapply(IBM$StockPrice, months(IBM$Date), mean)

Having lower stock prices in December is a trend that holds for all five companies.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

After seeing these trends, we are ready to buy stock in certain months and sell it in others! But, we should be careful, because one really good or really bad year could skew the average to show a trend that is not really there in general.

*   [BackAssignment 1]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1)
*   [ContinueDemographics and Employment in the United States]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1/demographics-and-employment-in-the-united-states)