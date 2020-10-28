---
layout: post
title: Filtering in ComboBox control for Syncfusion ASP.NET CORE
description: Filtering support to ComboBox control for Syncfusion ASP.NET CORE
platform: core
control: ComboBox
documentation: ug
keywords: allowFiltering, ComboBox, updateData, case sensitive filtering, filter type, minimum filter character
---

# Filtering

The ComboBox has built-in support to filter data items when the `allowFiltering` is enabled. The filter operation starts as soon as you start typing characters in the component.

To display the filtered items in the popup, filter the required data and return it to the ComboBox via **updateData** method by using the **filtering** event.

The following sample illustrates how to query the data source and pass the data to the ComboBox through the `updateData` method in the `filtering` event.


{% highlight html %}

    <div class="frame">
        <div class="control">
            <ej-combo-box id="searchcountry" datasource="(IEnumerable<Countries>)ViewBag.datasource" placeholder="Select a country" allow-filtering="true" width="100%" filtering="filtering">
                <e-combo-box-fields text="text" />
            </ej-combo-box>
        </div>
    </div>
    <script type="text/javascript">
        function filtering(e) {
            var query = new ej.Query().select(['text','category']);
            query = (e.text !== '') ? query.where('text', 'startswith', e.text, true) : query;
            e.updateData(e.model.dataSource, query);
        }
    </script>

{% endhighlight %}

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
            ...
            return country;
        }
    }
}

{% endhighlight %}


Output for filtering combobox control is as follows.


![](Combobox_filtering_images/filtering.png)


## Limit the minimum filter character

When filtering the list items, you can set the limit for character count to raise remote request and fetch filtered data on the ComboBox. This can be done by manual validation within the filter event handler.

In the following example, the remote request does not fetch the search data until the search key contains three characters.


{% highlight html %}

    <div class="frame">
        <div class="control">
            <ej-combo-box id="searchcountry" datasource="(IEnumerable<Countries>)ViewBag.datasource" placeholder="Select a country" allow-filtering="true" width="100%" filtering="filtering">
                <e-combo-box-fields text="text" />
            </ej-combo-box>
        </div>
    </div>
    <script type="text/javascript">
        function filtering(e) {
           if(e.text == '') e.updateData(e.model.dataSource);
            else{
                // restrict the remote request until search key contains 3 characters.
                if (e.text.length < 3) { return; }
                var query = new Query().select(['text', 'category']);
                query = (e.text !== '') ? query.where('text', 'startswith', e.text, true) : query;
                e.updateData(e.model.dataSource, query);
            }
        }
    </script>

{% endhighlight %}

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
            ...
            return country;
        }
    }
}

{% endhighlight %}




## Change the filter type

While filtering, you can change the filter type to `contains`, `startsWith`, or `endsWith` for string type within the filter event handler.

In the following examples, data filtering is done with the `endsWith` type.


{% highlight html %}

    <div class="frame">
        <div class="control">
            <ej-combo-box id="searchcountry" datasource="(IEnumerable<Countries>)ViewBag.datasource" placeholder="Select a country" allow-filtering="true" width="100%" filtering="filtering">
                <e-combo-box-fields text="text" />
            </ej-combo-box>
        </div>
    </div>
    <script type="text/javascript">
        function filtering(e) {
            var query = new ej.Query().select(['text','category']);
            query = (e.text !== '') ? query.where('text', 'endswith', e.text, true) : query;
            e.updateData(e.model.dataSource, query);
        }
    </script>

{% endhighlight %}

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
            ...
            return country;
        }
    }
}

{% endhighlight %}



Output for filtering combobox control is as follows.


![](Combobox_filtering_images/filter_type.png)

## Case sensitive filtering

Data items can be filtered either with or without case sensitivity using the DataManager. This can be done by passing the fourth optional parameter of the **where** clause.

The following example shows how to perform the case-sensitive filter.


{% highlight html %}

    <div class="frame">
        <div class="control">
           <ej-combo-box id="searchcountry" datasource="(IEnumerable<Countries>)ViewBag.datasource" placeholder="Select a country" allow-filtering="true" width="100%" filtering="filtering">
                <e-combo-box-fields text="text" />
            </ej-combo-box>
        </div>
    </div>
    <script type="text/javascript">
        function filtering(e) {
            var query = new ej.Query().select(['text','category']);
            query = (e.text !== '') ? query.where('text', 'startswith', e.text, false) : query;
            e.updateData(e.model.dataSource, query);
        }
    </script>

{% endhighlight %}

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
            ...
            return country;
        }
    }
}

{% endhighlight %}




Output for filtering combobox control is as follows:


![](Combobox_filtering_images/case_sensitive_filtering.png)
