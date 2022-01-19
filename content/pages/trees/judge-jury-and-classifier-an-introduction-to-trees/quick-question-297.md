---
content_type: page
parent_title: '4.2 Judge, Jury, and Classifier: An Introduction to Trees '
parent_uid: 11f9b44d-c296-0689-414b-8c313764a18d
title: '4.2 Judge, Jury, and Classifier: An Introduction to Trees '
uid: ff7dc49d-2cde-fc1a-c3e5-d01f07046ac1
---
<ul class="navigation pagination">
    <li id="top_bck_btn"><a href="./resolveuid/d818f0620c7e3cee943507c440503537">&lt;<span>Video 5: Random Forests</span></a></li>
    <li id="flp_btn_1"><a href="./resolveuid/11f9b44dc2960689414b8c313764a18d">4.2.1<span>Video 1: The Supreme Court</span></a></li>
    <li id="flp_btn_2"><a href="./resolveuid/b707db7f99009e83423e4911e4d83568">4.2.2<span>Quick Question</span></a></li>
    <li id="flp_btn_3"><a href="./resolveuid/fbeabfb3e0a4b479efe5ffb5d7cf5d4a">4.2.3<span>Video 2: CART</span></a></li>
    <li id="flp_btn_4"><a href="./resolveuid/076a36ddc951926fd5c99ccb41e476d9">4.2.4<span>Quick Question</span></a></li>
    <li id="flp_btn_5"><a href="./resolveuid/ca1564b0917866a3a00e801c8c9fdbbc">4.2.5<span>Video 3: Splitting and Predictions</span></a></li>
    <li id="flp_btn_6"><a href="./resolveuid/9788174fbc238176217873d882264bfd">4.2.6<span>Quick Question</span></a></li>
    <li id="flp_btn_7"><a href="./resolveuid/a0af0b83fff43d634dfe02e15106f92d">4.2.7<span>Video 4: CART in R</span></a></li>
    <li id="flp_btn_8"><a href="./resolveuid/8f336b6d3260d3a128f288e99dda1c42">4.2.8<span>Quick Question</span></a></li>
    <li id="flp_btn_9"><a href="./resolveuid/d818f0620c7e3cee943507c440503537">4.2.9<span>Video 5: Random Forests</span></a></li>
    <li id="flp_btn_10" class="button_selected"><a href="./resolveuid/ff7dc49d2cdefc1ac3e5d01f07046ac1">4.2.10<span>Quick Question</span></a></li>
    <li id="flp_btn_11"><a href="./resolveuid/aed8634b040dd1af7abb68e999cb9c43">4.2.11<span>Video 6: Cross-Validation</span></a></li>
    <li id="flp_btn_12"><a href="./resolveuid/0be06c807e39cc4e2808dc63ffaa5efa">4.2.12<span>Quick Question</span></a></li>
    <li id="flp_btn_13"><a href="./resolveuid/2ca2e4f174a66019fbe68e97bba87376">4.2.13<span>Video 7: The Model v. The Experts</span></a></li>
    <li id="top_continue_btn"><a href="./resolveuid/aed8634b040dd1af7abb68e999cb9c43">&gt;<span>Video 6: Cross-Validation</span></a></li>
</ul>
<h2 class="subhead">Quick Question</h2>
<div class="self_assessment">
<p display_name="Quick Question" url_name="Quick_Question_299"><b> Important Note: </b> When creating random forest models, you might still get different answers from the ones you see here even if you set the random seed. This has to do with different operating systems and the random forest implementation.</p>
<p display_name="Quick Question" url_name="Quick_Question_300">Let's see what happens if we set the seed to two different values and create two different random forest models.</p>
<div id="Q1_div" class="problem_question">
<p display_name="Quick Question" url_name="Quick_Question_301">First, set the seed to 100, and the re-build the random forest model, exactly like we did in the previous video (Video 5). Then make predictions on the test set. What is the accuracy of the model on the test set?</p>
<fieldset><legend class="visually-hidden">Exercise 1</legend>
<div class="choice"><label id="Q1_label"><span id="Q1_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q1_input" value="" onkeypress="numericTypedOrDropDownSelected(1)" class="problem_text_input" /><input type="hidden" id="Q1_ans" value="0.6882353" /><input type="hidden" id="Q1_tolerance" value="0.1" /><span id="Q1_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S1_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="Q2_div" class="problem_question">
<p display_name="Quick Question" url_name="Quick_Question_303">Now, set the seed to 200, and then re-build the random forest model, exactly like we did in the previous video (Video 5). Then make predictions on the test set. What is the accuracy of this model on the test set?</p>
<fieldset><legend class="visually-hidden">Exercise 2</legend>
<div class="choice"><label id="Q2_label"><span id="Q2_aria_status" tabindex="-1" class="visually-hidden">&amp;nbsp;</span><span class="visually-hidden">Numerical Response</span><input type="text" id="Q2_input" value="" onkeypress="numericTypedOrDropDownSelected(2)" class="problem_text_input" /><input type="hidden" id="Q2_ans" value="0.7058824" /><input type="hidden" id="Q2_tolerance" value="0.1" /><span id="Q2_normal_status" class="nostatus" aria-hidden="true">&amp;nbsp;</span></label></div>
<p id="S2_ans" tabindex="-1" class="problem_answer">&nbsp;</p>
</fieldset></div>
<div id="S1_div" class="problem_solution" tabindex="-1" display_name="Quick Question" url_name="Quick_Question_305">
<div class="detailed-solution">
<p>Explanation</p>
<p>You can create the models and compute the accuracies with the following commands in R:</p>
<p>set.seed(100)</p>
<p>StevensForest = randomForest(Reverse ~ Circuit + Issue + Petitioner + Respondent + LowerCourt + Unconst, data = Train, ntree=200, nodesize=25)</p>
<p>PredictForest = predict(StevensForest, newdata = Test)</p>
<p>table(Test$Reverse, PredictForest)</p>
<p>and then repeat it, but with set.seed(200) first.</p>
<p>As we see here, the random component of the random forest method can change the accuracy. The accuracy for a more stable dataset will not change very much, but a noisy dataset can be significantly affected by the random samples.</p>
</div>
</div>
<div class="action"><button id="Q1_button" onclick="checkAnswer({1: 'numerical', 2: 'numerical'})" class="problem_mo_button">Check</button><button id="Q1_button_show" onclick="showHideSolution({1: 'numerical', 2: 'numerical'}, 1, [1])" class="problem_mo_button">Show Answer</button></div>
</div>
<ul class="navigation progress">
    <li id="bck_btn"><a href="./resolveuid/d818f0620c7e3cee943507c440503537">Back<span>Video 5: Random Forests</span></a></li>
    <li id="continue_btn"><a href="./resolveuid/aed8634b040dd1af7abb68e999cb9c43">Continue<span>Video 6: Cross-Validation</span></a></li>
</ul>