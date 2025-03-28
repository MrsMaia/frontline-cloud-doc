---
title: "Trends"
description: "Learn how to compare test results."
lead: "Compare test results."
date: 2021-03-10T14:29:43+00:00
lastmod: 2021-08-05T13:13:30+00:00
weight: 10070
---

## Run / Trends

The runs list and trends for a simulation can be accessed by clicking on the {{< icon history >}} icon in the [simulations table]({{< ref "../simulations#simulations-table" >}}).

This view contains the list of your simulation's runs which can be filtered by name and/or status and the trends which are displaying information between those runs.
{{< img src="run-trends.png" alt="Run trends" >}}

### Runs table

{{< img src="run-table.png" alt="Run table" >}}

Just like for the result of the latest run in the [simulations table]({{< ref "simulations#simulations-table" >}}), you
have access to the [logs]({{< ref "../simulations#logs" >}}) of the run by clicking on the {{< icon file-alt >}} icon
and you can sort the table by each columns. The logs are only available for runs which are not flagged as "Successful".

If there is one, You can click on the {{< icon search >}} icon next to the status to display the [assertions]({{< ref "../reports#assertions" >}}) of the run.
You can delete runs by selecting them and click on the **Delete** button in the action bar above the table.

You can comment a run by clicking on the {{< icon comment-alt >}} icon on the right side of the table.

{{< img src="comment.png" alt="Comment" >}}

You can also click on the {{< icon info-circle >}} icon to see a snapshot of the run configuration. The system properties beginning with `sensitive.` are not displayed.

{{< img src="snapshot.png" alt="Snapshot" >}}

### Run Comparison

{{< img src="compare-runs.png" alt="Compare runs" >}}

You can compare the results of two runs if you click on the "Compare runs" button in the table. It allows you to compare the response time and errors of the two runs for each request.

You can choose the specific metric you want to compare by clicking on the metric name, and the specific run you want to compare by clicking on the run number.

The delta and variance will be displayed, so you can check if there is a progression or a degradation in performance.

### Trends charts

The trends are charts that will display some globals statistics for each run (eg: requests count) so that you can easily see how well your runs went compared to each other.
Each run is represented by its number in the chart and the chart won't display the statistics of a failed run (eg: Timeout, broken, etc..).

{{< img src="trends.png" alt="Trends" >}}

You can filter the statistics shown by filtering through scenarios, groups or requests that are involved in each runs.
You can chose how many runs will be compared by changing the limit (10, 25, 50, 100):

{{< img src="trends-bar.png" alt="Trends bar" >}}
