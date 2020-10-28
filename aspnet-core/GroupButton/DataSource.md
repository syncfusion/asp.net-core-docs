---
layout: post
title: DataSource Support
description: datasource
platform: aspnet-core
control: GroupButton
documentation: ug
---

# DataSource

GroupButton can populate the button items based on data source and by specifying the associated fields. 

Refer the below table to know about the available fields

<table>
<tr>
<td>
text<br/><br/></td><td>
Text to be displayed in button<br/><br/></td></tr>
<tr>
<td>
prefix-icon<br/><br/></td><td>
Icon class name – prefixIcon will be displayed from the left margin of the button.<br/><br/></td></tr>
<tr>
<td>
suffix-icon<br/><br/></td><td>
Icon class name – suffixIcon will be displayed from the left margin of the button.<br/><br/></td></tr>
<tr>
<td>
content-type<br/><br/></td><td>
Specifies content type of button item<br/><br/></td></tr>
<tr>
<td>
image-position<br/><br/></td><td>
Specifies position of the image in a button item<br/><br/></td></tr>
<tr>
<td>
selected<br/><br/></td><td>
Specifies the selection state of button item<br/><br/></td></tr>
<tr>
<td>
url<br/><br/></td><td>
Used to include the URL tag to the button item<br/><br/></td></tr>
<tr>
<td>
html-attribute<br/><br/></td><td>
It defines the HTML attributes such as class and styles for an button item.<br/><br/></td></tr>
<tr>
<td>
link-attribute<br/><br/></td><td>
It defines the image attributes such as height, width, styles, etc.<br/><br/></td></tr>
</table>


## Local Data

To set the local JSON data, define a JSON array and initialize the GroupButton with **dataSource** property. Specify the column names in the fields’ property.

N> the columns are bounded automatically when the fields are specified with the default names like id, text, etc...

Below is the sample to code to render the GroupButton JSON dataSource,

{% highlight CSHTML %}

/*ej-Tag Helper code to render GroupButton*/

<ej-group-button id="GroupButton" width="100%" group-button-mode="@GroupButtonMode.RadioButton" show-rounded-corner="true" datasource="ViewBag.datasource">
    <e-group-button-fields id="BtnID" text="Text" content-type="ContentType" selected="Selected" />    
</ej-group-button>

{% endhighlight %}

{% highlight CSHTML%}

/*Razor code to render GroupButton*/

     @{Html.EJ().GroupButton("GroupButton").Width("100%").GroupButtonMode(GroupButtonMode.RadioButton).ShowRoundedCorner(true).Datasource((IEnumerable<Groupbutton_core.ButtonController.Groupbutton>)ViewBag.Model).GroupButtonFields(e => e.Text("text").Selected("Selected")).Render(); }


{% endhighlight %}

N> To render the GroupButton Control you can use either Razor or Tag helper code as given in the above code snippet.


{% highlight c# %}
   
	// Add the following code to add list items in the controller page
	public class Btn
        {
            public string Text { get; set; }
            public string ContentType { get; set; }
            public string BtnID { get; set; }
            public string Selected { get; set; }
        }
        List<Btn> file = new List<Btn>();
        public IActionResult Index()
        {
            file.Add(new Btn { BtnID = "btn1", Text = "Day" });
            file.Add(new Btn { BtnID = "btn2", Text = "Week" });
            file.Add(new Btn { BtnID = "btn3", Text = "Work Week" });
            file.Add(new Btn { BtnID = "btn4", Text = "Month", Selected="selected" });
            file.Add(new Btn { BtnID = "btn5", Text = "Agenda" });
            ViewBag.datasource = file;
            return View();
        }

{% endhighlight %}


![](DataSource_images/DataSoruce_img1.jpg)


## Remote Data

To bind remote data to the GroupButton, you can assign a service data as an instance of `ejDataManager` to the `dataSource` property along with the fields mapping.


{% highlight CSHTML %}

<ej-group-button id="groupButton" query="ej.Query().from('Orders').take(6)" width="100%">
    <e-datamanager url="//mvc.syncfusion.com/Services/Northwnd.svc/" offline="false"></e-datamanager>
    <e-group-button-fields text="CustomerID" />
</ej-group-button>

{% endhighlight %}
