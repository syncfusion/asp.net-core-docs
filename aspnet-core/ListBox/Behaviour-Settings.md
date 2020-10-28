---
layout: post
title: Behaviour Settings | ListBox | ASP.NET Core | Syncfusion
description: behaviour settings
platform:  aspnet-core
control: ListBox
documentation: ug
---

# Behavior Settings

The following are some miscellaneous properties that helps you to change the behavior of ListBox control.

## Target ID

You can append a list with ListBox by using target-id property. Define a <ul>,< li> tag that you want to display on ListBox and then set the id of parent <ul> tag to target-id property. And its data type is string. 

The following steps explains you the configuration of target-id property in ListBox.

1. Add the below code in your page to render the ListBox 


  {% highlight CSHTML %}

	// Add the following code in View page to configure ListBox widget

	<div id="control">

<h5 class="ctrllabel">

    Select a font style

</h5>

<ej-list-box id="list1" height="220px" target-id="targetlist"></ej-list-box>
<ul id="targetlist">

    <li>Algerian</li>

    <li>ARIAL</li>

    <li>Bimini</li>

    <li>Courier</li>

    <li>Cursive</li>

    <li>Fantasy</li>

    <li>Georgia</li>

    <li>Impact</li>

    <li>New york</li>

    <li>Sans-Serif</li>

    <li>Scripts</li>

    <li>Times</li>

    <li>Times New Roman</li>

    <li>Verdana</li>

    <li>Western</li>

    <li>Zapfellipt bt</li>

</ul>
</div>

{% endhighlight %}
   




2. Output of the above steps.



![](Behaviour-Settings_images/Behaviour-Settings_img1.png)



## Select the value by index 

ListBox widget provides you support to select an item by mentioning the index of the item. The selected-index property helps you to select the particular item from the list. Its date type is number. 

The following steps explains you the configuration of selected-index= property in ListBox.

1. Add the below code in your page to render the ListBox


{% highlight CSHTML %}

 <div id="control">

     <h5 class="ctrllabel">

         Select a font style

     </h5>
    <ej-list-box id="listboxsample" datasource="ViewBag.datasource" selected-index="2">
        <e-list-box-fields id="empid" text="text"/>
     </ej-list-box> 
</div>
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

2.  Output of the above steps.


![](Behaviour-Settings_images/Behaviour-Settings_img2.png)



## Enable or Disable the ListBox Widget

This features enables you to set the enable or disable options for ListBox by setting Boolean type value to enabled property. 

The following steps explains you the configuration of enabled property in ListBox.

1. Add the below code in your view page to render the disabled ListBox



  {% highlight CSHTML %}

	// Add the following code in View page to configure ListBox widget
<div id="control">

     <h5 class="ctrllabel">

         Select a skill
        <ej-list-box id="listboxsample" datasource="ViewBag.datasource" enabled="false">
             <e-list-box-fields id="empid" text="text"/>
        </ej-list-box>  
</div>		
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



2. Output of the above steps.


![](Behaviour-Settings_images/Behaviour-Settings_img3.png)



