---
layout: post
title: Getting-Started of Menu control
description: How to create a Menu and its other functionalitie
platform: aspnet-core
control: Menu
documentation: ug
keywords: ejMenu, Menu, Menu widget, js Menu
---

# Getting Started 

## Create Syncfusion Menu in ASP.NET Core

Menu supports you to display a Menu of list-out items. This Menu is based on UL-LI hierarchy, where the sub-list items can be rendered as the sub-menu items. Its possible to render the Menu control with local and remote data source. 

From the following guideline, you can learn how to customize the Menu control for a website. 
 
## Create your first Menu in ASP.NET Core

Create Syncfusion ASP.NET Core application. You can refer [ASP.NET Core Getting Started](https://help.syncfusion.com/aspnet-core/getting-started) documentation to initially configure the common specifications.

{% highlight CSHTML %}

    /*ej-Tag Helper code to render Menu*/

    <ej-menu id="syncfusionProducts"> </ej-menu>

{% endhighlight %}

{% highlight Razor %}

    /*Razor code to render Menu*/

    @{ Html.EJ().Menu("SyncfusionProducts").Render(); }

{% endhighlight %}
    
N> To render the Menu Control you can use either Razor or Tag helper code as given in the above code snippet 

## Configure Parent Menu items

Each Menu consists of a list of Menu items with list of sub level Menu item. Refer the following guidelines to initialize the root level elements of Menu control with Remote data source value. RootLevelItems data service is created to define the root level Menu items, sub items and InnerItems data services to initialize the sub level and inner sub levels and both can be referred from the following service location. In Menu Widgets mention the RootLevelItem Data Source in the Datasource property. Elements’s properties like Id, Text, URL, and Parent Id can be defined using our menu fields and it explained briefly under the concept and features of Menu control.

To navigate the clicked Menu item to a specific URL, define the navigation URL to each Menu item.

Initialize the Menu element using datasource as follows. 

{% highlight CSHTML %}

    /*ej-Tag Helper code to render Menu*/
     <ej-Menu id="SyncfusionProducts">
         <e-menu-fields dataSource="ViewBag.datasource" id="pid" text="mtext" parent-id="parent"></e-menu-fields>
    </ej-Menu>
{% endhighlight %}

{% highlight Razor %}

    /*Razor code to render Menu*/

    @{Html.EJ().Menu("SyncfusionProducts").MenuFields(f => f.Datasource((IEnumerable<MenuJson>)ViewBag.datasource).Id("pid").Text("mtext").ParentId("parent")).Render();}

{% endhighlight %}

{% highlight C# %}

           
        public ActionResult Index()
        {
            List<MenuJson> menuitem = new List<MenuJson>();
            menuitem.Add(new MenuJson { pid = 1, mtext = "Product", parent = null });
            menuitem.Add(new MenuJson { pid = 2, mtext = "Support", parent = null });
            menuitem.Add(new MenuJson { pid = 3, mtext = "Purchase", parent = null });
            menuitem.Add(new MenuJson { pid = 4, mtext = "Downloads", parent = null });
            menuitem.Add(new MenuJson { pid = 5, mtext = "Resources", parent = null });
            menuitem.Add(new MenuJson { pid = 6, mtext = "Company", parent = null });
            ViewBag.datasource = menuitem;
            return View();
        }
         
         public class MenuJson
       {
        public string mtext { get; set; }
        public int pid { get; set; }
        public string parent { get; set; }
      }

{% endhighlight %}

The following screenshot displays the resultant output Menu without sub menu item.

![](Getting-Started_images/Getting-Started_img3.png) 

## Initialize sub-level Menu items

Each Menu items consist of list of sub level Menu items. Refer the following guidelines to initialize the sub level items of Menu control. The ParentId field property maps root level Menu item to its sub level Menu item. In Menu Widgets mention the RootLevelItems and SubLevelItems Data Source in the Datasource property. The Child field property is used to define sub level Menu items of parent Menu item.							

The following code example explains the initialization of first level sub menu items of Menu control.

{% highlight CSHTML %}

    /*ej-Tag Helper code to render Menu*/

     <ej-Menu id="SyncfusionProducts">
         <e-menu-fields dataSource="ViewBag.datasource" id="pid" text="mtext" parent-id="parent"></e-menu-fields>
    </ej-Menu>

{% endhighlight %}

{% highlight Razor %}

    /*Razor code to render Menu*/

    @{Html.EJ().Menu("SyncfusionProducts").MenuFields(f => f.Datasource((IEnumerable<MenuJson>)ViewBag.datasource).Id("pid").Text("mtext").ParentId("parent")).Render();}

{% endhighlight %}

{% highlight C# %}

           
       List<MenuJson> menuitem = new List<MenuJson>();
           menuitem.Add(new MenuJson { pid = 1, mtext = "Product", parent = null });
            menuitem.Add(new MenuJson { pid = 2, mtext = "Support", parent = null });
            menuitem.Add(new MenuJson { pid = 3, mtext = "Purchase", parent = null });
            menuitem.Add(new MenuJson { pid = 4, mtext = "Downloads", parent = null });
            menuitem.Add(new MenuJson { pid = 5, mtext = "Resources", parent = null });
            menuitem.Add(new MenuJson { pid = 6, mtext = "Company", parent = null });
            menuitem.Add(new MenuJson { pid = 11, parent = "1", mtext = "ASP.NET" });
            menuitem.Add(new MenuJson { pid = 12, parent = "1", mtext = "ASP.NET MVC" });
            menuitem.Add(new MenuJson { pid = 13, parent = "1", mtext = "Mobile MVC" });
            menuitem.Add(new MenuJson { pid = 14, parent = "1", mtext = "Silverlight" });
            menuitem.Add(new MenuJson { pid = 15, parent = "1", mtext = "Windows Forms" });
            menuitem.Add(new MenuJson { pid = 16, parent = "1", mtext = "Windows Phone" });
            menuitem.Add(new MenuJson { pid = 17, parent = "1", mtext = "WinRT(XMAL)" });
            menuitem.Add(new MenuJson { pid = 18, parent = "1", mtext = "WPF" });
            menuitem.Add(new MenuJson { pid = 19, parent = "1", mtext = "Orubase Studio" });
            menuitem.Add(new MenuJson { pid = 20, parent = "1", mtext = "Metro Studio" });
            menuitem.Add(new MenuJson { pid = 21, parent = "1", mtext = "What's NEw" });
            menuitem.Add(new MenuJson { pid = 27, parent = "2", mtext = "Direct-Trac Support" });
            menuitem.Add(new MenuJson { pid = 28, parent = "2", mtext = "Community Foruma" });
            menuitem.Add(new MenuJson { pid = 29, parent = "2", mtext = "Knowledge Base" });
            menuitem.Add(new MenuJson { pid = 30, parent = "2", mtext = "Online Documentation" });
            menuitem.Add(new MenuJson { pid = 31, parent = "2", mtext = "Services" });
            menuitem.Add(new MenuJson { pid = 34, parent = "4", mtext = "Evaluation" });
            menuitem.Add(new MenuJson { pid = 35, parent = "4", mtext = "Free E-books" });
            menuitem.Add(new MenuJson { pid = 36, parent = "4", mtext = "Metro Studio" });
            menuitem.Add(new MenuJson { pid = 37, parent = "4", mtext = "C" });
            menuitem.Add(new MenuJson { pid = 38, parent = "4", mtext = "Version History" });
            menuitem.Add(new MenuJson { pid = 39, parent = "5", mtext = "E-Books" });
            menuitem.Add(new MenuJson { pid = 40, parent = "5", mtext = "White Papers" });
            menuitem.Add(new MenuJson { pid = 41, parent = "6", mtext = "More About US" });
            menuitem.Add(new MenuJson { pid = 42, parent = "6", mtext = "Management" });
            menuitem.Add(new MenuJson { pid = 43, parent = "6", mtext = "News & Events" });
            menuitem.Add(new MenuJson { pid = 44, parent = "6", mtext = "Customer Quotes" });
            menuitem.Add(new MenuJson { pid = 45, parent = "6", mtext = "Customer Lists" });
            ViewBag.datasource = menuitem;
            return View();
        }
         
         public class MenuJson
       {
        public string mtext { get; set; }
        public int pid { get; set; }
        public string parent { get; set; }
      }

{% endhighlight %}



Execute the above code example to render the following output Menu with sub menu item.

![](Getting-Started_images/Getting-Started_img4.png)

## Define multiple level Menu items

Render sub menu item to multiple level in Menu control. In Menu Widgets, mention the InnerItems Data Source in the Datasource property. The Child field property is used to define the sub level Menu item of parent Menu. Specify the ParentId value to render sub level Menu item for the Menu item. Each Level Menu item have Child field to define the child level Menu item. 

The following code example explains the initialization of multiple level sub menu items.

{% highlight CSHTML %}

    /*ej-Tag Helper code to render Menu*/

    <ej-Menu id="SyncfusionProducts">
         <e-menu-fields dataSource="ViewBag.datasource" id="pid" text="mtext" parent-id="parent"></e-menu-fields>
    </ej-Menu>

{% endhighlight %}

{% highlight Razor %}

    /*Razor code to render Menu*/

     @{Html.EJ().Menu("SyncfusionProducts").MenuFields(f => f.Datasource((IEnumerable<MenuJson>)ViewBag.datasource).Id("pid").Text("mtext").ParentId("parent")).Render();}

{% endhighlight %}

{% highlight C# %}

           
        public ActionResult Index()
        {
            List<MenuJson> menuitem = new List<MenuJson>();
           menuitem.Add(new MenuJson { pid = 1, mtext = "Product", parent = null });
            menuitem.Add(new MenuJson { pid = 2, mtext = "Support", parent = null });
            menuitem.Add(new MenuJson { pid = 3, mtext = "Purchase", parent = null });
            menuitem.Add(new MenuJson { pid = 4, mtext = "Downloads", parent = null });
            menuitem.Add(new MenuJson { pid = 5, mtext = "Resources", parent = null });
            menuitem.Add(new MenuJson { pid = 6, mtext = "Company", parent = null });
            menuitem.Add(new MenuJson { pid = 11, parent = "1", mtext = "ASP.NET" });
            menuitem.Add(new MenuJson { pid = 12, parent = "1", mtext = "ASP.NET MVC" });
            menuitem.Add(new MenuJson { pid = 13, parent = "1", mtext = "Mobile MVC" });
            menuitem.Add(new MenuJson { pid = 14, parent = "1", mtext = "Silverlight" });
            menuitem.Add(new MenuJson { pid = 15, parent = "1", mtext = "Windows Forms" });
            menuitem.Add(new MenuJson { pid = 16, parent = "1", mtext = "Windows Phone" });
            menuitem.Add(new MenuJson { pid = 17, parent = "1", mtext = "WinRT(XMAL)" });
            menuitem.Add(new MenuJson { pid = 18, parent = "1", mtext = "WPF" });
            menuitem.Add(new MenuJson { pid = 19, parent = "1", mtext = "Orubase Studio" });
            menuitem.Add(new MenuJson { pid = 20, parent = "1", mtext = "Metro Studio" });
            menuitem.Add(new MenuJson { pid = 21, parent = "1", mtext = "What's NEw" });
            menuitem.Add(new MenuJson { pid = 22, parent = "21", mtext = "ASP.NET" });
            menuitem.Add(new MenuJson { pid = 23, parent = "21", mtext = "ASP.NET MVC" });
            menuitem.Add(new MenuJson { pid = 24, parent = "21", mtext = "Mobile MVC" });
            menuitem.Add(new MenuJson { pid = 25, parent = "21", mtext = "Windows Forms" });
            menuitem.Add(new MenuJson { pid = 26, parent = "21", mtext = "Windows Phone" });
            menuitem.Add(new MenuJson { pid = 27, parent = "2", mtext = "Direct-Trac Support" });
            menuitem.Add(new MenuJson { pid = 28, parent = "2", mtext = "Community Foruma" });
            menuitem.Add(new MenuJson { pid = 29, parent = "2", mtext = "Knowledge Base" });
            menuitem.Add(new MenuJson { pid = 30, parent = "2", mtext = "Online Documentation" });
            menuitem.Add(new MenuJson { pid = 31, parent = "2", mtext = "Services" });
            menuitem.Add(new MenuJson { pid = 32, parent = "31", mtext = "Consulting" });
            menuitem.Add(new MenuJson { pid = 33, parent = "31", mtext = "Training" });
            menuitem.Add(new MenuJson { pid = 34, parent = "4", mtext = "Evaluation" });
            menuitem.Add(new MenuJson { pid = 35, parent = "4", mtext = "Free E-books" });
            menuitem.Add(new MenuJson { pid = 36, parent = "4", mtext = "Metro Studio" });
            menuitem.Add(new MenuJson { pid = 37, parent = "4", mtext = "C" });
            menuitem.Add(new MenuJson { pid = 38, parent = "4", mtext = "Version History" });
            menuitem.Add(new MenuJson { pid = 39, parent = "5", mtext = "E-Books" });
            menuitem.Add(new MenuJson { pid = 40, parent = "5", mtext = "White Papers" });
            menuitem.Add(new MenuJson { pid = 41, parent = "6", mtext = "More About US" });
            menuitem.Add(new MenuJson { pid = 42, parent = "6", mtext = "Management" });
            menuitem.Add(new MenuJson { pid = 43, parent = "6", mtext = "News & Events" });
            menuitem.Add(new MenuJson { pid = 44, parent = "6", mtext = "Customer Quotes" });
            menuitem.Add(new MenuJson { pid = 45, parent = "6", mtext = "Customer Lists" });
            ViewBag.datasource = menuitem;
            return View();
        }
         
         public class MenuJson
       {
        public string mtext { get; set; }
        public int pid { get; set; }
        public string parent { get; set; }
      }

{% endhighlight %}


The following screenshot is the resultant output Menu with multiple level sub menu item.

![](Getting-Started_images/Getting-Started_img5.png) 