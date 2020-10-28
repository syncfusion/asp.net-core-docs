---
layout: post
title: Functionalities in the DropDownList control for Syncfusion ASP.NET Core
description: Functionalities in the DropDownList control for Syncfusion ASP.NET Core
platform: aspnet-core
control: DropDownList
documentation: ug
keywords: DropDownList, dropdown, Selection, Grouping, Sorting

---
# Functionalities

## Selection

By default only one item can be selected from the popup list. For multiple selection, you have to enable [checkboxes](Checkbox). The selected item consist of active class (“e-active”) to differentiate it from other items.

The following API’s, select the items in the DropDownList via text or value or indices.

<table>
    <tr>
        <th>
            Properties
            <br/>
        </th>
        <th>
            Description
            <br/>
        </th>
    </tr>
    <tr>
        <td>
            {{'[value](http://help.syncfusion.com/js/api/ejdropdownlist#members:value)'| markdownify }} 
            <br/>
        </td>
        <td>
            To select an item initially, you can pass the item’s value via value property.
            <br/>
            Multiple items can select via value property, the given values should be separated by delimiter character.
        </td>
    </tr>
    <tr>
        <td>
            {{'[text](http://help.syncfusion.com/js/api/ejdropdownlist#members:text)'| markdownify }} 
            <br/>
        </td>
        <td>
            To select an item initially, you can pass the item’s text via text property.
            <br/>
            Multiple items can select via text property, the given values should be separated by delimiter character.
        </td>
    </tr>
    <tr>
        <td>
            {{'[selectedIndex](http://help.syncfusion.com/js/api/ejdropdownlist#members:selectedindex)'| markdownify }} 
            <br/>
        </td>
        <td>
            Select a single item by passing an index value to the selectedIndex property.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
             {{'[selectedIndices](http://help.syncfusion.com/js/api/ejdropdownlist#members:selectedindices)'| markdownify }}
            <br/>
        </td>
        <td>
            Select more than one items by passing index values to the selectedIndices property when multi selection enabled. 
            <br/>
        </td>
    </tr>
</table>

N> Index starts from 0 here.
N> To use “selectedIndices” property, you should enable wither ShowCheckbox or MultiSelectMode property.

The following methods, select the items in the DropDownList.

<table>
    <tr>
        <th>
            Methods
            <br/>
        </th>
        <th>
            Description
            <br/>
        </th>
    </tr>
    <tr>
        <td>
            {{'[selectItemByIndices](http://help.syncfusion.com/js/api/ejdropdownlist#methods:selectitembyindices)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to select the list of items in the DropDownList through the Index of the items.
        </td>
    </tr>
    <tr>
        <td>
            {{'[selectItemByText](http://help.syncfusion.com/js/api/ejdropdownlist#methods:selectItemByText)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to select an item in the DropDownList by using the given text value.
        </td>
    </tr>
    <tr>
        <td>
            {{'[selectItemByValue](http://help.syncfusion.com/js/api/ejdropdownlist#methods:selectitembyvalue)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to select an item in the DropDownList by using the given value.
            <br/>
        </td>
    </tr>
</table>

The following methods, used to retrieve the items from the DropDownList.

<table>
    <tr>
        <th>
            Methods
            <br/>
        </th>
        <th>
            Description
            <br/>
        </th>
    </tr>
    <tr>
        <td>
            {{'[getListData](http://help.syncfusion.com/js/api/ejdropdownlist#methods:getlistdata)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to retrieve the items that are bound with the DropDownList.
        </td>
    </tr>
    <tr>
        <td>
            {{'[getSelectedItem](http://help.syncfusion.com/js/api/ejdropdownlist#methods:getselecteditem)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to get the selected items in the DropDownList.
        </td>
    </tr>
    <tr>
        <td>
            {{'[getSelectedValue](http://help.syncfusion.com/js/api/ejdropdownlist#methods:getSelectedValue)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to retrieve the items value that are selected in the DropDownList.
            <br/>
        </td>
    </tr>
</table>

I> When multiSelectMode is enabled in a DropDownList and selected items having same text but its value is different means, the items can be selected. Please refer the online link

### Using value or text

To select an item initially you can pass the item’s value via Value property or SelectItemByValue API. To achieve this DropDownList control must be initiated with the associate value. 

{% tabs %}

	{% highlight CSHTML %}

    <ej-drop-down-list id="customerList" datasource="ViewBag.datasource" value="item3">
        <e-drop-down-list-fields text="Text" value="Value"/>
    </ej-drop-down-list>

	{% endhighlight %}
    
    {% highlight c# %}
        public ActionResult Index()
        {
            List<Data> DropdownData = new List<Data>();
            DropdownData.Add(new Data { Value = "item1", Text = "ListItem 1" });
            DropdownData.Add(new Data { Value = "item2", Text = "ListItem 2" });
            DropdownData.Add(new Data { Value = "item3", Text = "ListItem 3" });
            DropdownData.Add(new Data { Value = "item4", Text = "ListItem 4" });
            DropdownData.Add(new Data { Value = "item5", Text = "ListItem 5" });
            ViewBag.datasource=DropDownData;
            return View();
        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}

![](Functionalities_images/Functionalities_img1.png)

### Using indices

You can select a single or more than one item by passing index values to the properties SelectedIndex or SelectedIndices respectively. Index starts from 0 here.

{% tabs %}

	{% highlight CSHTML %}        

    <ej-drop-down-list id="customerList" datasource="ViewBag.datasource" selected-index="1">
        <e-drop-down-list-fields text="Text" value="Value"/>
    </ej-drop-down-list>

	{% endhighlight %}
    
    {% highlight c# %}
        public ActionResult Index()
        {
            List<Data> DropdownData = new List<Data>();
            DropdownData.Add(new Data { Value = "item1", Text = "ListItem 1" });
            DropdownData.Add(new Data { Value = "item2", Text = "ListItem 2" });
            DropdownData.Add(new Data { Value = "item3", Text = "ListItem 3" });
            DropdownData.Add(new Data { Value = "item4", Text = "ListItem 4" });
            DropdownData.Add(new Data { Value = "item5", Text = "ListItem 5" });
            ViewBag.datasource=DropDownData;
            return View();
        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}

![](Functionalities_images/Functionalities_img2.png)

I> To use "SelectedIndices" property, you should enable either ShowCheckbox or MultiSelectMode property First.

{% tabs %}

	{% highlight CSHTML %}

    @{ 
    List<int> index= new List<int> { 1, 2 };
    }
    <ej-drop-down-list id="customerList" datasource="ViewBag.datasource" show-checkbox="true" selected-indices="index">
    <e-drop-down-list-fields text="Text" value="Value" />
    </ej-drop-down-list>

	{% endhighlight %}
    
    {% highlight c# %}
        public ActionResult Index()
        {
            List<Data> DropdownData = new List<Data>();
            DropdownData.Add(new Data { Value = "item1", Text = "ListItem 1" });
            DropdownData.Add(new Data { Value = "item2", Text = "ListItem 2" });
            DropdownData.Add(new Data { Value = "item3", Text = "ListItem 3" });
            DropdownData.Add(new Data { Value = "item4", Text = "ListItem 4" });
            DropdownData.Add(new Data { Value = "item5", Text = "ListItem 5" });
            ViewBag.datasource=DropDownData;
            return View();
        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}

### Unselect items

Similarly, you can unselect a single or multiple items by using [unselectItemByValue](http://help.syncfusion.com/js/api/ejdropdownlist#methods:unselectitembyvalue) or [unselectItemByIndices](http://help.syncfusion.com/js/api/ejdropdownlist#methods:unselectitembyindices) or [unselectItemByText](http://help.syncfusion.com/js/api/ejdropdownlist#methods:unselectitembytext) methods. This will remove the selection state of the corresponding data item from the popup list and textbox. 

{% tabs %}

	{% highlight CSHTML %}

        @{

        List<int> selected = new List<int> { 1, 2, 3 };
        }
        <ej-drop-down-list id="dropdown" datasource="ViewBag.datasource" show-checkbox="true" selected-indices="selected">
        <e-drop-down-list-fields text="Text" value="Value" />
        </ej-drop-down-list>
        <input type="button" value="Unselect" onclick="unselect()" />

	{% endhighlight %}
    
    {% highlight js %}
    
    function unselect() {
        var obj = $('#dropdown').data("ejDropDownList");
        obj.unselectItemByValue("item2");
        obj.unselectItemsByIndices(2);
        obj.unselectItemByText("ListItem 4");
    }		

    {% endhighlight %}
    
    {% highlight c# %}
        public ActionResult Index()
        {
            List<Data> DropdownData = new List<Data>();
            DropdownData.Add(new Data { Value = "item1", Text = "ListItem 1" });
            DropdownData.Add(new Data { Value = "item2", Text = "ListItem 2" });
            DropdownData.Add(new Data { Value = "item3", Text = "ListItem 3" });
            DropdownData.Add(new Data { Value = "item4", Text = "ListItem 4" });
            DropdownData.Add(new Data { Value = "item5", Text = "ListItem 5" });
            ViewBag.datasource=DropDownData;
            return View();
        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}

## Grouping

The DropDownList items can be categorized by using a specific field in the popup list. This is enabled by using Category field on data source binding. By default grouping is disabled in DropDownList.
The below given example explains the behavior of grouping with List data binding.

{% tabs %}

	{% highlight CSHTML %}

    <ej-drop-down-list id="dropdown" datasource="ViewBag.datasource" width="150px" popup-height="300px" watermark-text="Select a vegetable">
        <e-drop-down-list-fields text="Name" category="Category" />
    </ej-drop-down-list>

	{% endhighlight %}
    
    {% highlight c# %}
        public ActionResult Index()
        {
            List<VegetableList> vegetableList = new List<VegetableList>();
            vegetableList.Add(new VegetableList { Name = "Cabbage", Category = "Leafy and Salad" }); 
            vegetableList.Add(new VegetableList { Name = "Pea", Category = "Leafy and Salad" }); 
            vegetableList.Add(new VegetableList { Name = "Spinach", Category = "Leafy and Salad" }); 
            vegetableList.Add(new VegetableList { Name = "Wheat grass", Category = "Leafy and Salad" }); 
            vegetableList.Add(new VegetableList { Name = "Yarrow", Category = "Leafy and Salad" }); 
            vegetableList.Add(new VegetableList { Name = "Chickpea", Category = "Beans" }); 
            vegetableList.Add(new VegetableList { Name = "Green bean", Category = "Beans" }); 
            vegetableList.Add(new VegetableList { Name = "Horse gram", Category = "Beans" }); 
            vegetableList.Add(new VegetableList { Name = "Peanut", Category = "Beans" });
            vegetableList.Add(new VegetableList { Name = "Pigeon pea", Category = "Beans" }); 
            vegetableList.Add(new VegetableList { Name = "Garlic", Category = "Bulb and Stem" }); 
            vegetableList.Add(new VegetableList { Name = "Garlic Chives", Category = "Bulb and Stem" }); 
            vegetableList.Add(new VegetableList { Name = "Lotus root", Category = "Bulb and Stem" }); 
            vegetableList.Add(new VegetableList { Name = "Nopal", Category = "Bulb and Stem" });
            vegetableList.Add(new VegetableList { Name = "Onion", Category = "Bulb and Stem" }); 
            vegetableList.Add(new VegetableList { Name = "Shallot", Category = "Bulb and Stem" }); 
            vegetableList.Add(new VegetableList { Name = "Beetroot", Category = "Root and Tuberous" }); 
            vegetableList.Add(new VegetableList { Name = "Carrot", Category = "Root and Tuberous" }); 
            vegetableList.Add(new VegetableList { Name = "Ginger", Category = "Root and Tuberous" }); 
            vegetableList.Add(new VegetableList { Name = "Potato", Category = "Root and Tuberous" }); 
            vegetableList.Add(new VegetableList { Name = "Radish", Category = "Root and Tuberous"}); 
            vegetableList.Add(new VegetableList { Name = "Turmeric", Category = "Root and Tuberous" });
            ViewBag.datasource = vegetableList;
            return View();
        }
        public class VegetableList
        {
            public string Name { get; set; }
            public string Category { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}

![](Functionalities_images/Functionalities_img3.png)

N> Grouping has restrictions in the following scenarios, <BR>

1.  It is not supported on using HTML "select" element with predefined set of options<BR>
2.  When using UL-LI elements you need to use “e-category” class in LI element to specify it as the grouping header. The following code will explain this behavior,<BR>
3.  The sorting behavior varies when grouping is enabled in the DropDownList, based on browser as we have used browser based stable sorting method when there is multiple level of sorting. <BR>
4.  To overcome this behavior on sorting order with browser, we suggest you to set ej.support.stableSort as false from the script when the page is loaded or in document ready function.<BR>
   
   {% highlight javascript %}
    <script type="text/javascript">
            $(document).ready(function () {
                ej.support.stableSort = false;            
            });
    </script>
   {% endhighlight %}

{% highlight CSHTML %}

    <ej-drop-down-list id="dropdown" target-id="groupinglist" width="150px" popup-height="300px" watermark-text="Select an item">
    </ej-drop-down-list>

    <div id="groupinglist">
        <ul>
            <span class="e-category">Header 1</span>
            <li>Item 1</li>
            <li>Item 2</li>
            <span class="e-category">Header 2</span>
            <li>Item 3</li>
            <li>Item 4</li>
            <li>Item 5</li>
        </ul>
    </div>

{% endhighlight %}

![](Functionalities_images/Functionalities_img4.png)

I> Virtual scrolling is not supported with Grouping.

## Sorting

Sorting is enabled in order to display the items alphabetically in either ascending or descending order. By default the items is displayed in the initialized order, use EnableSorting property to automatically sort strings based on text field value. You can assign either SortOrder.Ascending or SortOrder.Descending enum values to the SortOrder property to sort out the list items. By default ascending order is followed when SortOrder property is not specified. 

{% tabs %}

	{% highlight CSHTML %}

    <ej-drop-down-list id="dropdown" datasource="ViewBag.datasource" enable-sorting="true" sort-order="@SortOrder.Descending">
        <e-drop-down-list-fields text="Text" value="Value" />
    </ej-drop-down-list>

	{% endhighlight %}
    
    {% highlight c# %}
        public ActionResult Index()
        {
            List<Data> DropDownData = new List<Data>();
            DropDownData.Add(new Data { Value = "item1", Text = "List Item 1" });
            DropDownData.Add(new Data { Value = "item5", Text = "List Item 5" });
            DropDownData.Add(new Data { Value = "item4", Text = "List Item 4" });
            DropDownData.Add(new Data { Value = "item2", Text = "List Item 2" });
            DropDownData.Add(new Data { Value = "item3", Text = "List Item 3" });
            ViewBag.datasource=DropDownData;
            return View();
        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}

I> Virtual scrolling is not supported with Sorting.

## Cascading

This works for series of DropDownList in which items are filtered based on the previous DropDownList‘s selection. Cascading is performed based on the value field and this field should be bounded with a foreign key. To perform cascading, specify the child DropDownList’s id in CascadeTo property and use delimiter (“,”) to specify more than one child DropDownList.

Configuring the data items for cascading to the series of DropDownList is demonstrated below

{% tabs %}

	{% highlight CSHTML %}
        
        <div style="width: 400px;">
            <ej-drop-down-list id="GroupDropDown" datasource="ViewBag.Groups" cascade-to="CountryDropDown">
                <e-drop-down-list-fields text="Text" value="ParentId"  />
            </ej-drop-down-list>

            <ej-drop-down-list id="CountryDropDown" datasource="ViewBag.CountriesData" enabled="false">
                <e-drop-down-list-fields text="Text" />
            </ej-drop-down-list>
       </div>
       
	{% endhighlight %}

    {% highlight c# %}
        public ActionResult Index()
        {
            List<Groups> GroupList = new List<Groups>();
            GroupList.Add(new Groups{ ParentId = "a", Text = "Group A" }); 
            GroupList.Add(new Groups{ ParentId = "b", Text = "Group B" }); 
            GroupList.Add(new Groups{ ParentId = "c", Text = "Group C" }); 
            GroupList.Add(new Groups{ ParentId = "d", Text = "Group D" }); 
            GroupList.Add(new Groups { ParentId = "e", Text = "Group E" });
            List<Country> CountryList = new List<Country>();
            CountryList.Add(new Country{ ParentId = "a", Text = "Algeria" }); 
            CountryList.Add(new Country{ ParentId = "a", Text = "Armenia" }); 
            CountryList.Add(new Country{ ParentId = "a", Text = "Bangladesh" }); 
            CountryList.Add(new Country{ ParentId = "a", Text = "Cuba" }); 
            CountryList.Add(new Country{ ParentId = "b", Text = "Denmark" }); 
            CountryList.Add(new Country{ ParentId = "b", Text = "Egypt" }); 
            CountryList.Add(new Country{ ParentId = "c", Text = "Finland" }); 
            CountryList.Add(new Country{ ParentId = "c", Text = "India" }); 
            CountryList.Add(new Country{ ParentId = "c", Text = "Malaysia" }); 
            CountryList.Add(new Country{ ParentId = "d", Text = "New Zealand" }); 
            CountryList.Add(new Country{ ParentId = "d", Text = "Norway" }); 
            CountryList.Add(new Country{ ParentId = "d", Text = "Poland" }); 
            CountryList.Add(new Country{ ParentId = "e", Text = "Romania" }); 
            CountryList.Add(new Country{ ParentId = "e", Text = "Singapore" }); 
            CountryList.Add(new Country{ ParentId = "e", Text = "Thailand" }); 
            CountryList.Add(new Country{ ParentId = "e", Text = "Ukraine" });
            ViewBag.Groups = GroupList;
            ViewBag.CountriesData = CountryList;
            return View();
        }
        public class Groups
        {
            public string ParentId { get; set; }
            public string Text { get; set; }
        }
        public class Country
        {
            public string ParentId { get; set; }
            public string Text { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}

![](Functionalities_images/Functionalities_img5.png)

![](Functionalities_images/Functionalities_img6.jpeg)

### Binding the data source to the cascading DropDownList using cascade event

Bind the data source to the cascading DropDownList dynamically using ClientSideEvent Cascade as demonstrated below,

{% tabs %}

	{% highlight CSHTML %}
      
        <div style="width: 530px;">
           <div style="float: left;">
               <span>Select Group</span>
                <ej-drop-down-list id="GroupDropDown" datasource="ViewBag.Groups" cascade-to="CountryDropDown,PlayersDropDown">
                    <e-drop-down-list-fields text="Text" value="ParentId"  />
                </ej-drop-down-list>
           </div>

           <div style="float: left; padding-left: 50px;">
               <span>Select Country</span>
                <ej-drop-down-list id="CountryDropDown" datasource="ViewBag.CountriesData" enabled="false">
                    <e-drop-down-list-fields text="Text" />
                </ej-drop-down-list>
           </div>

           <div style="float: right;">
               <span>Select Players</span>
                <ej-drop-down-list id="PlayersDropDown" datasource="ViewBag.PlayersData" enabled="false">
                    <e-drop-down-list-fields text="Text" />
                </ej-drop-down-list>
           </div>
       </div>
       
	{% endhighlight %}

    {% highlight c# %}
        public ActionResult Index()
        {
            List<Groups> GroupList = new List<Groups>();
            GroupList.Add(new Groups{ ParentId = "a", Text = "Group A" }); 
            GroupList.Add(new Groups{ ParentId = "b", Text = "Group B" });
            List<Country> CountryList = new List<Country>();
            CountryList.Add(new Country{ ParentId = "a", Text = "Algeria" }); 
            CountryList.Add(new Country{ ParentId = "a", Text = "Armenia" }); 
            CountryList.Add(new Country{ ParentId = "b", Text = "Denmark" }); 
            CountryList.Add(new Country{ ParentId = "b", Text = "Egypt" }); 
            List<Players> PlayerList = new List<Players>();
            PlayerList.Add(new Players { ParentId = "a", Text = "Adams" });
            PlayerList.Add(new Players { ParentId = "a", Text = "Clarke" });
            PlayerList.Add(new Players { ParentId = "b", Text = "Brett" });
            PlayerList.Add(new Players { ParentId = "b", Text = "James" });
            ViewBag.Groups = GroupList;
            ViewBag.CountriesData = CountryList;
            ViewBag.PlayersData = PlayerList;
            return View();
        }
        public class Groups
        {
            public string ParentId { get; set; }
            public string Text { get; set; }
        }
        public class Country
        {
            public string ParentId { get; set; }
            public string Text { get; set; }
        }
        public class Players
        {
            public string ParentId { get; set; }
            public string Text { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}

![](Functionalities_images/Functionalities_img7.jpeg)

### Multi-Level Cascading

The below scenario can be explained with three DropDownList for the multi-level cascading.

{% tabs %}

	{% highlight C# %}
    
    public partial class DropdownController: Controller
    {
        List<groups> group = new List<groups>();
        List<Countries> country = new List<Countries>();
        List<Capital> capital = new List<Capital>();
        public ActionResult DropdownFeatures()
        {
            group.Add(new groups { parentId = "a", text = "Group A" });
            group.Add(new groups { parentId = "b", text = "Group B" });
            group.Add(new groups { parentId = "c", text = "Group C" });
            group.Add(new groups { parentId = "d", text = "Group D" });
            group.Add(new groups { parentId = "e", text = "Group E" });
            ViewBag.datasource = group;
            country.Add(new Countries { value = 11, parentId = "a", text = "Algeria" });
            country.Add(new Countries { value = 12, parentId = "a", text = "Armenia" });
            country.Add(new Countries { value = 13, parentId = "a", text = "Bangladesh" });
            country.Add(new Countries { value = 14, parentId = "a", text = "Cuba" });
            country.Add(new Countries { value = 15, parentId = "b", text = "Denmark" });
            country.Add(new Countries { value = 16, parentId = "b", text = "Egypt"});
            country.Add(new Countries { value = 17, parentId = "c", text = "Finland"});
            country.Add(new Countries { value = 18, parentId = "c", text = "India" });
            country.Add(new Countries { value = 19, parentId = "c", text = "Malaysia"});
            country.Add(new Countries { value = 20, parentId = "d", text = "New Zealand"});
            country.Add(new Countries { value = 21, parentId = "d", text = "Norway" });
            country.Add(new Countries { value = 22, parentId = "d", text = "Romania" });
            country.Add(new Countries { value = 23, parentId = "e", text = "Singapore"});
            country.Add(new Countries { value = 24, parentId = "e", text = "Thailand" });
            country.Add(new Countries { value = 25, parentId = "e", text = "Ukraine"});
            ViewBag.datasource1 = country;
            capital.Add(new Capital { value = 11, text = "Algiers" });
            capital.Add(new Capital { value = 12, text = "Cairo" });
            capital.Add(new Capital { value = 13, text = "Copenhagen" });
            capital.Add(new Capital { value = 14, text = "Washington" });
            capital.Add(new Capital { value = 15, text = "Denmark" });
            capital.Add(new Capital { value = 16, text = "Yerevan" });
            capital.Add(new Capital { value = 17, text = "Copenhagen" });
            capital.Add(new Capital { value = 18, text = "New Delhi" });
            capital.Add(new Capital { value = 19, text = "Havana" });
            capital.Add(new Capital { value = 20, text = "Brasilia" });
            capital.Add(new Capital { value = 21, text = "Lima" });
            capital.Add(new Capital { value = 22, text = "Canberra" });
            capital.Add(new Capital { value = 23, text = "Wellington" });
            capital.Add(new Capital { value = 24, text = "Alfred Faure" });
            capital.Add(new Capital { value = 25, text = "King Edward Point" });
            ViewBag.capital = capital;
              return View();
         } 
    }
    public class groups
    {
        public string text { get; set; }
        public string parentId { get; set; }
      
    }
    public class Countries
    {
        public string text { get; set; }
       
        public int value { get; set; }
        public string parentId { get; set; }
        
    }
    public class Capital
    {
        public string text { get; set; }
        public int value { get; set; }
    }
    {% endhighlight %}
    
    {% highlight CSHTML %}
    
    <div class="control" style="float: left;">
        <span class="txt">Select Group</span>
        <ej-drop-down-list id="groupsList" datasource="ViewBag.groupData" cascade-to="countryList">
            <e-drop-down-list-fields text="text" value="parentId"  />
        </ej-drop-down-list>
    </div>
    <div class="control" style="float: left;">
        <span class="txt">Select Country</span>
        <ej-drop-down-list id="countryList" datasource="ViewBag.countryData" cascade-to="capitalList" enabled="false">
            <e-drop-down-list-fields text="text" value="value"/>
        </ej-drop-down-list>
    </div>
    <div class="control" style="float: left;">
        <span class="txt">Select Country</span>
        <ej-drop-down-list id="capitalList" datasource="ViewBag.capitalData" enabled="false">
            <e-drop-down-list-fields text="text" />
        </ej-drop-down-list>    
    </div>

     {% endhighlight %}
    
{% endtabs %}

First two DropDownList cascaded based on the parentId, and then from second to third, cascading performed based on the value field.

