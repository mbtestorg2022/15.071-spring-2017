---
content_type: page
parent_title: '4.2 Judge, Jury, and Classifier: An Introduction to Trees '
parent_uid: 11f9b44d-c296-0689-414b-8c313764a18d
title: '4.2 Judge, Jury, and Classifier: An Introduction to Trees '
uid: 076a36dd-c951-926f-d5c9-9ccb41e476d9
---
<ul class="navigation pagination">
    <li id="top_bck_btn"><a href="./resolveuid/fbeabfb3e0a4b479efe5ffb5d7cf5d4a">&lt;<span>Video 2: CART</span></a></li>
    <li id="flp_btn_1"><a href="./resolveuid/11f9b44dc2960689414b8c313764a18d">4.2.1<span>Video 1: The Supreme Court</span></a></li>
    <li id="flp_btn_2"><a href="./resolveuid/b707db7f99009e83423e4911e4d83568">4.2.2<span>Quick Question</span></a></li>
    <li id="flp_btn_3"><a href="./resolveuid/fbeabfb3e0a4b479efe5ffb5d7cf5d4a">4.2.3<span>Video 2: CART</span></a></li>
    <li id="flp_btn_4" class="button_selected"><a href="./resolveuid/076a36ddc951926fd5c99ccb41e476d9">4.2.4<span>Quick Question</span></a></li>
    <li id="flp_btn_5"><a href="./resolveuid/ca1564b0917866a3a00e801c8c9fdbbc">4.2.5<span>Video 3: Splitting and Predictions</span></a></li>
    <li id="flp_btn_6"><a href="./resolveuid/9788174fbc238176217873d882264bfd">4.2.6<span>Quick Question</span></a></li>
    <li id="flp_btn_7"><a href="./resolveuid/a0af0b83fff43d634dfe02e15106f92d">4.2.7<span>Video 4: CART in R</span></a></li>
    <li id="flp_btn_8"><a href="./resolveuid/8f336b6d3260d3a128f288e99dda1c42">4.2.8<span>Quick Question</span></a></li>
    <li id="flp_btn_9"><a href="./resolveuid/d818f0620c7e3cee943507c440503537">4.2.9<span>Video 5: Random Forests</span></a></li>
    <li id="flp_btn_10"><a href="./resolveuid/ff7dc49d2cdefc1ac3e5d01f07046ac1">4.2.10<span>Quick Question</span></a></li>
    <li id="flp_btn_11"><a href="./resolveuid/aed8634b040dd1af7abb68e999cb9c43">4.2.11<span>Video 6: Cross-Validation</span></a></li>
    <li id="flp_btn_12"><a href="./resolveuid/0be06c807e39cc4e2808dc63ffaa5efa">4.2.12<span>Quick Question</span></a></li>
    <li id="flp_btn_13"><a href="./resolveuid/2ca2e4f174a66019fbe68e97bba87376">4.2.13<span>Video 7: The Model v. The Experts</span></a></li>
    <li id="top_continue_btn"><a href="./resolveuid/ca1564b0917866a3a00e801c8c9fdbbc">&gt;<span>Video 3: Splitting and Predictions</span></a></li>
</ul>
<h2 class="subhead">Quick Question</h2>
<div class="self_assessment">
<p display_name="Quick Question" url_name="Quick_Question_260">Suppose that you have the following CART tree:</p>
<img display_name="Quick Question" src="./resolveuid/b2eea6fba57db424a4844f679aee4bc9" url_name="Quick_Question_261" alt="Example of a cart tree." />
<div id="Q1_div" class="problem_question">
<p display_name="Quick Question" url_name="Quick_Question_262">How many splits are in this tree?</p>
<fieldset><legend class="visually-hidden">Exercise 1</legend>
<div class="choice"><label id="Q1_label"><span id="Q1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q1_input" value="" onkeypress="numericTypedOrDropDownSelected(1)" class="problem_text_input" /><input type="hidden" id="Q1_ans" value="3" /><input type="hidden" id="Q1_tolerance" value="0" /><span id="Q1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S1_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="Q2_div" class="problem_question">
<p display_name="Quick Question" url_name="Quick_Question_264">For which data observations should we predict &quot;Red&quot;, according to this tree? Select all that apply.</p>
<fieldset><legend class="visually-hidden">Exercise 2</legend>
<div class="choice"><label id="Q2_input_1_label"><span id="Q2_input_1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q2_input_1" onclick="optionSelected(2)" name="Q2_input" class="problem_radio_input" correct="true" /><span class="choice">If X is less than 60, and Y is any value.</span><span id="Q2_input_1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q2_input_2_label"><span id="Q2_input_2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q2_input_2" onclick="optionSelected(2)" name="Q2_input" class="problem_radio_input" correct="false" /><span class="choice">If X is greater than or equal to 60, and Y is greater than or equal to 20.</span><span id="Q2_input_2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q2_input_3_label"><span id="Q2_input_3_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q2_input_3" onclick="optionSelected(2)" name="Q2_input" class="problem_radio_input" correct="false" /><span class="choice">If X is greater than or equal to 85, and Y is less than 20.</span><span id="Q2_input_3_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<div class="choice"><label id="Q2_input_4_label"><span id="Q2_input_4_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><input type="checkbox" id="Q2_input_4" onclick="optionSelected(2)" name="Q2_input" class="problem_radio_input" correct="true" /><span class="choice">If X is greater than or equal to 60 and less than 85, and Y is less than 20.</span><span id="Q2_input_4_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="Q2_status_combined" tabindex="-1" class="nostatus">&nbsp;</p>
</fieldset></div>
<div id="S1_div" class="problem_solution" tabindex="-1" display_name="Quick Question" url_name="Quick_Question_266">
<div class="detailed-solution">
<p>Explanation</p>
<p>This tree has three splits. The first split says to predict &quot;Red&quot; if X is less than 60, regardless of the value of Y. Otherwise, we move to the second split. The second split says to check the value of Y - if it is greater than or equal to 20, predict &quot;Gray&quot;. Otherwise, we move to the third split. This split checks the value of X again. If X is less than 85 (and greater than or equal to 60 by the first split) and Y is less than 20, then we predict &quot;Red&quot;. Otherwise, we predict &quot;Gray&quot;.</p>
</div>
</div>
<div class="action"><button id="Q1_button" onclick="checkAnswer({1: 'numerical', 2: 'choiceresponse'})" class="problem_mo_button">Check</button><button id="Q1_button_show" onclick="showHideSolution({1: 'numerical', 2: 'choiceresponse'}, 1, [1])" class="problem_mo_button">Show Answer</button></div>
</div>
<ul class="navigation progress">
    <li id="bck_btn"><a href="./resolveuid/fbeabfb3e0a4b479efe5ffb5d7cf5d4a">Back<span>Video 2: CART</span></a></li>
    <li id="continue_btn"><a href="./resolveuid/ca1564b0917866a3a00e801c8c9fdbbc">Continue<span>Video 3: Splitting and Predictions</span></a></li>
</ul>