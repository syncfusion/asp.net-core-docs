---
layout: post
title: Template support with DropDownList control for Syncfusion ASP.NET Core
description: Template Support with DropDownList control for Syncfusion ASP.NET Core
platform: aspnet-core
control: DropDownList
documentation: ug
keywords: Template Support, DropDownList, dropdown, Header Template

---

# Template Support

By default you can add any text or image to the DropDownList list item. To customize the items layout or to create your own visualized elements you can use this template support.

## Header Template

You can create the popup header by using HeaderTemplate property. You can add any HTML content in header template.

## Template Field

Create a set of div containers with common syntax or elements and assign it to the Template property. You can add any HTML mark-up element inside the DropDownList list using this property.

In the demo, a List data is created with Text, Image, Role and Country which is initialized with DataSource property. Content template is created by using the corresponding fields and assigned in template property. The content template is customized with images and custom CSS styles to visualize the items in popup.

{% tabs %}

	{% highlight CSHTML %}
     
   <ej-drop-down-list id="groupsList" datasource="ViewBag.datasource" width="250px" header-template="<div class='eheader'><span>PHOTO</span> <span>DETAILS</span></div>" template="<div><img class='imgId' src='../Content/Employees/${Image}.png' alt='employee'/> <div class='ename'> ${Text} </div><div class='role'> ${Role} </div><div class='cont'> ${Country} </div></div>">
   </ej-drop-down-list>

	{% endhighlight %}
    
    {% highlight css %}

    .imgId {
        margin: 0;
        padding: 3px 10px 3px 3px;
        border: 0 none;
        width: 60px;
        height: 60px;
        float: left;
    }
    
    .eheader {
        font-weight: bold;
        border-bottom: 1px solid #c8c8c8;
        background: #c8c8c8;
    }
    
    .eheader > span {
        display: inline-block;
        padding: 10px;
    }
    
    .ename {
        font-weight: bold;
        padding: 6px 3px 1px 3px;
    }
    
    .role, .cont {
        font-size: smaller;
        padding: 3px 3px -1px 0px;
    }    

    {% endhighlight %}
    
    {% highlight c# %}
        public ActionResult Index()
        {
           List<Employee> EmpData = new List<Employee>();
            EmpData.Add(new Employee
            {
                Text = "Erik Linden",
                Role = "Representative",
                Country = "England",
                Image = "3",
                ImgAttr = "class='imgId'"
            });
            EmpData.Add(new Employee
            {
                Text = "John Linden",
                Role = "Representative",
                Country = "Norway",
                Image = "6",
                ImgAttr = "class='imgId'"
            });
            EmpData.Add(new Employee
            {
                Text = "Louis",
                Role = "Representative",
                Country = "Australia",
                Image = "7",
                ImgAttr = "class='imgId'"
            });
            EmpData.Add(new Employee
            {
                Text = "Lawrence",
                Role = "Representative",
                Country = "India",
                Image = "8",
                ImgAttr = "class='imgId'"
            });
            ViewBag.datasource = EmpData;
            return View();
        }
        public class Employee
        {
            public string Text { get; set; }
            public string Role { get; set; }
            public string Country { get; set; }
            public string Image { get; set; }
            public string ImgAttr { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}

N> Images for this sample are available in (installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\samples\web\themes\images<br/>

![](TemplateSupport_images/TemplateSupport_img1.jpeg)