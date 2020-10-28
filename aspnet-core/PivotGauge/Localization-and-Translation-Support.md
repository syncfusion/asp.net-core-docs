---
layout: post
title: Localization | ASP.NET Core | PivotGauge | Syncfusion
description: This document illustrates that how to define localization with respective to the modes in ASP.NET Core PivotGauge control
platform: aspnet-core
control: PivotGauge
documentation: ug
---

# Localization

## Localization in pivot gauge control
You can localize the pivot gauge control texts with a collection of localized strings by using the **"ej.PivotGauge.Locale"** for different cultures.
 
N> By default, the pivot gauge control is localized in **"en-US"**.
 
Following code example illustrates how to localize the pivot gauge based on **"French"** culture:

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1" locale="fr-FR"></ej-pivot-gauge>

<script>
    ej.PivotGauge.Locale["fr-FR"] = {
        RevenueGoal: "Objectif de chiffre d'affaires",
        RevenueValue: "Valeur du chiffre d'affaires"
    }
</script>

{% endhighlight %}

Following table localizes the in-built keywords to **"French"** culture for the pivot gauge:

<table>
<tr>
<th>
Keywords</th><th>
Values</th></tr>
<tr>
<td>
RevenueGoal</td><td>
"Objectif de chiffre d'affaires"</td></tr>
<tr>
<td>
RevenueValue</td><td>
"Valeur du chiffre d'affaires "</td></tr>
</table>

## Localization and globalization of cube info

The content displayed within the pivot gauge control is obtained from the OLAP cube.

To get the localized string based on different cultures, set the **"Locale Identifier"** in the connection string to a specific culture of the OLAP cube. The attribute is set for the pivot gauge in client mode as shown follows:

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1" locale="fr-FR">
    <e-data-source catalog="Adventure Works DW 2008 SE" cube="Adventure Works" data="//bi.syncfusion.com/olap/msmdpump.dll;Locale Identifier=1036"></e-data-source>
</ej-pivot-gauge>

{% endhighlight %}

![Localization in ASP NET Core pivot gauge control](Localization-and-Translation-Support_images/Localization.png) 
