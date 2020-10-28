---
layout: post
title: Localization| Chart  | ASP.NET CORE | Syncfusion
description: Learn how to localize chart based on a specific culture.
platform: aspnet-core
control: Chart
documentation: ug
---

# Localization

Chart supports localization for its axis labels and tooltip. To render the chart with specific culture, refer to the corresponding **globalize** culture script, and specify the culture name in **Locale** property of chart.

{% highlight cshtml %}

<!--Refer french globalize culture script-->
<script src="../scripts/cultures/globalize.culture.fr-FR.min.js"></script>

<ej-chart id="chartContainer" locale="fr-FR">
</ej-chart>

{% endhighlight %}

![](Localization_images/Localization_img1.png)