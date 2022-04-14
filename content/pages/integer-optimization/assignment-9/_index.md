---
content_type: page
learning_resource_types: []
ocw_type: CourseSection
parent_title: 9 Integer Optimization
parent_type: CourseSection
parent_uid: db42b40a-d705-f431-a7e2-3a1d11cec341
title: 9.5 Assignment 9
uid: 2dbce7a6-bb37-17df-55b4-be0179616ad6
---

*   [\<Video 4: The Solution]({{< baseurl >}}/pages/integer-optimization/operating-room-scheduling-making-hospitals-run-smoothly-recitation/video-4-the-solution)
*   [9.5.1Even' Star Organic Farm Revisited]({{< baseurl >}}/pages/integer-optimization/assignment-9)
*   [9.5.2Gerrymandering New Mexico]({{< baseurl >}}/pages/integer-optimization/assignment-9/gerrymandering-new-mexico)
*   [\>Gerrymandering New Mexico]({{< baseurl >}}/pages/integer-optimization/assignment-9/gerrymandering-new-mexico)

Even' Star Organic Farm Revisited
---------------------------------

Last week in the "Even' Star Organic Farm" optional homework problem, we formulated and solved the problem faced by Brett Grohsgal, the founder of the organic farm in southern Maryland. This week, we'll use integer optimization to improve the formulation and model some new decisions faced by Brett. We'll be using the spreadsheet [EvenStarFarmRevisited (ODS)]({{< baseurl >}}/resources/evenstarfarmrevisited) for LibreOffice or OpenOffice, and [EvenStarFarmRevisited (XLSX)]({{< baseurl >}}/resources/evenstarfarmrevisited-1) for Microsoft Excel.

Problem 1.1 - Adjusting the Formulation
---------------------------------------

Last week, we saw that Brett has to pay an entry fee for each channel that he participates in. He could instead choose to not participate in a certain channel, and therefore not have to pay the entry fee. This week, we'll model this choice using binary variables to see if we can increase Brett's profit.

Add three new decision variables to your model: one for whether or not Brett participates in the restaurant channel, one for whether or not he participates in the farmers' market channel, and one for whether or not he participates in the CSA channel. (HINT: It will be easy to input your model into Solver if you add these decision variables in the row right below the current decision variable table.)

If Brett chooses not to participate in a channel, two things need to change in our model: (1) he does not have to pay the fixed cost to enter that channel, and (2) he can't sell any cases in that channel.

To remove the fixed cost, take a look at the objective function equation. You should see three terms each subtracting the fixed cost value from the total profit for one of the channels. Multiply each of these terms by the corresponding binary variable you just defined for that channel. Now, if the binary variable is equal to 1, Brett pays the fixed cost, but if the binary variable is equal to 0, Brett does not pay the fixed cost.

Set the value of each of your binary variables equal to 1 (Brett participates in all channels). You should see that the objective value is the same as our best objective value without the binary variables ($49,956.39).

Now, we need to add constraints to make sure that if Brett does not enter a channel (doesn't pay the entry cost), then he also does not sell any cases in this channel. And if he does enter a channel, then he can sell as many cases as he wants in that channel. We'll model this with a special type of logical constraint.

We know that Brett can’t sell more cases than he produced. What is the total number of cases Brett produced?

Exercise 1

&nbsp;Numerical Response&nbsp;

This is the maximum number of cases that Brett can sell in any channel. Call this number M. Add the following constraint to your model for restaurants:

Total number of cases sold to restaurants \\(\\leq\\) M\*(Binary variable for restaurants)

What does this constraint do? If the binary variable is equal to 1 (Brett does enter the channel), then he can sell up to M cases in that channel (because he can’t sell more than M cases, this constraint will not limit his sales in the restaurant channel). But if the binary variable is equal to 0 (Brett does not enter the channel), then he can't sell any cases in that channel (the total number of cases in that channel has to be less than or equal to 0).

Add similar constraints for the CSA channel, and the farmers' market channel, and then solve your model in LibreOffice. Be sure to add the new variables, and to indicate that the new variables are binary in the constraints section.

Problem 1.2 - Adjusting the Formulation
---------------------------------------

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Restaurants&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;CSA&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Farmers' Market&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The binary variables have value 1 for restaurants and CSA, but 0 for the Farmers' Market, meaning that he should enter the restaurant and CSA channel, but not the farmers' market channel.

Assuming that you added the new binary variables right below the current decision variables (in cells B34:D34) then the objective formula should now be:

SUMPRODUCT(B26:D33;C6:E13) - B19\*(SUM(B26:B33)/119) - B20\*B34 - C19\*(SUMPRODUCT(C26:C33;D6:D13)/400) - C20\*C34 - D20\*D34

And you should have added three new constraints:

Restaurant Cases: SUM(B26:B33) \<= 1820\*B34

CSA Cases: SUM(C26:C33) \<= 1820\*C34

Farmers' Market Cases: SUM(D26:D33) \<= 1820\*D34

Don't forget to indicate that the new decision variables are binary in the Solver, and that the objective should be maximized.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 1.3 - Adjusting the Formulation
---------------------------------------

How much extra profit does he gain now compared to before, when he was always entering all of the channels?

Exercise 3

&nbsp;Numerical Response&nbsp;

Problem 1.4 - Adjusting the Formulation
---------------------------------------

How many total cases of produce does Brett sell in the restaurant channel?

Exercise 4

&nbsp;Numerical Response&nbsp;

Answers will be marked correct within a 1% tolerance.

Problem 2.1 - Sensitivity Analysis
----------------------------------

{{< quiz_multiple_choice questionId="Q5_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;He could increase his prices.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;He could reduce the entry cost.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;He could reduce the variable costs.&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;He could buy a bigger truck to increase the number of cases he can sell.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Increasing his prices and/or reducing the entry cost for the farmers' market channel will increase his profits. Reducing the variables costs will not help since they are currently zero, and buying a bigger truck will not help since he currently does not even want to use the truck he has.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.2 - Sensitivity Analysis
----------------------------------

{{< quiz_multiple_choice questionId="Q6_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Increasing his prices at the farmers' market by 10%&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Increasing his prices at the farmers' market by 25%&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Reducing his entry cost to $5,000.00&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Reducing his entry cost to $3,000.00&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

If you increase the prices at the farmers' market by 10% and resolve the model, the solution does not change. However, if you increase the prices by 25%, the solution changes and it becomes profitable to enter the farmers' market channel. Reducing the entry cost to either $5,000 or $3,000 does not change the solution.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.3 - Sensitivity Analysis
----------------------------------

Suppose that Brett finds it easier to increase his prices than to reduce his entry cost, so he decides to increase his prices in the farmers' market by 25%. Make this adjustment in LibreOffice, and re-solve the model (remember to change any other values back to their original values if you have adjusted them to answer any previous questions).

What is the objective value in the new solution?

Exercise 7

&nbsp;Numerical Response&nbsp;

Problem 2.4 - Sensitivity Analysis
----------------------------------

{{< quiz_multiple_choice questionId="Q8_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;Tomatoes (large)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Tomatoes (small)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Watermelon&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Okra&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Basil&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;Cucumbers&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Sweet Potatoes&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Winter Squash&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

At the farmers' market, Brett should sell large tomatoes, sweet potatoes, and winter squash.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.5 - Sensitivity Analysis
----------------------------------

{{< quiz_multiple_choice questionId="Q9_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Restaurants&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;CSA&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;Farmers' Market&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The binary variables for CSA and the farmers' market are equal to 1, so he enters these two channels.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.6 - Sensitivity Analysis
----------------------------------

The decision variables for the number of cases can take fractional values. It seems impractical for Brett to sell a fractional number of cases of any produce at the farmers' market, and he would prefer to always sell an integer number of cases. Restrict the cases decision variables to be integer, and resolve the model. Does the objective value change?

{{< quiz_multiple_choice questionId="Q10_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;Yes&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;No&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

No, the objective value does not change. Note that your solution might have changed slightly, so Brett might have had to make some adjustments to his case allocation.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

In many situations, the decision variables should take integer values, but we often don't need to add the integer restriction (the solution gives integer values naturally). If this is the case, it is better to not include the integer restriction, since it is a simpler model. However, in some cases, like this one, we needed to add the integer restriction to our model.

Acknowledgements: This problem is based on the case study "[Introducing Integer Modeling with Excel Solver](https://pubsonline.informs.org/doi/10.1287/ited.7.1.88)" by Dessislava Pachamanova, _INFORMS Transactions on Education_ 7(1), p.88-98, 2006.

*   [BackVideo 4: The Solution]({{< baseurl >}}/pages/integer-optimization/operating-room-scheduling-making-hospitals-run-smoothly-recitation/video-4-the-solution)
*   [ContinueGerrymandering New Mexico]({{< baseurl >}}/pages/integer-optimization/assignment-9/gerrymandering-new-mexico)