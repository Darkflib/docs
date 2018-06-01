---
title: Custom Chart Debug Page
toc: false
---

The **Custom Chart** debug page in the Admin UI can be used to create a custom chart showing any combination of over [200 available metrics](#available-metrics).

The definition of the customized dashboard is encoded in the URL. To share the dashboard with someone, send them the URL. Like any other URL, it can be bookmarked, sit in a pinned tab in your browser, etc.

<div id="toc"></div>

## Getting there

To get to the **Custom Chart** debug page, [open the Admin UI](admin-ui-access-and-navigate.html), and either:

- Open <http://localhost:8080/#/debug/chart> in your browser (replacing `localhost` and `8080` with your node's host and port).

- Open any node's Admin UI debug page at <http://localhost:8080/#/debug> in your browser (replacing `localhost` and `8080` with your node's host and port), scroll down to the **UI Debugging** section, and click **Custom Time-Series Chart**.

## Query options

The dropdown menus above the chart are used to set:

- The time span to chart
- The units to display

<img src="{{ 'images/v2.0/admin-ui-custom-chart-debug-00.png' | relative_url }}" alt="CockroachDB Admin UI" style="border:1px solid #eee;max-width:100%" />

The table below the chart shows which metrics are being queried, and how they'll be combined and displayed.

Options include:

{% include {{page.version.version}}/admin-ui-custom-chart-debug-page-00.html %}

## Examples

### Query user and system CPU usage

<img src="{{ 'images/v2.0/admin-ui-custom-chart-debug-00.png' | relative_url }}" alt="CockroachDB Admin UI" style="border:1px solid #eee;max-width:100%" />

To compare system vs. userspace CPU usage, select the following values under **Metric Name**:

+ `sys.cpu.sys.percent`
+ `sys.cpu.user.percent`

The Y-axis label is the **Count**. A count of 1 represents 100% utilization. The **Aggregator** of **Sum** can show the count to be above 1, which would mean CPU utilization is greater than 100%.

Checking **Per Node** displays statistics for each node, which could show whether an individual node's CPU usage was higher or lower than the average.

## Available metrics

{{site.data.alerts.callout_info}}
This list is taken directly from the source code and is subject to change. Some of the metrics listed below are already visible in other areas of the [Admin UI](admin-ui-overview.html).
{{site.data.alerts.end}}

{% include {{page.version.version}}/metric-names.md %}

## See also

+ [Troubleshooting Overview](troubleshooting-overview.html)
+ [Support Resources](support-resources.html)
+ [Raw Status Endpoints](monitoring-and-alerting.html#raw-status-endpoints)
