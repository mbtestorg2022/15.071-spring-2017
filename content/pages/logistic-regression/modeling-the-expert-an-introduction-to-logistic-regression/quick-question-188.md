---
content_type: page
parent_title: '3.2 Modeling the Expert: An Introduction to Logistic Regression'
parent_uid: 3063320a-4175-6b8a-4fa9-892f61b52c0d
title: '3.2 Modeling the Expert: An Introduction to Logistic Regression'
uid: d565e093-b63d-b842-9332-eabcb8503b85
---
<ul class="navigation pagination">
    <li id="top_bck_btn"><a href="./resolveuid/7bf86a6c2bb6629ed20e4dd216833197">&lt;<span>Video 5: Thresholding</span></a></li>
    <li id="flp_btn_1"><a href="./resolveuid/3063320a41756b8a4fa9892f61b52c0d">3.2.1<span>Video 1: Replicating Expert Assessment</span></a></li>
    <li id="flp_btn_2"><a href="./resolveuid/a92dcb88eddd40ad72c0d5bc2288c90e">3.2.2<span>Video 2: Building the Dataset</span></a></li>
    <li id="flp_btn_3"><a href="./resolveuid/4551bb95ca82a0cacf08eda74141daaa">3.2.3<span>Quick Question</span></a></li>
    <li id="flp_btn_4"><a href="./resolveuid/8099bebbd4e81ce09baa3ede1f3ec357">3.2.4<span>Video 3: Logistic Regression</span></a></li>
    <li id="flp_btn_5"><a href="./resolveuid/9cb7a258ad190f7f84e589aad47092b1">3.2.5<span>Quick Question</span></a></li>
    <li id="flp_btn_6"><a href="./resolveuid/8fc17cbb03cdce23b5880c21e7dc33e8">3.2.6<span>Video 4: Logistic Regression in R</span></a></li>
    <li id="flp_btn_7"><a href="./resolveuid/8c08020699935e2bb0c50c4cd73fd74c">3.2.7<span>Quick Question</span></a></li>
    <li id="flp_btn_8"><a href="./resolveuid/7bf86a6c2bb6629ed20e4dd216833197">3.2.8<span>Video 5: Thresholding</span></a></li>
    <li id="flp_btn_9" class="button_selected"><a href="./resolveuid/d565e093b63db8429332eabcb8503b85">3.2.9<span>Quick Question</span></a></li>
    <li id="flp_btn_10"><a href="./resolveuid/f62162651257bdbe48268a5e5b311096">3.2.10<span>Video 6: ROC Curves</span></a></li>
    <li id="flp_btn_11"><a href="./resolveuid/d9817f81c4ac257aed44548eaa714059">3.2.11<span>Quick Question</span></a></li>
    <li id="flp_btn_12"><a href="./resolveuid/1e61720ecc150a7b0c5eb3fe60c5ffa1">3.2.12<span>Video 7: Interpreting the Model</span></a></li>
    <li id="flp_btn_13"><a href="./resolveuid/8809159b6e060da2d38690c7900fdd67">3.2.13<span>Quick Question</span></a></li>
    <li id="flp_btn_14"><a href="./resolveuid/81d5d93d77c2b8fc0b85d9cbcdc418a5">3.2.14<span>Video 8: The Analytics Edge</span></a></li>
    <li id="top_continue_btn"><a href="./resolveuid/f62162651257bdbe48268a5e5b311096">&gt;<span>Video 6: ROC Curves</span></a></li>
</ul>
<h2 class="subhead">Quick Question</h2>
<p>This question asks about the following two confusion matrices:</p>
<p>Confusion Matrix #1:</p>
<table border="1">
    <tbody>
        <tr>
            <th>&nbsp;</th>
            <th>Predicted = 0</th>
            <th>Predicted = 1</th>
        </tr>
        <tr>
            <th>Actual = 0</th>
            <td>15</td>
            <td>10</td>
        </tr>
        <tr>
            <th>Actual = 1</th>
            <td>5</td>
            <td>20</td>
        </tr>
    </tbody>
</table>
<p>&nbsp;</p>
<p>Confusion Matrix #2:</p>
<table border="1">
    <tbody>
        <tr>
            <th>&nbsp;</th>
            <th>Predicted = 0</th>
            <th>Predicted = 1</th>
        </tr>
        <tr>
            <th>Actual = 0</th>
            <td>20</td>
            <td>5</td>
        </tr>
        <tr>
            <th>Actual = 1</th>
            <td>10</td>
            <td>15</td>
        </tr>
    </tbody>
</table>
<div class="self_assessment">
<div id="Q1_div" class="problem_question">
<p display_name="Quick Question" url_name="Quick_Question_190">What is the sensitivity of Confusion Matrix #1?</p>
<fieldset><legend class="visually-hidden">Exercise 1</legend>
<div class="choice"><label id="Q1_label"><span id="Q1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q1_input" value="" onkeypress="numericTypedOrDropDownSelected(1)" class="problem_text_input" /><input type="hidden" id="Q1_ans" value="0.8" /><input type="hidden" id="Q1_tolerance" value="1%" /><span id="Q1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S1_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="S1_div" class="problem_solution" tabindex="-1" display_name="Quick Question" url_name="Quick_Question_192">
<div class="detailed-solution">
<p>Explanation</p>
<p>The sensitivity of a confusion matrix is the true positives, divided by the true positives plus the false negatives. In this case, it is 20/(20+5) = 0.8</p>
</div>
</div>
<div id="Q2_div" class="problem_question">
<p display_name="Quick Question" url_name="Quick_Question_193">What is the specificity of Confusion Matrix #1?</p>
<fieldset><legend class="visually-hidden">Exercise 2</legend>
<div class="choice"><label id="Q2_label"><span id="Q2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q2_input" value="" onkeypress="numericTypedOrDropDownSelected(2)" class="problem_text_input" /><input type="hidden" id="Q2_ans" value="0.6" /><input type="hidden" id="Q2_tolerance" value="1%" /><span id="Q2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S2_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="S2_div" class="problem_solution" tabindex="-1" display_name="Quick Question" url_name="Quick_Question_195">
<div class="detailed-solution">
<p>Explanation</p>
<p>The specificity of a confusion matrix is the true negatives, divided by the true negatives plus the false positives. In this case, it is 15/(15+10) = 0.6</p>
</div>
</div>
<div class="action"><button id="Q1_button" onclick="checkAnswer({1: 'numerical', 2: 'numerical'})" class="problem_mo_button">Check</button><button id="Q1_button_show" onclick="showHideSolution({1: 'numerical', 2: 'numerical'}, 1, [1, 2])" class="problem_mo_button">Show Answer</button></div>
</div>
<h2 class="subhead">Quick Question</h2>
<div class="self_assessment">
<div id="Q3_div" class="problem_question">
<p display_name="Quick Question" url_name="Quick_Question_197">To go from Confusion Matrix #1 to Confusion Matrix #2, did we increase or decrease the threshold value?</p>
<fieldset><legend class="visually-hidden">Exercise 3</legend>
<div class="choice"><label id="Q3_input_1_label"><span id="Q3_input_1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q3_input_1" onclick="optionSelected(3)" name="Q3_input" class="problem_radio_input" correct="true" /><span class="choice">We increased the threshold value.</span><span id="Q3_input_1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q3_input_2_label"><span id="Q3_input_2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="radio" id="Q3_input_2" onclick="optionSelected(3)" name="Q3_input" class="problem_radio_input" correct="false" /><span class="choice">We decreased the threshold value.</span><span id="Q3_input_2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
</fieldset></div>
<div id="S3_div" class="problem_solution" tabindex="-1" display_name="Quick Question" url_name="Quick_Question_199">
<div class="detailed-solution">
<p>Explanation</p>
<p>We predict the outcome 1 less often in Confusion Matrix #2. This means we must have increased the threshold.</p>
</div>
</div>
<div class="action"><button id="Q2_button" onclick="checkAnswer({3: 'multiple_choice'})" class="problem_mo_button">Check</button><button id="Q2_button_show" onclick="showHideSolution({3: 'multiple_choice'}, 2, [3])" class="problem_mo_button">Show Answer</button></div>
</div>
<ul class="navigation progress">
    <li id="bck_btn"><a href="./resolveuid/7bf86a6c2bb6629ed20e4dd216833197">Back<span>Video 5: Thresholding</span></a></li>
    <li id="continue_btn"><a href="./resolveuid/f62162651257bdbe48268a5e5b311096">Continue<span>Video 6: ROC Curves</span></a></li>
</ul>