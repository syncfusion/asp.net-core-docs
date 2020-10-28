---
layout: post
title: Localization in DropDownList control for Syncfusion ASP.NET Core
description: Describes about Localization in DropDownList control for Syncfusion ASP.NET Core
platform: aspnet-core
control: DropDownList
documentation: ug
---
# Localization

The DropDownList provides option to localize its strings, it is used to adapting the DropDownList to a particular local language. By default, the DropDownList will use the US English (en-US) as its language.

N> The culture name has to be specified in a standard format such as [Language Code]-[County/Region Code].

To localize the dropdownlist’s strings with your own localization, copy the default language informations and localize the strings in the values column. For example, to localize the DropDownList in German language (“de-DE”).

{% highlight javascript %}

    ej.DropDownList.Locale["de-DE"] = {
        emptyResultText: "Keine Vorschläge" //replace with your text  
    };
    
{% endhighlight %}

Set the locale property of the DropDownList to the new language.

{% highlight CSHTML %}

    <ej-drop-down-list id="dropdown" datasource="ViewBag.datasource" locale="de-DE" watermark-text="Select a Student" enable-filter-search="true" filter-type="@SearchFilterType.StartsWith">
        <e-drop-down-list-fields text="Text" value="Value" />
    </ej-drop-down-list>

{% endhighlight %}

![](Localization_images/Locale.png)