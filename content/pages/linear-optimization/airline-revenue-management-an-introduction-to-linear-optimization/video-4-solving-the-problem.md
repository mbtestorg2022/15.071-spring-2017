---
content_type: page
parent_title: '8.2 Airline Revenue Management: An Introduction to Linear Optimization '
parent_uid: 2900efa7-1aff-756d-feba-74c6d16f2d3d
title: '8.2 Airline Revenue Management: An Introduction to Linear Optimization '
uid: 86a033cc-e142-d448-a8bb-9112a73f89db
---

*   [<Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-590)
*   [8.2.1Video 1: Introduction]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization)
*   [8.2.2Video 2: A Single Flight]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-2-a-single-flight)
*   [8.2.3Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-581)
*   [8.2.4Video 3: The Problem Formulation]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-3-the-problem-formulation)
*   [8.2.5Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-590)
*   [8.2.6Video 4: Solving the Problem]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-4-solving-the-problem)
*   [8.2.7Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-598)
*   [8.2.8Video 5: Visualizing the Problem]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-5-visualizing-the-problem)
*   [8.2.9Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-606)
*   [8.2.10Video 6: Sensitivity Analysis]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-6-sensitivity-analysis)
*   [8.2.11Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-614)
*   [8.2.12Video 7: Connecting Flights]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-7-connecting-flights)
*   [8.2.13Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-620)
*   [8.2.14Video 8: The Edge of Revenue Management]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/video-8-the-edge-of-revenue-management)
*   [\>Quick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-598)

Video 4: Solving the Problem
----------------------------

In this video, we'll be solving our optimization problem using the spreadsheet AirlineRM. If you are using LibreOffice or OpenOffice, please download and open the spreadsheet [AirlineRM (ODS)]({{< baseurl >}}/resources/airlinerm) to follow along with the lecture. If you are using Microsoft Excel, please download and open the spreadsheet [AirlineRM (XLSX)]({{< baseurl >}}/resources/airlinerm-1) to follow along with the lecture. The following spreadsheets have the completed model as it is at the end of the video: [AirlineRM\_Complete (ODS)]({{< baseurl >}}/resources/airlinerm_complete) and [AirlineRM\_Complete (XLSX)]({{< baseurl >}}/resources/airlinerm_complete-1).

If you are using LibreOffice or OpenOffice, the functions and solver will look very similar to what you see in this video. **If you are using Microsoft Excel, please see the helpful tips below this video.**

{{< resource 2aee3adb-3118-2d75-3b1a-8145cc77261a >}}

Helpful Tips for Excel
----------------------

If you are using Microsoft Excel, the functions and solver you will be using are similar, but not identical, to what you see in the video. Here are some helpful tips to assist in using Excel for this class.

*   Unlike LibreOffice and OpenOffice, the "Solver" option does not typically come pre-loaded into Excel. **If you are on a Mac** and you don't see "Solver..." in the Tools menu, you will need to add it in by going to the Tools menu, and selecting "Add-Ins...". Then, check "Solver.Xlam" if it is not already checked, and click OK. You should now see "Solver..." under the Tools menu. **If you are on a Windows computer** and you don't see Solver in the Data tab, go to the File menu, and click on "Options". Then select "Add-ins", then "Manage Excel Add-ins" and click Go. Check "Solver Add-in" if it is not already checked, and click OK. You might need to search for "SOLVER.XLAM" if you don't see a checkbox and click through a security warning about running macros within Excel - please click ok and run the macros. You should now see Solver in the Analysis section of the Data tab. You might experience various issues if you are using an older version of Excel - you can search on Google to get help with these problems. 
*   When using the sumproduct function, you should separate the two groups of cells with a comma, instead of a semicolon. So whenever we say semicolon in LibreOffice, you probably want a comma in Excel.
*   Specifying the objective and decision variables is very similar to how it is done in LibreOffice, but the constraints are slightly different. To add a new constraint, you should click on the "Add" button to the right of the "Subject to the Constraints" box. This will change the window into one that looks more like how we are adding constraints in LibreOffice. After filling in the left-hand-side, sign, and right-hand-side, you can click on "Add" to add the constraint to your model and to continue adding constraints, or click "OK" to stop adding constraints. If you click "Cancel" it will just bring you back to the Solver window, without doing anything. You can change or delete a constraint by just selecting it and clicking the "Change" or "Delete" buttons next to the "Subject to the Constraints" box. 
*   Excel has a nice way of specifying non-negativity constraints. You can just check the "Make Unconstrained Variables Non-Negative" box insteading of adding the non-negativity constraints. 
*   You should always select the "Simplex LP" solving method in this class. 

*   [BackQuick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-590)
*   [ContinueQuick Question]({{< baseurl >}}/pages/linear-optimization/airline-revenue-management-an-introduction-to-linear-optimization/quick-question-598)