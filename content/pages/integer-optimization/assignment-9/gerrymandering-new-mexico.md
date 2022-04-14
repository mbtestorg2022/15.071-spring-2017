---
content_type: page
learning_resource_types:
- Assignments
ocw_type: CourseSection
parent_title: 9.5 Assignment 9
parent_type: CourseSection
parent_uid: 2dbce7a6-bb37-17df-55b4-be0179616ad6
title: 9.5 Assignment 9
uid: 1ab3f4de-f050-7a6b-6327-b8e7dfa4fb69
---

*   [\<Assignment 9]({{< baseurl >}}/pages/integer-optimization/assignment-9)
*   [9.5.1Even' Star Organic Farm Revisited]({{< baseurl >}}/pages/integer-optimization/assignment-9)
*   [9.5.2Gerrymandering New Mexico]({{< baseurl >}}/pages/integer-optimization/assignment-9/gerrymandering-new-mexico)

Gerrymandering New Mexico
-------------------------

In the United States, each state is divided into small regions called _districts_. In every even-numbered year, the citizens who reside in each district can vote in an election to determine the _representative_ of that district. The representative is a member of the House of Representatives, which is one of the two chambers of the Congress of the United States. Representatives hold great power, as they can propose and vote on bills that later can become laws. 

Each representative typically is affiliated with one of the two major political parties in the United States: the Democratic Party or the Republican Party. Each party naturally wants to ensure that they have as many representatives in Congress as possible. One way of achieving this is through _gerrymandering_.

Gerrymandering refers to the process of redrawing district boundaries so as to favor a particular political party. To illustrate this, suppose we have the hypothetical state below, with three districts. Each district is further subdivided along a grid into smaller subregions, where each subregion votes unanimously for either party. Suppose that in this hypothetical example, there is only one voter in each subregion.

![Example of a gerrymandering grid in which Blue wins.]({{< resource_file 2cc4ad88-5d21-56d8-9c14-e3848a5fb9dc >}})

Based on the current district boundaries, the blue party has a majority in each district, so each district elects a blue representative. However, suppose we decide to redraw the boundaries in the following way:

![Example of the same gerrymandering grid in which red wins.]({{< resource_file 96516b5e-431f-1672-ee8c-a633d2d2e93e >}})

Now the blue party does not win in every district; in fact, the red party wins two of the three districts. 

In this problem, we will be exploring how to systematically manipulate these kinds of boundaries. We will be doing this specifically for the state of New Mexico, which is one of the fifty states of the United States.

The Data
--------

The state of New Mexico, located in the south of the US, currently has three districts:

![Colored map showing New Mexico's congressional districts.]({{< resource_file a716bfa7-76b2-be85-f666-b0a4e6877f69 >}})

The state of New Mexico is also divided into counties:

![Map showing the outlines of New Mexico's counties.]({{< resource_file 47316383-de17-3f45-7bcc-8726c7c9aef7 >}})

Counties are administrative units that are typically smaller than districts. In many states counties are split across districts, but in this problem we will assume that the new districts we will design will be built from the existing counties. 

We have the voting record from the 2012 presidential election for each county in New Mexico. We will use the presidential election voting record of each county in 2012 as a proxy for how the county will vote in the next election for the house of representatives. This data is provided in [Gerrymandering (ODS)]({{< baseurl >}}/resources/gerrymandering) for LibreOffice and OpenOffice, or [Gerrymandering (XLSX)]({{< baseurl >}}/resources/gerrymandering-1) for Excel.

The Problem
-----------

In the 2012 House of Representatives election, the Democratic party won in New Mexico’s 1st and 3rd districts, while the Republican party won in the 2nd district. 

Suppose that we have the opportunity to gerrymander New Mexico, so that we still have three districts. Is there a way to redesign the three districts so that the Democratic party takes all three districts? 

This is the topic of our problem — and we will tackle it using integer optimization. Let’s formulate this problem as follows.

Our principal decision variables are \\(x\_{ij}\\) defined for each district \\(i\\) and each county \\(j\\), where \\(x\_{ij}\\) is 1 if county \\(j\\) is assigned to district \\(i\\) and 0 otherwise. 

The first scenario we will consider is selecting our objective to maximize the number of votes that the Democratic party wins district 2 by (remember that the Democratic party lost in the 2nd district). If we can get the Democratic party to win district 2 by a margin of at least 100 votes while still winning districts 1 and 3 by a margin of at least 100 votes in each district, the Democratic party will win all three districts.

With regard to constraints, we would like:

*   Each county to be assigned to exactly one district;
*   Each district to consist of at least one county; and
*   The Democratic party to still win districts 1 and 3 by a margin of at least 100 votes.

Problem 1.1 - The Objective
---------------------------

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;O1: maximize \\((D\_1 - R\_1) x\_{2,1} + (D\_2 - R\_2) x\_{2,2} + ... + (D\_{33} - R\_{33}) x\_{2,33}\\), where \\(D\_j\\) and \\(R\_j\\) are the numbers of Democratic and Republican votes, respectively, cast in county \\(j\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;O2: maximize \\(x\_{1,1} + x\_{1,2} + ... + x\_{1,33} + x\_{2,1} + ... + x\_{2,33} + x\_{3,1} + ... + x\_{3,33}\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;O3: maximize \\((D\_1 - R\_1) x\_{1,1} + (D\_2 - R\_2) x\_{1,2} + ... + (D\_{33} - R\_{33}) x\_{1,33}\\), where \\(D\_j\\) and \\(R\_j\\) are the numbers of Democratic and Republican votes, respectively, cast in county \\(j\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;O4: maximize \\(x\_{2,1} + ... + x\_{2,33}\\) &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

O1 is the correct objective function; the sum over all counties \\(i\\) of \\((D\_i - R\_i)x\_{2,i}\\) will be the number of votes that the Democratic party wins district 2 by.

O2 is not correct. O2 merely sums the assignment variables -- this expression does not capture by how much the Democratic Party wins district 2.

O3 is also incorrect. O3 is the same as O1, except that it computes the number of votes that the Democratic Party wins district 1 by.

O4 is also incorrect, because it just sums up the decision variables for district 2.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 1.2 - Assignment Constraints
------------------------------------

{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;C1: \\(x\_{1,1} + x\_{1,2} + ... + x\_{1,33} + x\_{2,1} + ... + x\_{2,33} + x\_{3,1} + ... + x\_{3,33} = 33\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;C2: \\(x\_{1,j} + x\_{2,j} + x\_{3,j} = 1\\), for \\(j = 1, ... , 33\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;C3: \\(x\_{i,1} + x\_{i,2} + ... + x\_{i,33} \\geq 1\\), for \\(i = 1, ..., 3\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;C4: \\(x\_{i,j} = 1,\\) for \\(i = 1, ..., 3\\), and \\(j = 1, ..., 33\\)&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

C2 is correct for the first question, and C3 is correct for the second question. C2 ensures that every county is assigned to one -- and only one -- district.

C3 says that the sum of \\(x\_{i,1}, x\_{i,2}, ... x\_{i,33}\\) is at least one; since the \\(x\_{i,j}\\)'s are binary, this means that for each district, there is at least one county j such that \\(x\_{i,j}\\) is 1. This is exactly the constraint that at least one county is assigned to every district.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q3_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;C1: \\(x\_{1,1} + x\_{1,2} + ... + x\_{1,33} + x\_{2,1} + ... + x\_{2,33} + x\_{3,1} + ... + x\_{3,33} = 33\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;C2: \\(x\_{1,j} + x\_{2,j} + x\_{3,j} = 1\\), for \\(j = 1, ... , 33\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;C3: \\(x\_{i,1} + x\_{i,2} + ... + x\_{i,33} \\geq 1\\), for \\(i = 1, ..., 3\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;C4: \\(x\_{i,j} = 1,\\) for \\(i = 1, ..., 3\\), and \\(j = 1, ..., 33\\)&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

C2 is correct for the first question, and C3 is correct for the second question. C2 ensures that every county is assigned to one -- and only one -- district.

C3 says that the sum of \\(x\_{i,1}, x\_{i,2}, ... x\_{i,33}\\) is at least one; since the \\(x\_{i,j}\\)'s are binary, this means that for each district, there is at least one county j such that \\(x\_{i,j}\\) is 1. This is exactly the constraint that at least one county is assigned to every district.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 1.3 - District 1 and 3 Constraints
------------------------------------------

We would also like to ensure that the Democratic Party still wins districts 1 and 3 (with a margin of 100 votes).

Remember that our data gives us for each county the difference \\(D\_i - R\_i\\), where \\(R\_i\\) is the number of votes cast for the Republican Party, and \\(D\_i\\) is the number of votes cast for the Democratic Party.

{{< quiz_multiple_choice questionId="Q4_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp; C1: \\((D\_1 - R\_1) x\_{1,1} + (D\_2 - R\_2) x\_{1,2} + ... + (D\_{33} - R\_{33}) x\_{1,33} \\geq 100\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; C2: \\((D\_1 - R\_1) x\_{1,1} +(D\_2 - R\_2) x\_{1,2} + ... + (D\_{33} - R\_{33}) x\_{1,33} \\geq 0\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp; C3: For each county j, \\(D\_j x\_{1,j} - R\_j x\_{1,j} \\geq 100\\)&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

The first option is the correct answer. The left hand side models the difference of Democratic and Republican votes in district 1, and the constraint says that this difference has to be at least 100.

The second option is incorrect. It requires that the difference in Democratic and Republican votes, in district 1, is nonnegative: in words, the Democratic party wins district 1. This is not what we want.

The third option is also incorrect. This is immediate from the fact that it is specified for each county; the left hand side does not model the difference between the votes cast in district 1.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

We'll need to add a similar constraint to our model for district 3.

Problem 2.1 - Solving the Problem
---------------------------------

Formulate the problem in LibreOffice and solve it. Use the decision variables, the objective and the constraints we defined above. For the vote difference \\(D\_j - R\_j\\), use the numbers given under the column "Scenario 1".

By how many votes does the Democratic Party win in district 2 under this redistricting?

Exercise 5

&nbsp;Numerical Response&nbsp;

Problem 2.2 - Adjusting the Objective
-------------------------------------

Given the data we have provided, it may seem that there are many ways to redistrict the state so that the Democratic Party wins in all three districts. However, some of the new proposals may not be very different from the existing districts, while some may require drastic changes to the boundaries.

In the spreadsheet, we have included information about the current districts, that is, which counties belong to which districts. (Note that this is an approximate assessment because in New Mexico, districts are not exactly made up of counties.)

{{< quiz_multiple_choice questionId="Q6_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;O1: maximize \\((x\_{1,1} - z\_{1,1}) + (x\_{1,2} - z\_{1,2}) + ... + (x\_{1,33} - z\_{1,33}) \\\\+ (x\_{2,1} - z\_{2,1}) + (x\_{2,2} - z\_{2,2}) + ... + (x\_{2,33} - z\_{2,33}) \\\\+ (x\_{3,1} - z\_{3,1}) + (x\_{3,2} - z\_{3,2}) + ... + (x\_{3,33} - z\_{3,33})\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;O2: minimize \\(z\_{1,1} x\_{1,1} + z\_{1,2} x\_{1,2} + ... + z\_{1,33} x\_{1,33} \\\\+ z\_{2,1} x\_{2,1} + z\_{2,2} x\_{2,2} + . . . + z\_{2,33} x\_{2,33} \\\\+ z\_{3,1} x\_{3,1} + z\_{3,2} x\_{3,2} + . . . + z\_{3,33} x\_{3,33}\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;O3: maximize \\(z\_{1,1} x\_{1,1} + z\_{1,2} x\_{1,2} + ... + z\_{1,33} x\_{1,33} \\\\+ z\_{2,1} x\_{2,1} + z\_{2,2} x\_{2,2} + . . . + z\_{2,33} x\_{2,33} \\\\+ z\_{3,1} x\_{3,1} + z\_{3,2} x\_{3,2} + . . . + z\_{3,33} x\_{3,33}\\) &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

O3 is the correct answer. To see this, fix a county j. If we consider the terms for county j, we have

\\\[z\_{1,j} x\_{1,j} + z\_{2,j} x\_{2,j} + z\_{3,j} x\_{3,j}\\\]

If the assignment of county j is the same in our proposal and in the current (2012) assignments, then this expression evaluates to one.

If the assignments of county j in our proposal and in the 2012 districts are different, then this expression evaluates to zero. In words, the sum is 0 if county j is assigned differently in the two assignments, and 1 if it is assigned the same way. If we now sum this over all i, as in O3, we get the total number of counties that we assigned the same as the existing 2012 districts. By maximizing this sum, we ensure that our proposal is as similar as possible to the existing 2012 districts.

O1 is not correct. The reason why is that for any solution, the value of this objective is the same.

O2 is not correct because it is minimizing instead of maximizing.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 2.3 - Re-Solving the Problem
------------------------------------

Modify your problem to include the new objective. The old objective should become a constraint like the ones we have for districts 1 and 3 - we want to ensure that the Democratic party wins by a margin of at least 100 votes in district 2 as well.

You should still be using the "Scenario 1" column for the vote differences.

Solve the problem. How many counties are NOT given new assignments (relative to the 2012 districts -- columns C through E in the spreadsheet) in this new solution?

Exercise 7

&nbsp;Numerical Response&nbsp;

Problem 2.4 - Understanding the Solution
----------------------------------------

{{< quiz_multiple_choice questionId="Q8_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;1 - Bernalillo&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;2 - Catron&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;3 - Chaves&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;4 - Cibola&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;5 - Colfax&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;6 - Curry&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;7 - DeBaca&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;8 - Dona Ana&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;9 - Eddy&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;10 - Grant&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;11 - Guadalupe&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;12 - Harding&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;13 - Hidalgo&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;14 - Lea&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;15 - Lincoln&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;16 - Los Alamos&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;17 - Luna&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;18 - McKinley&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;19 - Mora&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;20 - Otero&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;21 - Quay&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;22 - Rio Arriba&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;23 - Roosevelt&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;24 - Sandoval&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;25 - San Juan&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;26 - San Miguel&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;27 - Santa Fe&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;28 - Sierra&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;29 - Socorro&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;30 - Taos&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;31 - Torrance&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;32 - Union&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;33 - Valencia&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Simply compare the values in your assignment cells to the values in columns C through E. By doing this, the only county that has changed is Santa Fe.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

In addition to ensuring that the Democratic Party wins in each district, we also may have to take into account other considerations:

1.  Exactly one of Santa Fe (county 27) or Dona Ana (county 8) must be in district 2.
2.  Both Socorro (county 29) and Torrance (county 31) must be in the same district.

Problem 3.1 - A New Constraint
------------------------------

{{< quiz_multiple_choice questionId="Q9_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;C1: \\(x\_{2,27} + x\_{2,8} \\leq 1\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;C2: \\(x\_{2,27} + x\_{2,8} = 1\\) &nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;C3: \\(x\_{2,27} + x\_{2,8} = 2\\) &nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

C2 is the correct answer. There are only two ways that C2 can be satisfied: if \\(x\_{2,27} = 1\\) and \\(x\_{2,8} = 0\\) (Santa Fe is in district 2, and Dona Ana is not in district 2), or if \\(x\_{2,27} = 0\\) and \\(x\_{2,8} = 1\\) (Santa Fe is not in district 2, and Dona Ana is in district 2).

C1 is incorrect. The meaning of C1 is that at most one of counties 27 and 8 is in district 2.

C3 is also incorrect. C3 can only be satisfied if both Santa Fe and Dona Ana are in district 2. Clearly this is not what we want, so C3 is not appropriate.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.2 - A New Constraint
------------------------------

{{< quiz_multiple_choice questionId="Q10_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;C1: \\(x\_{1,29} + x\_{2,29} + x\_{3,29} = x\_{1,31} + x\_{2,31} + x\_{3,31}\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;C2: \\(x\_{1,29} + 2 x\_{2,29} + 3 x\_{3,29} = x\_{1,31} + 2 x\_{2,31} + 3 x\_{3,31}\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;C3: \\(x\_{1,29} = x\_{1,31}\\)&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;This constraint cannot be modeled using the variables of our model.&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

C2 is the correct answer. To see this, consider what the value of the left hand side will be. If county 29 is assigned to district 1, then \\(x\_{1,29}\\) is 1, and \\(x\_{2,29}\\) and \\(x\_{3,29}\\) are both 0, so the value of the left hand side is 1. If county 29 is assigned to district 2, then \\(x\_{2,29} = 1\\), and \\(x\_{1,29} = x\_{3,29} = 0\\), so the value is 2. If county 29 is assigned to district 3, then \\(x\_{3,29} = 1, x\_{1,29} = x\_{2,29} = 0\\), so the value is 3. In words, the left hand side exactly models the district to which county 29 is assigned. The right hand side similarly models the district to which county 31 is assigned. By setting these two values to be equal to each other, we ensure that county 29 and county 31 end up in the same district.

C1 is not correct. It can be satisfied by assigning counties 29 and 31 to different districts; for example, if \\(x\_{1,29} = 1\\) (so {\\(x\_{2,29} = x\_{3,29} = 0\\)) and if \\(x\_{2,31} = 1\\) (so \\(x\_{1,31} = x\_{3,31} = 0\\)), then the left hand side ends up being 1 and the right hand side ends up being 1, even though county 29 is in district 1 and county 31 is in district 2.

C3 is not correct. C3 requires that either both county 29 and 31 are in district 1, or both county 29 and 31 are not in district 1. This is in the right direction, but not quite what we want.

C4 is clearly not correct, as C2 is a valid way to model this constraint.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 3.3 - Re-Solving the Problem
------------------------------------

Add these two constraints and re-solve the problem. How many counties have been re-assigned (relative to the 2012 assignments in columns C through E of the spreadsheet)?

Exercise 11

&nbsp;Numerical Response&nbsp;

Problem 3.4 - Re-Assigned Counties
----------------------------------

{{< quiz_multiple_choice questionId="Q12_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;1 - Bernalillo&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;2 - Catron&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;3 - Chaves&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;4 - Cibola&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;5 - Colfax&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;6 - Curry&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;7 - DeBaca&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;8 - Dona Ana&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;9 - Eddy&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;10 - Grant&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;11 - Guadalupe&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;12 - Harding&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;13 - Hidalgo&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;14 - Lea&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;15 - Lincoln&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;16 - Los Alamos&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;17 - Luna&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;18 - McKinley&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;19 - Mora&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;20 - Otero&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;21 - Quay&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;22 - Rio Arriba&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;23 - Roosevelt&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;24 - Sandoval&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;25 - San Juan&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;26 - San Miguel&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;27 - Santa Fe&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;28 - Sierra&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;29 - Socorro&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;30 - Taos&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;31 - Torrance&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;32 - Union&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;33 - Valencia&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Simply compare the values in the cells containing your assignment decision variables to the values in columns C through E of the spreadsheet.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 4.1 - Voting Considerations
-----------------------------------

So far, we have been using only one voting scenario to design our districts. In this scenario, we’ve assumed that each county will vote in the representative election of its designated district the same way it voted in the 2012 presidential election (scenario 1 in the spreadsheet). For example, Bernalillo county will vote for the Democratic candidate of its district, with a margin of 42,941 more voters (i.e., the number of Democratic votes from Bernalillo is 42,941 higher than the number of Republican votes).

This is a problematic feature of the model, because voters will not vote in this exact way in future elections. In fact, if they vote sufficiently differently, the democratic party may not be able to win all of its representative elections.

{{< quiz_multiple_choice questionId="Q13_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;District 1&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;District 2&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;District 3&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Apply the SUMPRODUCT command using the assignments and the new margins. Doing this, we see that the difference between the Democratic votes and Republican votes in each of the districts are

District 1: -489 votes

District 2: 24899 votes

District 3: 51662 votes

Since district 1 is the only one where the difference is negative, this is the only district the Democrats lose.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 4.2 - Voting Scenarios
------------------------------

Let’s change our formulation to make it more robust to changes in voter behavior. Suppose that in addition to the data we have been using so far (based on the 2012 presidential election numbers), we also wish to account for two other scenarios: scenario 2 (which we just used in Problem 12) and scenario 3. These scenarios are based on forecasts obtained from a separate prediction model. Furthermore, we want to make sure that the Democratic party wins by a large margin, so we will change the constraints to ensure that the Democratic party wins at least 12,000 more votes than the republicans.

To do this, we need to revisit our constraints that ensure that the Democratic party wins each district. In particular, the Democratic Party should win each district with a margin of at least 12,000 votes in every scenario; so instead of three constraints (one for each district), we should have nine constraints (one for each district and scenario pair).

Add these constraints to the model, and re-solve it. How many counties have been re-assigned relative to the existing 2012 assignments (columns C through E in the spreadsheet)?

Exercise 14

&nbsp;Numerical Response&nbsp;

Problem 4.3 - Understanding the New Solution
--------------------------------------------

{{< quiz_multiple_choice questionId="Q15_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;1 - Bernalillo&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;2 - Catron&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;3 - Chaves&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;4 - Cibola&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;5 - Colfax&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;6 - Curry&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;7 - DeBaca&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;8 - Dona Ana&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;9 - Eddy&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;10 - Grant&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;11 - Guadalupe&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;12 - Harding&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;13 - Hidalgo&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;14 - Lea&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;15 - Lincoln&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;16 - Los Alamos&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;17 - Luna&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;18 - McKinley&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;19 - Mora&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;20 - Otero&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;21 - Quay&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;22 - Rio Arriba&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;23 - Roosevelt&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;24 - Sandoval&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;25 - San Juan&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;26 - San Miguel&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;27 - Santa Fe&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;28 - Sierra&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;29 - Socorro&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;30 - Taos&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;31 - Torrance&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;32 - Union&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;33 - Valencia&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Simply compare the values in the cells containing your assignment decision variables to the values in columns C through E of the spreadsheet.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

Problem 4.4 - Margin of Victory
-------------------------------

By what margin does the Democratic Party win in district 3 in Scenario 2?

Exercise 16

&nbsp;Numerical Response&nbsp;

By what margin does the Democratic Party win in district 1 in Scenario 3?

Exercise 17

&nbsp;Numerical Response&nbsp;

*   [BackAssignment 9]({{< baseurl >}}/pages/integer-optimization/assignment-9)