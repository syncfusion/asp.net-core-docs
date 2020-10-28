---
layout: post
title: Named Set | PivotTreeMap | ASP.NET | Syncfusion
description: named set
platform: aspnet
control: PivotTreeMap
documentation: ug
---

# Named sets

Named sets is a multidimensional expression (MDX) that returns a set of dimension members, which can be created by combining the cube data, arithmetic operators, numbers, and functions.

You can bind the named sets in the pivot tree map by setting it's unique name in the `field-name` property in the row or column axis and `is-named-sets` Boolean property to true.

{% highlight js %}

<!--Create a tag which acts as a container for PivotTreeMap--> 
<ej-pivot-treemap id="PivotTreeMap1">
    <e-data-source catalog="Adventure Works DW 2008 SE" cube="Adventure Works" data="//bi.syncfusion.com/olap/msmdpump.dll">
        <e-pivot-rows>
            <e-row-field field-name="[Core Product Group]" is-named-sets="true"></e-row-field>
        </e-pivot-rows>
        <e-pivot-columns>
            <e-column-field field-name="[Customer].[Customer Geography]"></e-column-field>
        </e-pivot-columns>
        <e-pivot-values>
            <e-value-field axis="Column">
                <e-measures>
                    <e-measure-items field-name="[Measures].[Customer Count]"></e-measure-items>
                </e-measures>
            </e-value-field>
        </e-pivot-values>
    </e-data-source>
</ej-pivot-treemap>

<!--Tooltip labels can be localized here-->
<script id="tooltipTemplate" type="application/jsrender">
    <div style="background:White; color:black; font-size:12px; font-weight:normal; border: 1px solid #4D4D4D; white-space: nowrap;border-radius: 2px; margin-right: 25px; min-width: 110px;padding-right: 5px; padding-left: 5px; padding-bottom: 2px ;width: auto; height: auto;">
        <div>Measure(s) : {{:~Measures(#data)}}</div><div>Row : {{:~Row(#data)}}</div><div>Column : {{:~Column(#data)}}</div><div>Value : {{:~Value(#data)}}</div>
    </div>
</script>  

{% endhighlight %}

![](NamedSets_images/namedset.png)