---
layout: post
title: Sorting in ComboBox control for Syncfusion ASP.NET CORE
description: Sorting support to ComboBox control for Syncfusion ASP.NET CORE
platform: aspnet-core
control: ComboBox
documentation: ug
keywords: sortorder
---

# Sorting

The ComboBox has built-in support to sort data items when `SortOrder` is specified. The available sort orders are ascending, descending and none.

To sort the data in ascending order, set the `SortOrder` as ascending.

The following sample illustrates how to sort the data.



{% highlight html%}

<div class="frame">
        <div class="control"> 
        <ej-combo-box id="select" datasource="(IEnumerable<Countries>)ViewBag.datasource" placeholder="Select" sort-order="Ascending">
            <e-combo-box-fields text="text"/>
        </ej-combo-box>
        </div>
    </div>

{% endhighlight%}

{% highlight c# %}

        public string text { get; set; }
        public string category { get; set; }
        public static List<Countries> GetCountries()
        {
            List<Countries> country = new List<Countries>();
            country.Add(new Countries { text = "Austria", category = "A" });
            country.Add(new Countries { text = "Australia", category = "A" });
            country.Add(new Countries { text = "Antarctica", category = "A" });
            country.Add(new Countries { text = "Bangladesh", category = "B" });
            country.Add(new Countries { text = "Brazil", category = "B" });
            country.Add(new Countries { text = "Canada", category = "C" });
            country.Add(new Countries { text = "Cuba", category = "C" });
            country.Add(new Countries { text = "Denmark", category = "D" });
            country.Add(new Countries { text = "Dominica", category = "D" });
            return country;
        }
    }
}

{% endhighlight %}

Output for Sorting  is as follows.


![](Combobox_sorting_images/sorting.png)
