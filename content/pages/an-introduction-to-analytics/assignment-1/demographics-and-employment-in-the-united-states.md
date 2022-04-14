---
content_type: page
learning_resource_types:
- Assignments
ocw_type: CourseSection
parent_title: 1.5 Assignment 1
parent_type: CourseSection
parent_uid: 0af41c2f-ca68-84fa-b36c-0a31155319b9
title: 1.5 Assignment 1
uid: d628845f-dc26-781b-fce4-c58e39e14746
---

*   [\<Stock Dynamics]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1/stock-dynamics)
*   [1.5.1An Analytical Detective]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1)
*   [1.5.2Stock Dynamics]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1/stock-dynamics)
*   [1.5.3Demographics and Employment in the United States]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1/demographics-and-employment-in-the-united-states)
*   [1.5.4Internet Privacy Poll]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1/internet-privacy-poll)
*   [\>Internet Privacy Poll]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1/internet-privacy-poll)

Demographics and Employment in the United States
------------------------------------------------

In the wake of the Great Recession of 2009, there has been a good deal of focus on employment statistics, one of the most important metrics policymakers use to gauge the overall strength of the economy. In the United States, the government measures unemployment using [the Current Population Survey (CPS)](https://www.bls.gov/cps/), which collects demographic and employment information from a wide range of Americans each month. In this exercise, we will employ the topics reviewed in the lectures as well as a few new techniques using the September 2013 version of this rich, nationally representative dataset.

The observations in the dataset represent people surveyed in the September 2013 CPS who actually completed a survey. While the full dataset has 385 variables, in this exercise we will use a more compact version of the dataset, [CPSData (CSV)]({{< baseurl >}}/resources/cpsdata), which has the following variables:

**PeopleInHousehold**: The number of people in the interviewee's household.

**Region**: The census region where the interviewee lives.

**State**: The state where the interviewee lives.

**MetroAreaCode**: A code that identifies the metropolitan area in which the interviewee lives (missing if the interviewee does not live in a metropolitan area). The mapping from codes to names of metropolitan areas is provided in the file [MetroAreaCodes (CSV)]({{< baseurl >}}/resources/metroareacodes).

**Age**: The age, in years, of the interviewee. 80 represents people aged 80-84, and 85 represents people aged 85 and higher.

**Married**: The marriage status of the interviewee.

**Sex**: The sex of the interviewee.

**Education**: The maximum level of education obtained by the interviewee.

**Race**: The race of the interviewee.

**Hispanic**: Whether the interviewee is of Hispanic ethnicity.

**CountryOfBirthCode**: A code identifying the country of birth of the interviewee. The mapping from codes to names of countries is provided in the file [CountryCodes (CSV)]({{< baseurl >}}/resources/countrycodes).

**Citizenship**: The United States citizenship status of the interviewee.

**EmploymentStatus**: The status of employment of the interviewee.

**Industry**: The industry of employment of the interviewee (only available if they are employed).

Problem 1.1 - Loading and Summarizing the Dataset
-------------------------------------------------

Load the dataset from [CPSData (CSV)]({{< baseurl >}}/resources/cpsdata) into a data frame called CPS, and view the dataset with the summary() and str() commands.

How many interviewees are in the dataset?

Exercise 1

&nbsp;Numerical Response&nbsp;

Problem 1.2 - Loading and Summarizing the Dataset
-------------------------------------------------

Among the interviewees with a value reported for the Industry variable, what is the most common industry of employment? Please enter the name exactly how you see it.

Exercise 2

&nbsp;Text Response&nbsp; Answer:Educational and health services

Problem 1.3 - Loading and Summarizing the Dataset
-------------------------------------------------

Recall from the homework assignment "The Analytical Detective" that you can call the sort() function on the output of the table() function to obtain a sorted breakdown of a variable. For instance, sort(table(CPS$Region)) sorts the regions by the number of interviewees from that region.

Which state has the fewest interviewees?

Exercise 3

&nbsp;Text Response&nbsp; Answer:New Mexico

Which state has the largest number of interviewees?

Exercise 4

&nbsp;Text Response&nbsp; Answer:California

Problem 1.4 - Loading and Summarizing the Dataset
-------------------------------------------------

What proportion of interviewees are citizens of the United States?

Exercise 5

&nbsp;Numerical Response&nbsp;

Problem 1.5 - Loading and Summarizing the Dataset
-------------------------------------------------

{{< quiz_multiple_choice questionId="Q6_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;American Indian&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Asian&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Black&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Multiracial&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Pacific Islander&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;White&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The breakdown of race and Hispanic ethnicity can be obtained with table(CPS$Race, CPS$Hispanic).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.1 - Evaluating Missing Values
---------------------------------------

{{< quiz_multiple_choice questionId="Q7_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;PeopleInHousehold&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Region&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;State&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;MetroAreaCode&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Age&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Married&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Sex&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Education&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Race&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Hispanic&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;CountryOfBirthCode&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Citizenship&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;EmploymentStatus&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Industry&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

This can be read from the output of summary(CPS).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.2 - Evaluating Missing Values
---------------------------------------

{{< quiz_multiple_choice questionId="Q8_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;The Married variable being missing is related to the Region value for the interviewee.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;The Married variable being missing is related to the Sex value for the interviewee.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;The Married variable being missing is related to the Age value for the interviewee.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;The Married variable being missing is related to the Citizenship value for the interviewee.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;The Married variable being missing is not related to the Region, Sex, Age, or Citizenship value for the interviewee.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

We can test the relationship between these four variable values and whether the Married variable is missing with the following commands:

table(CPS$Region, is.na(CPS$Married))

table(CPS$Sex, is.na(CPS$Married))

table(CPS$Age, is.na(CPS$Married))

table(CPS$Citizenship, is.na(CPS$Married))

For each possible value of Region, Sex, and Citizenship, there are both interviewees with missing and non-missing Married values. However, Married is missing for all interviewees Aged 0-14 and is present for all interviewees aged 15 and older. This is because the CPS does not ask about marriage status for interviewees 14 and younger.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.3 - Evaluating Missing Values
---------------------------------------

As mentioned in the variable descriptions, MetroAreaCode is missing if an interviewee does not live in a metropolitan area. Using the same technique as in the previous question, answer the following questions about people who live in non-metropolitan areas.

How many states had all interviewees living in a non-metropolitan area (aka they have a missing MetroAreaCode value)? For this question, treat the District of Columbia as a state (even though it is not technically a state).

Exercise 9

&nbsp;Numerical Response&nbsp;

How many states had all interviewees living in a metropolitan area? Again, treat the District of Columbia as a state.

Exercise 10

&nbsp;Numerical Response&nbsp;

Problem 2.4 - Evaluating Missing Values
---------------------------------------

{{< quiz_multiple_choice questionId="Q11_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Midwest&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Northeast&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;South&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;West&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

To evaluate the number of interviewees not living in a metropolitan area, broken down by region, we can run table(CPS$Region, is.na(CPS$MetroAreaCode)). We can then compute the proportion of interviewees in each region that live in a non-metropolitan area: 34.8% in the Midwest, 21.6% in the Northeast, 23.8% in the South, and 24.4% in the West.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.5 - Evaluating Missing Values
---------------------------------------

While we were able to use the table() command to compute the proportion of interviewees from each region not living in a metropolitan area, it was somewhat tedious (it involved manually computing the proportion for each region) and isn't something you would want to do if there were a larger number of options. It turns out there is a less tedious way to compute the proportion of values that are TRUE. The mean() function, which takes the average of the values passed to it, will treat TRUE as 1 and FALSE as 0, meaning it returns the proportion of values that are true. For instance, mean(c(TRUE, FALSE, TRUE, TRUE)) returns 0.75. Knowing this, use tapply() with the mean function to answer the following questions:

Which state has a proportion of interviewees living in a non-metropolitan area closest to 30%?

Exercise 12

&nbsp;Text Response&nbsp; Answer:Wisconsin

Which state has the largest proportion of non-metropolitan interviewees, ignoring states where all interviewees were non-metropolitan?

Exercise 13

&nbsp;Text Response&nbsp; Answer:Montana

Problem 3.1 - Integrating Metropolitan Area Data
------------------------------------------------

Codes like MetroAreaCode and CountryOfBirthCode are a compact way to encode factor variables with text as their possible values, and they are therefore quite common in survey datasets. In fact, all but one of the variables in this dataset were actually stored by a numeric code in the original CPS datafile.

When analyzing a variable stored by a numeric code, we will often want to convert it into the values the codes represent. To do this, we will use a dictionary, which maps the the code to the actual value of the variable. We have provided dictionaries [MetroAreaCodes.csv]({{< baseurl >}}/resources/metroareacodes) and [CountryCodes.csv]({{< baseurl >}}/resources/countrycodes), which respectively map MetroAreaCode and CountryOfBirthCode into their true values. Read these two dictionaries into data frames MetroAreaMap and CountryMap.

How many observations (codes for metropolitan areas) are there in MetroAreaMap?

Exercise 14

&nbsp;Numerical Response&nbsp;

How many observations (codes for countries) are there in CountryMap?

Exercise 15

&nbsp;Numerical Response&nbsp;

Problem 3.2 - Integrating Metropolitan Area Data
------------------------------------------------

To merge in the metropolitan areas, we want to connect the field MetroAreaCode from the CPS data frame with the field Code in MetroAreaMap. The following command merges the two data frames on these columns, overwriting the CPS data frame with the result:

CPS = merge(CPS, MetroAreaMap, by.x="MetroAreaCode", by.y="Code", all.x=TRUE)

The first two arguments determine the data frames to be merged (they are called "x" and "y", respectively, in the subsequent parameters to the merge function). by.x="MetroAreaCode" means we're matching on the MetroAreaCode variable from the "x" data frame (CPS), while by.y="Code" means we're matching on the Code variable from the "y" data frame (MetroAreaMap). Finally, all.x=TRUE means we want to keep all rows from the "x" data frame (CPS), even if some of the rows' MetroAreaCode doesn't match any codes in MetroAreaMap (for those familiar with database terminology, this parameter makes the operation a left outer join instead of an inner join).

Review the new version of the CPS data frame with the summary() and str() functions. What is the name of the variable that was added to the data frame by the merge() operation?

Exercise 16

&nbsp;Text Response&nbsp; Answer:MetroArea

How many interviewees have a missing value for the new metropolitan area variable? Note that all of these interviewees would have been removed from the merged data frame if we did not include the all.x=TRUE parameter.

Exercise 17

&nbsp;Numerical Response&nbsp;

Problem 3.3 - Integrating Metropolitan Area Data
------------------------------------------------

{{< quiz_multiple_choice questionId="Q18_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Atlanta-Sandy Springs-Marietta, GA&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Baltimore-Towson, MD&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Boston-Cambridge-Quincy, MA-NH&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;San Francisco-Oakland-Fremont, CA&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

From table(CPS$MetroArea), we can read that Boston-Cambridge-Quincy, MA-NH has the largest number of interviewees of these options, with 2229.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.4 - Integrating Metropolitan Area Data
------------------------------------------------

Which metropolitan area has the highest proportion of interviewees of Hispanic ethnicity? Hint: Use tapply() with mean, as in the previous subproblem. Calling sort() on the output of tapply() could also be helpful here.

Exercise 19

&nbsp;Text Response&nbsp; Answer:Laredo, TX

Problem 3.5 - Integrating Metropolitan Area Data
------------------------------------------------

Remembering that CPS$Race == "Asian" returns a TRUE/FALSE vector of whether an interviewee is Asian, determine the number of metropolitan areas in the United States from which at least 20% of interviewees are Asian.

Exercise 20

&nbsp;Numerical Response&nbsp;

Problem 3.6 - Integrating Metropolitan Area Data
------------------------------------------------

Normally, we would look at the sorted proportion of interviewees from each metropolitan area who have not received a high school diploma with the command:

sort(tapply(CPS$Education == "No high school diploma", CPS$MetroArea, mean))

However, none of the interviewees aged 14 and younger have an education value reported, so the mean value is reported as NA for each metropolitan area. To get mean (and related functions, like sum) to ignore missing values, you can pass the parameter na.rm=TRUE. Passing na.rm=TRUE to the tapply function, determine which metropolitan area has the smallest proportion of interviewees who have received no high school diploma.

Exercise 21

&nbsp;Text Response&nbsp; Answer:Iowa City, IA

Problem 4.1 - Integrating Country of Birth Data
-----------------------------------------------

Just as we did with the metropolitan area information, merge in the country of birth information from the CountryMap data frame, replacing the CPS data frame with the result. If you accidentally overwrite CPS with the wrong values, remember that you can restore it by re-loading the data frame from CPSData.csv and then merging in the metropolitan area information using the command provided in the previous subproblem.

What is the name of the variable added to the CPS data frame by this merge operation?

Exercise 22

&nbsp;Text Response&nbsp; Answer:Country

How many interviewees have a missing value for the new country of birth variable?

Exercise 23

&nbsp;Numerical Response&nbsp;

Problem 4.2 - Integrating Country of Birth Data
-----------------------------------------------

Among all interviewees born outside of North America, which country was the most common place of birth?

Exercise 24

&nbsp;Text Response&nbsp; Answer:Philippines

Problem 4.3 - Integrating Country of Birth Data
-----------------------------------------------

What proportion of the interviewees from the "New York-Northern New Jersey-Long Island, NY-NJ-PA" metropolitan area have a country of birth that is not the United States? For this computation, don't include people from this metropolitan area who have a missing country of birth.

Exercise 25

&nbsp;Numerical Response&nbsp;

Problem 4.4 - Integrating Country of Birth Data
-----------------------------------------------

{{< quiz_multiple_choice questionId="Q26_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Boston-Cambridge-Quincy, MA-NH&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Minneapolis-St Paul-Bloomington, MN-WI&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;New York-Northern New Jersey-Long Island, NY-NJ-PA&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Washington-Arlington-Alexandria, DC-VA-MD-WV&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

To obtain the number of TRUE values in a vector of TRUE/FALSE values, you can use the sum() function. For instance, sum(c(TRUE, FALSE, TRUE, TRUE)) is 3. Therefore, we can obtain counts of people born in a particular country living in a particular metropolitan area with:

sort(tapply(CPS$Country == "India", CPS$MetroArea, sum, na.rm=TRUE))

sort(tapply(CPS$Country == "Brazil", CPS$MetroArea, sum, na.rm=TRUE))

sort(tapply(CPS$Country == "Somalia", CPS$MetroArea, sum, na.rm=TRUE))

We see that New York has the most interviewees born in India (96), Boston has the most born in Brazil (18), and Minneapolis has the most born in Somalia (17).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q27_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Boston-Cambridge-Quincy, MA-NH&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Minneapolis-St Paul-Bloomington, MN-WI&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;New York-Northern New Jersey-Long Island, NY-NJ-PA&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Washington-Arlington-Alexandria, DC-VA-MD-WV&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

To obtain the number of TRUE values in a vector of TRUE/FALSE values, you can use the sum() function. For instance, sum(c(TRUE, FALSE, TRUE, TRUE)) is 3. Therefore, we can obtain counts of people born in a particular country living in a particular metropolitan area with:

sort(tapply(CPS$Country == "India", CPS$MetroArea, sum, na.rm=TRUE))

sort(tapply(CPS$Country == "Brazil", CPS$MetroArea, sum, na.rm=TRUE))

sort(tapply(CPS$Country == "Somalia", CPS$MetroArea, sum, na.rm=TRUE))

We see that New York has the most interviewees born in India (96), Boston has the most born in Brazil (18), and Minneapolis has the most born in Somalia (17).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q28_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Boston-Cambridge-Quincy, MA-NH&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Minneapolis-St Paul-Bloomington, MN-WI&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;New York-Northern New Jersey-Long Island, NY-NJ-PA&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Washington-Arlington-Alexandria, DC-VA-MD-WV&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

To obtain the number of TRUE values in a vector of TRUE/FALSE values, you can use the sum() function. For instance, sum(c(TRUE, FALSE, TRUE, TRUE)) is 3. Therefore, we can obtain counts of people born in a particular country living in a particular metropolitan area with:

sort(tapply(CPS$Country == "India", CPS$MetroArea, sum, na.rm=TRUE))

sort(tapply(CPS$Country == "Brazil", CPS$MetroArea, sum, na.rm=TRUE))

sort(tapply(CPS$Country == "Somalia", CPS$MetroArea, sum, na.rm=TRUE))

We see that New York has the most interviewees born in India (96), Boston has the most born in Brazil (18), and Minneapolis has the most born in Somalia (17).{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackStock Dynamics]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1/stock-dynamics)
*   [ContinueInternet Privacy Poll]({{< baseurl >}}/pages/an-introduction-to-analytics/assignment-1/internet-privacy-poll)