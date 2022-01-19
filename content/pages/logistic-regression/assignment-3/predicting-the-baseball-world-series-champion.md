---
content_type: page
parent_title: 3.5 Assignment 3
parent_uid: d4a650ea-930c-2c8c-0f98-9b353a5a342e
title: 3.5 Assignment 3
uid: 3b462833-7389-a83d-6609-7f7597856e56
---
<ul class="navigation pagination">
    <li id="top_bck_btn"><a href="./resolveuid/d4a650ea930c2c8c0f989b353a5a342e">&lt;<span>Assignment 3</span></a></li>
    <li id="flp_btn_1"><a href="./resolveuid/d4a650ea930c2c8c0f989b353a5a342e">3.5.1<span>Popularity of Music Records</span></a></li>
    <li id="flp_btn_2" class="button_selected"><a href="./resolveuid/3b4628337389a83d66097f7597856e56">3.5.2<span>Predicting the Baseball World Series Champion</span></a></li>
    <li id="top_continue_btn"><a href="./resolveuid/19c8cf92e31d034a1ea15ad53194d892">&gt;<span>Trees</span></a></li>
</ul>
<h2 class="subhead">Predicting the Baseball World Series Champion</h2>
<p>Last week, in the Moneyball lecture, we discussed how regular season performance is not strongly correlated with winning the World Series in baseball. In this homework question, we'll use the same data to investigate how well we can predict the World Series winner at the beginning of the playoffs.</p>
<p>To begin, load the dataset <span style="text-decoration: underline;"><a href="./resolveuid/20168d0dad9b53e072396f5168dc5290">baseball (CSV)</a></span>&nbsp;into R using the read.csv function, and call the data frame &quot;baseball&quot;. This is the same data file we used during the Moneyball lecture, and the data comes from <span style="text-decoration: underline;"><a href="http://www.baseball-reference.com/">Baseball-Reference.com</a></span>.</p>
<p>As a reminder, this dataset contains data concerning a baseball team's performance in a given year. It has the following variables:</p>
<ul>
    <li><b>Team</b>: A code for the name of the team</li>
    <li><b>League</b>: The Major League Baseball league the team belongs to, either AL (American League) or NL (National League)</li>
    <li><b>Year</b>: The year of the corresponding record</li>
    <li><b>RS</b>: The number of runs scored by the team in that year</li>
    <li><b>RA</b>: The number of runs allowed by the team in that year</li>
    <li><b>W</b>: The number of regular season wins by the team in that year</li>
    <li><b>OBP</b>: The on-base percentage of the team in that year</li>
    <li><b>SLG</b>: The slugging percentage of the team in that year</li>
    <li><b>BA</b>: The batting average of the team in that year</li>
    <li><b>Playoffs</b>: Whether the team made the playoffs in that year (1 for yes, 0 for no)</li>
    <li><b>RankSeason</b>: Among the playoff teams in that year, the ranking of their regular season records (1 is best)</li>
    <li><b>RankPlayoffs</b>: Among the playoff teams in that year, how well they fared in the playoffs. The team winning the World Series gets a RankPlayoffs of 1.</li>
    <li><b>G</b>: The number of games a team played in that year</li>
    <li><b>OOBP</b>: The team's opponents' on-base percentage in that year</li>
    <li><b>OSLG</b>: The team's opponents' slugging percentage in that year</li>
</ul>
<h2 class="subhead">Problem 1.1 - Limiting to Teams Making the Playoffs</h2>
<div class="self_assessment">
<p display_name="Problem 1.1 - Limiting to Teams Making the Playoffs" url_name="Problem_1_1_Limiting_to_Teams_Making_the_Playoffs_0">Each row in the baseball dataset represents a team in a particular year.</p>
<div id="Q1_div" class="problem_question">
<p display_name="Problem 1.1 - Limiting to Teams Making the Playoffs" url_name="Problem_1_1_Limiting_to_Teams_Making_the_Playoffs_1">How many team/year pairs are there in the whole dataset?</p>
<fieldset><legend class="visually-hidden">Exercise 1</legend>
<div class="choice"><label id="Q1_label"><span id="Q1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q1_input" value="" onkeypress="numericTypedOrDropDownSelected(1)" class="problem_text_input" /><input type="hidden" id="Q1_ans" value="1232" /><input type="hidden" id="Q1_tolerance" value="0" /><span id="Q1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S1_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="S1_div" class="problem_solution" tabindex="-1" display_name="Problem 1.1 - Limiting to Teams Making the Playoffs" url_name="Problem_1_1_Limiting_to_Teams_Making_the_Playoffs_3">
<div class="detailed-solution">
<p>Explanation</p>
<p>You can read the dataset into R by using the following command:</p>
<p>baseball = read.csv(&quot;baseball.csv&quot;)</p>
<p>Then nrow(baseball) or str(baseball) both show that there are 1232 team/year pairs.</p>
</div>
</div>
<div class="action"><button id="Q1_button" onclick="checkAnswer({1: 'numerical'})" class="problem_mo_button">Check</button><button id="Q1_button_show" onclick="showHideSolution({1: 'numerical'}, 1, [1])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Problem 1.2 - Limiting to Teams Making the Playoffs</h2>
<div class="self_assessment">
<div id="Q2_div" class="problem_question">
<p display_name="Problem 1.2 - Limiting to Teams Making the Playoffs" url_name="Problem_1_2_Limiting_to_Teams_Making_the_Playoffs_0">Though the dataset contains data from 1962 until 2012, we removed several years with shorter-than-usual seasons. Using the table() function, identify the total number of years included in this dataset.</p>
<fieldset><legend class="visually-hidden">Exercise 2</legend>
<div class="choice"><label id="Q2_label"><span id="Q2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q2_input" value="" onkeypress="numericTypedOrDropDownSelected(2)" class="problem_text_input" /><input type="hidden" id="Q2_ans" value="47" /><input type="hidden" id="Q2_tolerance" value="0" /><span id="Q2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S2_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="S2_div" class="problem_solution" tabindex="-1" display_name="Problem 1.2 - Limiting to Teams Making the Playoffs" url_name="Problem_1_2_Limiting_to_Teams_Making_the_Playoffs_2">
<div class="detailed-solution">
<p>Explanation</p>
<p>table(baseball$Year) contains 47 years (1972, 1981, 1994, and 1995 are missing). You can count the number of years in the table, or the command length(table(baseball$Year)) directly provides the answer.</p>
</div>
</div>
<div class="action"><button id="Q2_button" onclick="checkAnswer({2: 'numerical'})" class="problem_mo_button">Check</button><button id="Q2_button_show" onclick="showHideSolution({2: 'numerical'}, 2, [2])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Problem 1.3 - Limiting to Teams Making the Playoffs</h2>
<div class="self_assessment">
<div id="Q3_div" class="problem_question">
<p display_name="Problem 1.3 - Limiting to Teams Making the Playoffs" url_name="Problem_1_3_Limiting_to_Teams_Making_the_Playoffs_0">Because we're only analyzing teams that made the playoffs, use the subset() function to <b>replace baseball</b> with a data frame limited to teams that made the playoffs (so your subsetted data frame should still be called &quot;baseball&quot;). How many team/year pairs are included in the new dataset?</p>
<fieldset><legend class="visually-hidden">Exercise 3</legend>
<div class="choice"><label id="Q3_label"><span id="Q3_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q3_input" value="" onkeypress="numericTypedOrDropDownSelected(3)" class="problem_text_input" /><input type="hidden" id="Q3_ans" value="244" /><input type="hidden" id="Q3_tolerance" value="0" /><span id="Q3_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S3_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="S3_div" class="problem_solution" tabindex="-1" display_name="Problem 1.3 - Limiting to Teams Making the Playoffs" url_name="Problem_1_3_Limiting_to_Teams_Making_the_Playoffs_2">
<div class="detailed-solution">
<p>Explanation</p>
<p>baseball = subset(baseball, Playoffs == 1) limits the dataset, and the nrow() or str() functions can be used to identify that 244 team/year pairs remain.</p>
</div>
</div>
<div class="action"><button id="Q3_button" onclick="checkAnswer({3: 'numerical'})" class="problem_mo_button">Check</button><button id="Q3_button_show" onclick="showHideSolution({3: 'numerical'}, 3, [3])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Problem 1.4 - Limiting to Teams Making the Playoffs</h2>
<div class="self_assessment">
<div id="Q4_div" class="problem_question">
<p display_name="Problem 1.4 - Limiting to Teams Making the Playoffs" url_name="Problem_1_4_Limiting_to_Teams_Making_the_Playoffs_0">Through the years, different numbers of teams have been invited to the playoffs. Which of the following has been the number of teams making the playoffs in some season? Select all that apply.</p>
<fieldset><legend class="visually-hidden">Exercise 4</legend>
<div class="choice"><label id="Q4_input_1_label"><span id="Q4_input_1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q4_input_1" onclick="optionSelected(4)" name="Q4_input" class="problem_radio_input" correct="true" /><span class="choice">2</span><span id="Q4_input_1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q4_input_2_label"><span id="Q4_input_2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q4_input_2" onclick="optionSelected(4)" name="Q4_input" class="problem_radio_input" correct="true" /><span class="choice">4</span><span id="Q4_input_2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q4_input_3_label"><span id="Q4_input_3_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q4_input_3" onclick="optionSelected(4)" name="Q4_input" class="problem_radio_input" correct="false" /><span class="choice">6</span><span id="Q4_input_3_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q4_input_4_label"><span id="Q4_input_4_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q4_input_4" onclick="optionSelected(4)" name="Q4_input" class="problem_radio_input" correct="true" /><span class="choice">8</span><span id="Q4_input_4_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q4_input_5_label"><span id="Q4_input_5_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q4_input_5" onclick="optionSelected(4)" name="Q4_input" class="problem_radio_input" correct="true" /><span class="choice">10</span><span id="Q4_input_5_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q4_input_6_label"><span id="Q4_input_6_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q4_input_6" onclick="optionSelected(4)" name="Q4_input" class="problem_radio_input" correct="false" /><span class="choice">12</span><span id="Q4_input_6_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="Q4_status_combined" tabindex="-1" class="nostatus">&nbsp;</p>
</fieldset></div>
<div id="S4_div" class="problem_solution" tabindex="-1" display_name="Problem 1.4 - Limiting to Teams Making the Playoffs" url_name="Problem_1_4_Limiting_to_Teams_Making_the_Playoffs_2">
<div class="detailed-solution">
<p>Explanation</p>
<p>Using table(baseball$Year), we can see at least one season had 2, 4, 8, and 10 contenders. A fancier approach would be to use table(table(baseball$Year)).</p>
</div>
</div>
<div class="action"><button id="Q4_button" onclick="checkAnswer({4: 'choiceresponse'})" class="problem_mo_button">Check</button><button id="Q4_button_show" onclick="showHideSolution({4: 'choiceresponse'}, 4, [4])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Problem 2.1 - Adding an Important Predictor</h2>
<div class="self_assessment">
<p display_name="Problem 2.1 - Adding an Important Predictor" url_name="Problem_2_1_Adding_an_Important_Predictor_0">It's much harder to win the World Series if there are 10 teams competing for the championship versus just two. Therefore, we will add the predictor variable NumCompetitors to the baseball data frame. NumCompetitors will contain the number of total teams making the playoffs in the year of a particular team/year pair. For instance, NumCompetitors should be 2 for the 1962 New York Yankees, but it should be 8 for the 1998 Boston Red Sox.</p>
<p display_name="Problem 2.1 - Adding an Important Predictor" url_name="Problem_2_1_Adding_an_Important_Predictor_1">We start by storing the output of the table() function that counts the number of playoff teams from each year:</p>
<p display_name="Problem 2.1 - Adding an Important Predictor" url_name="Problem_2_1_Adding_an_Important_Predictor_2">PlayoffTable = table(baseball$Year)</p>
<p display_name="Problem 2.1 - Adding an Important Predictor" url_name="Problem_2_1_Adding_an_Important_Predictor_3">You can output the table with the following command:</p>
<p display_name="Problem 2.1 - Adding an Important Predictor" url_name="Problem_2_1_Adding_an_Important_Predictor_4">PlayoffTable</p>
<p display_name="Problem 2.1 - Adding an Important Predictor" url_name="Problem_2_1_Adding_an_Important_Predictor_5">We will use this stored table to look up the number of teams in the playoffs in the year of each team/year pair.</p>
<div id="Q5_div" class="problem_question">
<p display_name="Problem 2.1 - Adding an Important Predictor" url_name="Problem_2_1_Adding_an_Important_Predictor_6">Just as we can use the names() function to get the names of a data frame's columns, we can use it to get the names of the entries in a table. What best describes the output of names(PlayoffTable)?</p>
<fieldset><legend class="visually-hidden">Exercise 5</legend>
<div class="choice"><label id="Q5_input_1_label"><span id="Q5_input_1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q5_input_1" onclick="optionSelected(5)" name="Q5_input" class="problem_radio_input" correct="false" /><span class="choice">Vector of years stored as numbers (type num)</span><span id="Q5_input_1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q5_input_2_label"><span id="Q5_input_2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q5_input_2" onclick="optionSelected(5)" name="Q5_input" class="problem_radio_input" correct="true" /><span class="choice">Vector of years stored as strings (type chr)</span><span id="Q5_input_2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q5_input_3_label"><span id="Q5_input_3_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q5_input_3" onclick="optionSelected(5)" name="Q5_input" class="problem_radio_input" correct="false" /><span class="choice">Vector of frequencies stored as numbers (type num)</span><span id="Q5_input_3_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q5_input_4_label"><span id="Q5_input_4_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q5_input_4" onclick="optionSelected(5)" name="Q5_input" class="problem_radio_input" correct="false" /><span class="choice">Vector of frequencies stored as strings (type chr)</span><span id="Q5_input_4_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
</fieldset></div>
<div id="S5_div" class="problem_solution" tabindex="-1" display_name="Problem 2.1 - Adding an Important Predictor" url_name="Problem_2_1_Adding_an_Important_Predictor_8">
<div class="detailed-solution">
<p>Explanation</p>
<p>From the call str(names(PlayoffTable)) we see PlayoffTable has names of type chr, which are the years of the teams in the dataset.</p>
</div>
</div>
<div class="action"><button id="Q5_button" onclick="checkAnswer({5: 'multiple_choice'})" class="problem_mo_button">Check</button><button id="Q5_button_show" onclick="showHideSolution({5: 'multiple_choice'}, 5, [5])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Problem 2.2 - Adding an Important Predictor</h2>
<div class="self_assessment">
<div id="Q6_div" class="problem_question">
<p display_name="Problem 2.2 - Adding an Important Predictor" url_name="Problem_2_2_Adding_an_Important_Predictor_0">Given a vector of names, the table will return a vector of frequencies. Which function call returns the number of playoff teams in 1990 and 2001? (HINT: If you are not sure how these commands work, go ahead and try them out in your R console!)</p>
<fieldset><legend class="visually-hidden">Exercise 6</legend>
<div class="choice"><label id="Q6_input_1_label"><span id="Q6_input_1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q6_input_1" onclick="optionSelected(6)" name="Q6_input" class="problem_radio_input" correct="false" /><span class="choice">PlayoffTable(1990, 2001)</span><span id="Q6_input_1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q6_input_2_label"><span id="Q6_input_2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q6_input_2" onclick="optionSelected(6)" name="Q6_input" class="problem_radio_input" correct="false" /><span class="choice">PlayoffTable(c(1990, 2001))</span><span id="Q6_input_2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q6_input_3_label"><span id="Q6_input_3_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q6_input_3" onclick="optionSelected(6)" name="Q6_input" class="problem_radio_input" correct="false" /><span class="choice">PlayoffTable(&quot;1990&quot;, &quot;2001&quot;)</span><span id="Q6_input_3_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q6_input_4_label"><span id="Q6_input_4_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q6_input_4" onclick="optionSelected(6)" name="Q6_input" class="problem_radio_input" correct="false" /><span class="choice">PlayoffTable(c(&quot;1990&quot;, &quot;2001&quot;))</span><span id="Q6_input_4_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q6_input_5_label"><span id="Q6_input_5_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q6_input_5" onclick="optionSelected(6)" name="Q6_input" class="problem_radio_input" correct="false" /><span class="choice">PlayoffTable[1990, 2001]</span><span id="Q6_input_5_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q6_input_6_label"><span id="Q6_input_6_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q6_input_6" onclick="optionSelected(6)" name="Q6_input" class="problem_radio_input" correct="false" /><span class="choice">PlayoffTable[c(1990, 2001)]</span><span id="Q6_input_6_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q6_input_7_label"><span id="Q6_input_7_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q6_input_7" onclick="optionSelected(6)" name="Q6_input" class="problem_radio_input" correct="false" /><span class="choice">PlayoffTable[&quot;1990&quot;, &quot;2001&quot;]</span><span id="Q6_input_7_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q6_input_8_label"><span id="Q6_input_8_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q6_input_8" onclick="optionSelected(6)" name="Q6_input" class="problem_radio_input" correct="true" /><span class="choice">PlayoffTable[c(&quot;1990&quot;, &quot;2001&quot;)]</span><span id="Q6_input_8_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
</fieldset></div>
<div id="S6_div" class="problem_solution" tabindex="-1" display_name="Problem 2.2 - Adding an Important Predictor" url_name="Problem_2_2_Adding_an_Important_Predictor_2">
<div class="detailed-solution">
<p>Explanation</p>
<p>Because PlayoffTable is an object and not a function, we look up elements in it with square brackets instead of parentheses. We build the vector of years to be passed with the c() function. Because the names of PlayoffTable are strings and not numbers, we need to pass &quot;1990&quot; and &quot;2001&quot;.</p>
</div>
</div>
<div class="action"><button id="Q6_button" onclick="checkAnswer({6: 'multiple_choice'})" class="problem_mo_button">Check</button><button id="Q6_button_show" onclick="showHideSolution({6: 'multiple_choice'}, 6, [6])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Problem 2.3 - Adding an Important Predictor</h2>
<div class="self_assessment">
<div id="Q7_div" class="problem_question">
<p display_name="Problem 2.3 - Adding an Important Predictor" url_name="Problem_2_3_Adding_an_Important_Predictor_0">Putting it all together, we want to look up the number of teams in the playoffs for each team/year pair in the dataset, and store it as a new variable named NumCompetitors in the baseball data frame. While of the following function calls accomplishes this? (HINT: Test out the functions if you are not sure what they do.)</p>
<fieldset><legend class="visually-hidden">Exercise 7</legend>
<div class="choice"><label id="Q7_input_1_label"><span id="Q7_input_1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q7_input_1" onclick="optionSelected(7)" name="Q7_input" class="problem_radio_input" correct="false" /><span class="choice">baseball$NumCompetitors = PlayoffTable(baseball$Year)</span><span id="Q7_input_1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q7_input_2_label"><span id="Q7_input_2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q7_input_2" onclick="optionSelected(7)" name="Q7_input" class="problem_radio_input" correct="false" /><span class="choice">baseball$NumCompetitors = PlayoffTable[baseball$Year]</span><span id="Q7_input_2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q7_input_3_label"><span id="Q7_input_3_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q7_input_3" onclick="optionSelected(7)" name="Q7_input" class="problem_radio_input" correct="false" /><span class="choice">baseball$NumCompetitors = PlayoffTable(as.character(baseball$Year))</span><span id="Q7_input_3_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q7_input_4_label"><span id="Q7_input_4_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q7_input_4" onclick="optionSelected(7)" name="Q7_input" class="problem_radio_input" correct="true" /><span class="choice">baseball$NumCompetitors = PlayoffTable[as.character(baseball$Year)]</span><span id="Q7_input_4_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
</fieldset></div>
<div id="S7_div" class="problem_solution" tabindex="-1" display_name="Problem 2.3 - Adding an Important Predictor" url_name="Problem_2_3_Adding_an_Important_Predictor_2">
<div class="detailed-solution">
<p>Explanation</p>
<p>Because PlayoffTable is an object and not a function, we look up elements in it with square brackets instead of parentheses. as.character() is needed to convert the Year variable in the dataset to a string, which we know from the previous parts is needed to look up elements in a table. If you're not sure what a function does, remember you can look it up with the ? function. For instance, you could type ?as.character to look up information about as.character.</p>
</div>
</div>
<div class="action"><button id="Q7_button" onclick="checkAnswer({7: 'multiple_choice'})" class="problem_mo_button">Check</button><button id="Q7_button_show" onclick="showHideSolution({7: 'multiple_choice'}, 7, [7])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Problem 2.4 - Adding an Important Predictor</h2>
<div class="self_assessment">
<div id="Q8_div" class="problem_question">
<p display_name="Problem 2.4 - Adding an Important Predictor" url_name="Problem_2_4_Adding_an_Important_Predictor_0">Add the NumCompetitors variable to your baseball data frame. How many playoff team/year pairs are there in our dataset from years where 8 teams were invited to the playoffs?</p>
<fieldset><legend class="visually-hidden">Exercise 8</legend>
<div class="choice"><label id="Q8_label"><span id="Q8_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q8_input" value="" onkeypress="numericTypedOrDropDownSelected(8)" class="problem_text_input" /><input type="hidden" id="Q8_ans" value="128" /><input type="hidden" id="Q8_tolerance" value="0" /><span id="Q8_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S8_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="S8_div" class="problem_solution" tabindex="-1" display_name="Problem 2.4 - Adding an Important Predictor" url_name="Problem_2_4_Adding_an_Important_Predictor_2">
<div class="detailed-solution">
<p>Explanation</p>
<p>You can add the NumCompetitors variable to the baseball data frame with the following command:</p>
<p>baseball$NumCompetitors = PlayoffTable[as.character(baseball$Year)]</p>
<p>Then you can obtain the number of team/year pairs with 8 teams in the playoffs by running table(baseball$NumCompetitors)</p>
</div>
</div>
<div class="action"><button id="Q8_button" onclick="checkAnswer({8: 'numerical'})" class="problem_mo_button">Check</button><button id="Q8_button_show" onclick="showHideSolution({8: 'numerical'}, 8, [8])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Problem 3.1 - Bivariate Models for Predicting World Series Winner</h2>
<div class="self_assessment">
<p display_name="Problem 3.1 - Bivariate Models for Predicting World Series Winner" url_name="Problem_3_1_Bivariate_Models_for_Predicting_World_Series_Winner_0">In this problem, we seek to predict whether a team won the World Series; in our dataset this is denoted with a RankPlayoffs value of 1. Add a variable named WorldSeries to the baseball data frame, by typing the following command in your R console:</p>
<p display_name="Problem 3.1 - Bivariate Models for Predicting World Series Winner" url_name="Problem_3_1_Bivariate_Models_for_Predicting_World_Series_Winner_1">baseball$WorldSeries = as.numeric(baseball$RankPlayoffs == 1)</p>
<div id="Q9_div" class="problem_question">
<p display_name="Problem 3.1 - Bivariate Models for Predicting World Series Winner" url_name="Problem_3_1_Bivariate_Models_for_Predicting_World_Series_Winner_2">WorldSeries takes value 1 if a team won the World Series in the indicated year and a 0 otherwise. How many observations do we have in our dataset where a team did NOT win the World Series?</p>
<fieldset><legend class="visually-hidden">Exercise 9</legend>
<div class="choice"><label id="Q9_label"><span id="Q9_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q9_input" value="" onkeypress="numericTypedOrDropDownSelected(9)" class="problem_text_input" /><input type="hidden" id="Q9_ans" value="197" /><input type="hidden" id="Q9_tolerance" value="0" /><span id="Q9_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S9_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="S9_div" class="problem_solution" tabindex="-1" display_name="Problem 3.1 - Bivariate Models for Predicting World Series Winner" url_name="Problem_3_1_Bivariate_Models_for_Predicting_World_Series_Winner_4">
<div class="detailed-solution">
<p>Explanation</p>
<p>You can create the WorldSeries variable by running the command:</p>
<p>baseball$WorldSeries = as.numeric(baseball$RankPlayoffs == 1)</p>
<p>Then, if you create the table:</p>
<p>table(baseball$WorldSeries)</p>
<p>You can see that there are 197 teams that did not win the World Series.</p>
</div>
</div>
<div class="action"><button id="Q9_button" onclick="checkAnswer({9: 'numerical'})" class="problem_mo_button">Check</button><button id="Q9_button_show" onclick="showHideSolution({9: 'numerical'}, 9, [9])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Problem 3.2 - Bivariate Models for Predicting World Series Winner</h2>
<div class="self_assessment">
<div id="Q10_div" class="problem_question">
<p display_name="Problem 3.2 - Bivariate Models for Predicting World Series Winner" url_name="Problem_3_2_Bivariate_Models_for_Predicting_World_Series_Winner_0">When we're not sure which of our variables are useful in predicting a particular outcome, it's often helpful to build bivariate models, which are models that predict the outcome using a single independent variable. Which of the following variables is a significant predictor of the WorldSeries variable in a bivariate logistic regression model? To determine significance, remember to look at the stars in the summary output of the model. We'll define an independent variable as significant if there is at least one star at the end of the coefficients row for that variable (this is equivalent to the probability column having a value smaller than 0.05). Note that you have to build 12 models to answer this question! Use the entire dataset baseball to build the models. (Select all that apply.)</p>
<fieldset><legend class="visually-hidden">Exercise 10</legend>
<div class="choice"><label id="Q10_input_1_label"><span id="Q10_input_1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q10_input_1" onclick="optionSelected(10)" name="Q10_input" class="problem_radio_input" correct="true" /><span class="choice">Year</span><span id="Q10_input_1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q10_input_2_label"><span id="Q10_input_2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q10_input_2" onclick="optionSelected(10)" name="Q10_input" class="problem_radio_input" correct="false" /><span class="choice">RS</span><span id="Q10_input_2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q10_input_3_label"><span id="Q10_input_3_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q10_input_3" onclick="optionSelected(10)" name="Q10_input" class="problem_radio_input" correct="true" /><span class="choice">RA</span><span id="Q10_input_3_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q10_input_4_label"><span id="Q10_input_4_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q10_input_4" onclick="optionSelected(10)" name="Q10_input" class="problem_radio_input" correct="false" /><span class="choice">W</span><span id="Q10_input_4_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q10_input_5_label"><span id="Q10_input_5_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q10_input_5" onclick="optionSelected(10)" name="Q10_input" class="problem_radio_input" correct="false" /><span class="choice">OBP</span><span id="Q10_input_5_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q10_input_6_label"><span id="Q10_input_6_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q10_input_6" onclick="optionSelected(10)" name="Q10_input" class="problem_radio_input" correct="false" /><span class="choice">SLG</span><span id="Q10_input_6_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q10_input_7_label"><span id="Q10_input_7_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q10_input_7" onclick="optionSelected(10)" name="Q10_input" class="problem_radio_input" correct="false" /><span class="choice">BA</span><span id="Q10_input_7_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q10_input_8_label"><span id="Q10_input_8_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q10_input_8" onclick="optionSelected(10)" name="Q10_input" class="problem_radio_input" correct="true" /><span class="choice">RankSeason</span><span id="Q10_input_8_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q10_input_9_label"><span id="Q10_input_9_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q10_input_9" onclick="optionSelected(10)" name="Q10_input" class="problem_radio_input" correct="false" /><span class="choice">OOBP</span><span id="Q10_input_9_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q10_input_10_label"><span id="Q10_input_10_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q10_input_10" onclick="optionSelected(10)" name="Q10_input" class="problem_radio_input" correct="false" /><span class="choice">OSLG</span><span id="Q10_input_10_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q10_input_11_label"><span id="Q10_input_11_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q10_input_11" onclick="optionSelected(10)" name="Q10_input" class="problem_radio_input" correct="true" /><span class="choice">NumCompetitors</span><span id="Q10_input_11_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q10_input_12_label"><span id="Q10_input_12_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q10_input_12" onclick="optionSelected(10)" name="Q10_input" class="problem_radio_input" correct="false" /><span class="choice">League</span><span id="Q10_input_12_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="Q10_status_combined" tabindex="-1" class="nostatus">&nbsp;</p>
</fieldset></div>
<div id="S10_div" class="problem_solution" tabindex="-1" display_name="Problem 3.2 - Bivariate Models for Predicting World Series Winner" url_name="Problem_3_2_Bivariate_Models_for_Predicting_World_Series_Winner_2">
<div class="detailed-solution">
<p>Explanation</p>
<p>The results come from building each bivariate model and looking at its summary. For instance, the result for the variable Year can be obtained by running summary(glm(WorldSeries~Year, data=baseball, family=&quot;binomial&quot;)). You can save time on repeated model building by using the up arrow in your R terminal. The W and SLG variables were both nearly significant, with p = 0.0577 and 0.0504, respectively.</p>
</div>
</div>
<div class="action"><button id="Q10_button" onclick="checkAnswer({10: 'choiceresponse'})" class="problem_mo_button">Check</button><button id="Q10_button_show" onclick="showHideSolution({10: 'choiceresponse'}, 10, [10])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Problem 4.1 - Multivariate Models for Predicting World Series Winner</h2>
<div class="self_assessment">
<div id="Q11_div" class="problem_question">
<p display_name="Problem 4.1 - Multivariate Models for Predicting World Series Winner" url_name="Problem_4_1_Multivariate_Models_for_Predicting_World_Series_Winner_0">In this section, we'll consider multivariate models that combine the variables we found to be significant in bivariate models. Build a model using all of the variables that you found to be significant in the bivariate models. How many variables are significant in the combined model?</p>
<fieldset><legend class="visually-hidden">Exercise 11</legend>
<div class="choice"><label id="Q11_label"><span id="Q11_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q11_input" value="" onkeypress="numericTypedOrDropDownSelected(11)" class="problem_text_input" /><input type="hidden" id="Q11_ans" value="0" /><input type="hidden" id="Q11_tolerance" value="0" /><span id="Q11_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S11_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="S11_div" class="problem_solution" tabindex="-1" display_name="Problem 4.1 - Multivariate Models for Predicting World Series Winner" url_name="Problem_4_1_Multivariate_Models_for_Predicting_World_Series_Winner_2">
<div class="detailed-solution">
<p>Explanation</p>
<p>You can create a model with all of the significant variables from the bivariate models (Year, RA, RankSeason, and NumCompetitors) by using the following command:</p>
<p>LogModel = glm(WorldSeries ~ Year + RA + RankSeason + NumCompetitors, data=baseball, family=binomial)</p>
<p>Looking at summary(LogModel), you can see that none of the variables are significant in the multivariate model!</p>
</div>
</div>
<div class="action"><button id="Q11_button" onclick="checkAnswer({11: 'numerical'})" class="problem_mo_button">Check</button><button id="Q11_button_show" onclick="showHideSolution({11: 'numerical'}, 11, [11])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Problem 4.2 - Multivariate Models for Predicting World Series Winner</h2>
<div class="self_assessment">
<div id="Q12_div" class="problem_question">
<p display_name="Problem 4.2 - Multivariate Models for Predicting World Series Winner" url_name="Problem_4_2_Multivariate_Models_for_Predicting_World_Series_Winner_0">Often, variables that were significant in bivariate models are no longer significant in multivariate analysis due to correlation between the variables. Which of the following variable pairs have a high degree of correlation (a correlation greater than 0.8 or less than -0.8)? Select all that apply.</p>
<fieldset><legend class="visually-hidden">Exercise 12</legend>
<div class="choice"><label id="Q12_input_1_label"><span id="Q12_input_1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q12_input_1" onclick="optionSelected(12)" name="Q12_input" class="problem_radio_input" correct="false" /><span class="choice">Year/RA</span><span id="Q12_input_1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q12_input_2_label"><span id="Q12_input_2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q12_input_2" onclick="optionSelected(12)" name="Q12_input" class="problem_radio_input" correct="false" /><span class="choice">Year/RankSeason</span><span id="Q12_input_2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q12_input_3_label"><span id="Q12_input_3_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q12_input_3" onclick="optionSelected(12)" name="Q12_input" class="problem_radio_input" correct="true" /><span class="choice">Year/NumCompetitors</span><span id="Q12_input_3_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q12_input_4_label"><span id="Q12_input_4_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q12_input_4" onclick="optionSelected(12)" name="Q12_input" class="problem_radio_input" correct="false" /><span class="choice">RA/RankSeason</span><span id="Q12_input_4_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q12_input_5_label"><span id="Q12_input_5_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q12_input_5" onclick="optionSelected(12)" name="Q12_input" class="problem_radio_input" correct="false" /><span class="choice">RA/NumCompetitors</span><span id="Q12_input_5_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q12_input_6_label"><span id="Q12_input_6_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q12_input_6" onclick="optionSelected(12)" name="Q12_input" class="problem_radio_input" correct="false" /><span class="choice">RankSeason/NumCompetitors</span><span id="Q12_input_6_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="Q12_status_combined" tabindex="-1" class="nostatus">&nbsp;</p>
</fieldset></div>
<div id="S12_div" class="problem_solution" tabindex="-1" display_name="Problem 4.2 - Multivariate Models for Predicting World Series Winner" url_name="Problem_4_2_Multivariate_Models_for_Predicting_World_Series_Winner_2">
<div class="detailed-solution">
<p>Explanation</p>
<p>To test the correlation between two variables, use a command like cor(baseball$Year, baseball$RA). While every pair was at least moderately correlated, the only strongly correlated pair was Year/NumCompetitors, with correlation coefficient 0.914.</p>
<p>As a shortcut, you can compute all pair-wise correlations between these variables with:</p>
<p>cor(baseball[c(&ldquo;Year&rdquo;, &ldquo;RA&rdquo;, &ldquo;RankSeason&rdquo;, &ldquo;NumCompetitors&rdquo;)])</p>
</div>
</div>
<div class="action"><button id="Q12_button" onclick="checkAnswer({12: 'choiceresponse'})" class="problem_mo_button">Check</button><button id="Q12_button_show" onclick="showHideSolution({12: 'choiceresponse'}, 12, [12])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Problem 4.3 - Multivariate Models for Predicting World Series Winner</h2>
<div class="self_assessment">
<div id="Q13_div" class="problem_question">
<p display_name="Problem 4.3 - Multivariate Models for Predicting World Series Winner" url_name="Problem_4_3_Multivariate_Models_for_Predicting_World_Series_Winner_0">Build all six of the two variable models listed in the previous problem. Together with the four bivariate models, you should have 10 different logistic regression models. Which model has the best AIC value (the minimum AIC value)?</p>
<fieldset><legend class="visually-hidden">Exercise 13</legend>
<div class="choice"><label id="Q13_input_1_label"><span id="Q13_input_1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q13_input_1" onclick="optionSelected(13)" name="Q13_input" class="problem_radio_input" correct="false" /><span class="choice">Year</span><span id="Q13_input_1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q13_input_2_label"><span id="Q13_input_2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q13_input_2" onclick="optionSelected(13)" name="Q13_input" class="problem_radio_input" correct="false" /><span class="choice">RA</span><span id="Q13_input_2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q13_input_3_label"><span id="Q13_input_3_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q13_input_3" onclick="optionSelected(13)" name="Q13_input" class="problem_radio_input" correct="false" /><span class="choice">RankSeason</span><span id="Q13_input_3_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q13_input_4_label"><span id="Q13_input_4_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q13_input_4" onclick="optionSelected(13)" name="Q13_input" class="problem_radio_input" correct="true" /><span class="choice">NumCompetitors</span><span id="Q13_input_4_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q13_input_5_label"><span id="Q13_input_5_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q13_input_5" onclick="optionSelected(13)" name="Q13_input" class="problem_radio_input" correct="false" /><span class="choice">Year/RA</span><span id="Q13_input_5_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q13_input_6_label"><span id="Q13_input_6_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q13_input_6" onclick="optionSelected(13)" name="Q13_input" class="problem_radio_input" correct="false" /><span class="choice">Year/RankSeason</span><span id="Q13_input_6_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q13_input_7_label"><span id="Q13_input_7_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q13_input_7" onclick="optionSelected(13)" name="Q13_input" class="problem_radio_input" correct="false" /><span class="choice">Year/NumCompetitors</span><span id="Q13_input_7_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q13_input_8_label"><span id="Q13_input_8_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q13_input_8" onclick="optionSelected(13)" name="Q13_input" class="problem_radio_input" correct="false" /><span class="choice">RA/RankSeason</span><span id="Q13_input_8_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q13_input_9_label"><span id="Q13_input_9_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q13_input_9" onclick="optionSelected(13)" name="Q13_input" class="problem_radio_input" correct="false" /><span class="choice">RA/NumCompetitors</span><span id="Q13_input_9_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q13_input_10_label"><span id="Q13_input_10_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q13_input_10" onclick="optionSelected(13)" name="Q13_input" class="problem_radio_input" correct="false" /><span class="choice">RankSeason/NumCompetitors</span><span id="Q13_input_10_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
</fieldset></div>
<div id="S13_div" class="problem_solution" tabindex="-1" display_name="Problem 4.3 - Multivariate Models for Predicting World Series Winner" url_name="Problem_4_3_Multivariate_Models_for_Predicting_World_Series_Winner_2">
<div class="detailed-solution">
<p>Explanation</p>
<p>The two-variable models can be built with the following commands:</p>
<p>Model1 = glm(WorldSeries ~ Year + RA, data=baseball, family=binomial)</p>
<p>Model2 = glm(WorldSeries ~ Year + RankSeason, data=baseball, family=binomial)</p>
<p>Model3 = glm(WorldSeries ~ Year + NumCompetitors, data=baseball, family=binomial)</p>
<p>Model4 = glm(WorldSeries ~ RA + RankSeason, data=baseball, family=binomial)</p>
<p>Model5 = glm(WorldSeries ~ RA + NumCompetitors, data=baseball, family=binomial)</p>
<p>Model6 = glm(WorldSeries ~ RankSeason + NumCompetitors, data=baseball, family=binomial)</p>
<p>None of the models with two independent variables had both variables significant, so none seem promising as compared to a simple bivariate model. Indeed the model with the lowest AIC value is the model with just NumCompetitors as the independent variable.</p>
<p>This seems to confirm the claim made by Billy Beane in Moneyball that all that matters in the Playoffs is luck, since NumCompetitors has nothing to do with the quality of the teams!</p>
</div>
</div>
<div class="action"><button id="Q13_button" onclick="checkAnswer({13: 'multiple_choice'})" class="problem_mo_button">Check</button><button id="Q13_button_show" onclick="showHideSolution({13: 'multiple_choice'}, 13, [13])" class="problem_mo_button">Show Answer</button></div>
</div>
<ul class="navigation progress">
    <li id="bck_btn"><a href="./resolveuid/d4a650ea930c2c8c0f989b353a5a342e">Back<span>Assignment 3</span></a></li>
    <li id="continue_btn"><a href="./resolveuid/19c8cf92e31d034a1ea15ad53194d892">Continue<span>Trees</span></a></li>
</ul>