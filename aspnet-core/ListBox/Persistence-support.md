---
layout: post
title: Persistence support | ListBox | ASP.NET Core | Syncfusion
description: persistence support 
platform: aspnet-core
control: ListBox
documentation: ug
---

# Persistence support 

This features enables you to save current model value to browser cookies for state maintains. When you refresh the ListBox control page, it retains the model value apply from browser cookies. The date type of enable-persistence is Boolean type. 

The following steps explains you the configuration of enable-persistence property in ListBox.

1. Add the below code in your view page to render the ListBox


 {% highlight CSHTML %}

	// Add the following code in View page to configure ListBox widget

<ej-list-box id="listboxsample" datasource="ViewBag.datasource" enable-persistence="true">
    <e-list-box-fields id="empid" text="text"/>
</ej-list-box>  
 

{% endhighlight %}
   
   
{% highlight C# %}

	// Add the following code to add list items in the controller page



	     public class skillset
        {
            public string text { get; set; }
        }
        public ActionResult Localdata()
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
   
   

   

