---
layout: post
title: Appearance and Styling | ListBox | ASP.NET Core | Syncfusion
description: appearance and styling
platform: aspnet-core
control: ListBox
documentation: ug
---

# Appearance and Styling

## Adjusting ListBox size

### Width

ListBox widget provides you support to customize the dimensions of the ListBox. By using width property you can set the width of the ListBox. Its data type is string.

### Height

ListBox widget provides you support to customize the dimensions of the ListBox. By using height property, you can set the height of the ListBox. Its data type is string.

Defining the ListBox size properties

The following steps explains you the configuration of Height & Width properties in ListBox.

1. Add the below code in your view page to render the ListBox with customized height and width

   {% highlight CSHTML %}
   
	// Add the following code in View page to configure ListBox widget

<ej-list-box id="listboxsample" datasource="ViewBag.datasource" height="240" width="302">
    <e-list-box-fields id="empid" text="text"/>
</ej-list-box>  

{% endhighlight %}
   
   
  {% highlight C# %}
		
	// Add the following code to add list items in the controller page  
	 public class skillset
        {
            public string text { get; set; }
        }
        public ActionResult Draganddrop()
        {
            List<skillset> skill = new List<skillset>();
            skill.Add(new skillset { text = "ASP.NET" });
            skill.Add(new skillset { text = "ActionScript" });
            skill.Add(new skillset { text = "Basic" });
            skill.Add(new skillset { text = "C++" });
            skill.Add(new skillset { text = "C#" });
            skill.Add(new skillset { text = "dBase" });
            skill.Add(new skillset { text = "Delphi" });
            skill.Add(new skillset { text = "ESPOL" });
            skill.Add(new skillset { text = "F#" });
            skill.Add(new skillset { text = "FoxPro" });
            skill.Add(new skillset { text = "Java" });
            skill.Add(new skillset { text = "J#" });
            skill.Add(new skillset { text = "Lisp" });
            skill.Add(new skillset { text = "Logo" });
            skill.Add(new skillset { text = "PHP" });
            ViewBag.datasource = skill;
            return View();
        }

{% endhighlight %}


2. Output of the above steps


![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)



### Enabling Rounded corner

ListBox widget provides you support to change the appearance of ListBox. By using show-rounded-corner you can create a rounded corner on the ListBox. Its data type is Boolean.

The following steps explains you the configuration of Rounded corner of the ListBox.

1. Add the below code in your view page to render the ListBox with rounded corners


 {% highlight CSHTML %}
   
	// Add the following code in View page to configure ListBox widget
    
<ej-list-box id="listboxsample" datasource="ViewBag.datasource" show-rounded-corner="true">
    <e-list-box-fields id="empid" text="text"/>
</ej-list-box>  

		
{% endhighlight %}
   
		
  {% highlight C# %}
		
	// Add the following code to add list items in the controller page  
	 public class skillset
        {
            public string text { get; set; }
        }
        public ActionResult Draganddrop()
        {
            List<skillset> skill = new List<skillset>();
            skill.Add(new skillset { text = "ASP.NET" });
            skill.Add(new skillset { text = "ActionScript" });
            skill.Add(new skillset { text = "Basic" });
            skill.Add(new skillset { text = "C++" });
            skill.Add(new skillset { text = "C#" });
            skill.Add(new skillset { text = "dBase" });
            skill.Add(new skillset { text = "Delphi" });
            skill.Add(new skillset { text = "ESPOL" });
            skill.Add(new skillset { text = "F#" });
            skill.Add(new skillset { text = "FoxPro" });
            skill.Add(new skillset { text = "Java" });
            skill.Add(new skillset { text = "J#" });
            skill.Add(new skillset { text = "Lisp" });
            skill.Add(new skillset { text = "Logo" });
            skill.Add(new skillset { text = "PHP" });
            ViewBag.datasource = skill;
            return View();
        }

{% endhighlight %}



2. Output of the above steps.


![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)



