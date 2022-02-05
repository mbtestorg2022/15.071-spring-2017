---
content_type: page
parent_title: '9.2 Sports Scheduling: An Introduction to Integer Optimization '
parent_uid: fbf2b704-9246-466e-f247-36bff248b7c3
title: '9.2 Sports Scheduling: An Introduction to Integer Optimization '
uid: d7c69cd7-0f13-ee07-7976-805c01b4a9e2
---

*   [\<Sports Scheduling: An Introduction to Integer Optimization]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization)
*   [9.2.1Video 1: Introduction]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization)
*   [9.2.2Quick Question]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization/quick-question-665)
*   [9.2.3Video 2: The Optimization Problem]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization/video-2-the-optimization-problem)
*   [9.2.4Quick Question]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization/quick-question-673)
*   [9.2.5Video 3: Solving the Problem]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization/video-3-solving-the-problem-2)
*   [9.2.6Quick Question]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization/quick-question-685)
*   [9.2.7Video 4: Logical Constraints]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization/video-4-logical-constraints)
*   [9.2.8Quick Question]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization/quick-question-693)
*   [9.2.9Video 5: The Edge]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization/video-5-the-edge)
*   [\>Video 2: The Optimization Problem]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization/video-2-the-optimization-problem)

Quick Question
--------------

{{< quiz_multiple_choice questionId="Q1_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="true" >}}&nbsp;A plays B, C plays D, and E plays F&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;A plays C, B plays D, and C plays F&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;A plays F, B plays E, and C plays D&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;A plays B, B plays C, and C plays D&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;A plays D, B plays E, and C plays F&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

Each of the teams has to play exactly one of the other teams for the games to occur simultaneously. In the second option, C is playing twice, which is impossible. In the fourth option, B and C are both playing twice.{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}{{< quiz_multiple_choice questionId="Q2_div" >}}{{< quiz_choices >}}{{< quiz_choice isCorrect="false" >}}&nbsp;5&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;10&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="true" >}}&nbsp;15&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;20&nbsp;{{< /quiz_choice >}}
{{< quiz_choice isCorrect="false" >}}&nbsp;25&nbsp;{{< /quiz_choice >}}{{< /quiz_choices >}}
{{< quiz_solution >}}Explanation

There are 15 different feasible schedules. We can count them by observing that A can play any of the 5 teams. Once this is fixed, we have 4 teams left. There are 3 ways to make two pairs out of 4 teams. So in total, there are 5\*3 = 15 different schedules. Here is a list of all of them:

A plays B, C plays D, E plays F

A plays B, C plays E, D plays F

A plays B, C plays F, D plays E

A plays C, B plays D, E plays F

A plays C, B plays E, D plays F

A plays C, B plays F, D plays E

A plays D, B plays C, E plays F

A plays D, B plays E, C plays F

A plays D, B plays F, C plays E

A plays E, B plays C, D plays F

A plays E, B plays D, C plays F

A plays E, B plays F, C plays D

A plays F, B plays C, D plays E

A plays F, B plays D, C plays E

A plays F, B plays E, C plays D{{< /quiz_solution >}}{{< /quiz_multiple_choice >}}

*   [BackSports Scheduling: An Introduction to Integer Optimization]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization)
*   [ContinueVideo 2: The Optimization Problem]({{< baseurl >}}/pages/integer-optimization/sports-scheduling-an-introduction-to-integer-optimization/video-2-the-optimization-problem)