---
content_type: page
parent_title: '3.3 The Framingham Heart Study: Evaluating Risk Factors to Save Lives '
parent_uid: 58bb6065-48df-9c3a-8c14-8318a4e0e5c7
title: '3.3 The Framingham Heart Study: Evaluating Risk Factors to Save Lives '
uid: 9b282848-c7ee-4f02-8080-13bb442f487c
---
<ul class="navigation pagination">
    <li id="top_bck_btn"><a href="./resolveuid/8a9ba6a68196ffcd9f101b66733dbcb0">&lt;<span>Video 3: A Logistic Regression Model</span></a></li>
    <li id="flp_btn_1"><a href="./resolveuid/58bb606548df9c3a8c148318a4e0e5c7">3.3.1<span>Video 1: The Framingham Heart Study</span></a></li>
    <li id="flp_btn_2"><a href="./resolveuid/68185a3fa6032c323cac5f62061ce192">3.3.2<span>Quick Question</span></a></li>
    <li id="flp_btn_3"><a href="./resolveuid/0d81134389999639fbba0487029acf21">3.3.3<span>Video 2: Risk Factors</span></a></li>
    <li id="flp_btn_4"><a href="./resolveuid/41ef73a1494f0f228a21a56a082cb9ca">3.3.4<span>Quick Question</span></a></li>
    <li id="flp_btn_5"><a href="./resolveuid/8a9ba6a68196ffcd9f101b66733dbcb0">3.3.5<span>Video 3: A Logistic Regression Model</span></a></li>
    <li id="flp_btn_6" class="button_selected"><a href="./resolveuid/9b282848c7ee4f02808013bb442f487c">3.3.6<span>Quick Question</span></a></li>
    <li id="flp_btn_7"><a href="./resolveuid/4f9a84c34f7f3867891dbe7fae75a149">3.3.7<span>Video 4: Validating the Model</span></a></li>
    <li id="flp_btn_8"><a href="./resolveuid/332c772ac3431943e27c0bb91f073b40">3.3.8<span>Quick Question</span></a></li>
    <li id="flp_btn_9"><a href="./resolveuid/4d65e7631a9d6885f511959c8382aa48">3.3.9<span>Video 5: Interventions</span></a></li>
    <li id="flp_btn_10"><a href="./resolveuid/3a429d7bb7cc36d231ba2a9cdd7dc04e">3.3.10<span>Quick Question</span></a></li>
    <li id="flp_btn_11"><a href="./resolveuid/001f5747862d225993bf38e6c5e9227e">3.3.11<span>Video 6: Overall Impact</span></a></li>
    <li id="top_continue_btn"><a href="./resolveuid/4f9a84c34f7f3867891dbe7fae75a149">&gt;<span>Video 4: Validating the Model</span></a></li>
</ul>
<h2 class="subhead">Quick Question</h2>
<div class="self_assessment">
<p display_name="Quick Question" url_name="Quick_Question_235">In the previous video, we computed the following confusion matrix for our logistic regression model on our test set with a threshold of 0.5:</p>
<div class="maintabletemplate">
	<table class="tablewidth25" display_name="Quick Question" url_name="Quick_Question_236">
    <tbody>
        <tr>
            <td>&nbsp;</td>
            <td>FALSE</td>
            <td>TRUE</td>
        </tr>
        <tr>
            <td>0</td>
            <td>1069</td>
            <td>6</td>
        </tr>
        <tr>
            <td>1</td>
            <td>187</td>
            <td>11</td>
        </tr>
    </tbody>
</table>
<p display_name="Quick Question" url_name="Quick_Question_237">Using this confusion matrix, answer the following questions.</p>
<div id="Q1_div" class="problem_question">
<p display_name="Quick Question" url_name="Quick_Question_238">What is the sensitivity of our logistic regression model on the test set, using a threshold of 0.5?</p>
<fieldset><legend class="visually-hidden">Exercise 1</legend>
<div class="choice"><label id="Q1_label"><span id="Q1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q1_input" value="" onkeypress="numericTypedOrDropDownSelected(1)" class="problem_text_input" /><input type="hidden" id="Q1_ans" value="0.05555556" /><input type="hidden" id="Q1_tolerance" value="1%" /><span id="Q1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S1_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="Q2_div" class="problem_question">
<p display_name="Quick Question" url_name="Quick_Question_240">What is the specificity of our logistic regression model on the test set, using a threshold of 0.5?</p>
<fieldset><legend class="visually-hidden">Exercise 2</legend>
<div class="choice"><label id="Q2_label"><span id="Q2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q2_input" value="" onkeypress="numericTypedOrDropDownSelected(2)" class="problem_text_input" /><input type="hidden" id="Q2_ans" value="0.9944186" /><input type="hidden" id="Q2_tolerance" value="1%" /><span id="Q2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S2_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="S1_div" class="problem_solution" tabindex="-1" display_name="Quick Question" url_name="Quick_Question_242">
<div class="detailed-solution">
<p>Explanation</p>
<p>Using this confusion matrix, we can compute that the sensitivity is 11/(11+187) and the specificity is 1069/(1069+6).</p>
</div>
</div>
<div class="action"><button id="Q1_button" onclick="checkAnswer({1: 'numerical', 2: 'numerical'})" class="problem_mo_button">Check</button><button id="Q1_button_show" onclick="showHideSolution({1: 'numerical', 2: 'numerical'}, 1, [1])" class="problem_mo_button">Show Answer</button></div>
</div>
<ul class="navigation progress">
    <li id="bck_btn"><a href="./resolveuid/8a9ba6a68196ffcd9f101b66733dbcb0">Back<span>Video 3: A Logistic Regression Model</span></a></li>
    <li id="continue_btn"><a href="./resolveuid/4f9a84c34f7f3867891dbe7fae75a149">Continue<span>Video 4: Validating the Model</span></a></li>
</ul>