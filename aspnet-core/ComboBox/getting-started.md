---
layout: post
title: Getting Started with ASP.NET Core ComboBox control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio ASP.NET Core ComboBox control, its elements, and more.
platform: aspnet-core
control: ComboBox
documentation: ug
keywords: allowCustom, ComboBox, dataSource, popupHeight, popupWidth
---

# Getting Started with ASP.NET Core ComboBox

This section explains how to create a simple **ComboBox** component and configure its available functionalities in TypeScript, using [`ASP.NET Core`](https://help.syncfusion.com/aspnet-core/gettingstarted/getting-started-1-1-0) documentation.

{% highlight CSHTML %}
  
   /*ej-Tag Helper code to render ComboBox*/

            <ej-ComboBox id="selectCar"></ej-ComboBox>

       
  {% endhighlight  %}

  {% highlight Razor %}
  
       /*Razor code to render DropDownList*/

          @{Html.EJ().ComboBox("id").Render();}

  {% endhighlight  %}

N> To render the ComboBox Control, you can use either Razor or Tag helper code as given in the code sample above.

## Initialize the ComboBox

To initialize the ComboBox

{% highlight html %}

<div class="frame">
        <div class="control"> 
        <ej-combo-box id="select" datasource="(IEnumerable<CarsList>)ViewBag.datasource" placeholder="Select">
        <e-combo-box-fields text="text" />
    </ej-combo-box>
        </div>
    </div>

{% endhighlight %}

{% highlight c# %}

        public ActionResult Index()
        {
            List<CarsList> car = new List<CarsList>();
            car.Add(new CarsList { text = "Audi S6" });
            car.Add(new CarsList { text = "Austin-Healey" });
            car.Add(new CarsList { text = "Alfa Romeo" });
            car.Add(new CarsList { text = "Aston Martin" });
            car.Add(new CarsList { text = "BMW 7" });
            car.Add(new CarsList { text = "Bentley Mulsanne" });
            ViewBag.datasource = car;
            return View();
        }
     public class CarsList
      {
        public string text { get; set; }

      }
       
  {% endhighlight  %}

![Getting-Started_images](Combobox_getting_started_images/Getting-Started.png)

## Binding data source

After initializing, populate the ComboBox with data using the **dataSource** property. Here, an array of string values is passed to the ComboBox component.

{% highlight CSHTML %}

 @{string[] datasource = new string[] { "Badminton", "Cricket", "Football", "Golf", "Tennis" };
    }
    <div class="frame">
        <div class="control"> 
        <ej-combo-box id="selectCar" datasource="datasource" placeholder="Select">
            <e-combo-box-fields text="text"/>
        </ej-combo-box>
        </div>
    </div>

{% endhighlight %}


![Combobox_getting_started_images1](Combobox_getting_started_images/Getting-Started1.png)


## Custom values

The ComboBox allows the user to give custom values when it is not available in the predefined set of values. By default, this is enabled by the **allowCustom** property. In this case, both text and value fields are considered the same. When a form is submitted, the custom value will be sent to the post back handler.

{% highlight CSHTML %}

<div class="frame">
        <div class="control"> 
        <ej-combo-box id="select" datasource="(IEnumerable<CarsList>)ViewBag.datasource" allow-custom="true" placeholder="Select">
            <e-combo-box-fields text="text" value="id"/>
        </ej-combo-box>
        </div>
    </div>

{% endhighlight %}

{% highlight c# %}

   public ActionResult Index()
        {
            List<CarsList> car = new List<CarsList>();
            car.Add(new CarsList { text = "Audi S6" });
            car.Add(new CarsList { text = "Austin-Healey" });
            car.Add(new CarsList { text = "Alfa Romeo" });
            car.Add(new CarsList { text = "Aston Martin" });
            car.Add(new CarsList { text = "BMW 7" });
            car.Add(new CarsList { text = "Bentley Mulsanne" });
            ViewBag.datasource = car;
            return View();
        }
     public class CarsList
      {
        public string text { get; set; }

      }
  {% endhighlight  %}

![Combobox_getting_started_images1](Combobox_getting_started_images/Combobox_data_binding_img1.png)

## Configure the popup list

By default, the width of the popup list automatically adjusts according to the ComboBox input element's width, and the height of the popup list is '300px'.

The height and width of the popup list can also be customized using the **popupHeight** &nbsp;and **popupWidth** properties respectively.

In the following sample, popup list's width and height are configured.

{% highlight CSHTML %}

<div class="frame">
        <div class="control"> 
        <ej-combo-box id="select" datasource="(IEnumerable<CarsList>)ViewBag.datasource" popup-height="100px" popup-width="200px" placeholder="Select">
            <e-combo-box-fields text="text" value="id"/>
        </ej-combo-box>
        </div>
    </div>

{% endhighlight %}

{% highlight c# %}

  
         public ActionResult Index()
        {
            List<CarsList> car = new List<CarsList>();
            car.Add(new CarsList { text = "Audi S6" });
            car.Add(new CarsList { text = "Austin-Healey" });
            car.Add(new CarsList { text = "Alfa Romeo" });
            car.Add(new CarsList { text = "Aston Martin" });
            car.Add(new CarsList { text = "BMW 7" });
            car.Add(new CarsList { text = "Bentley Mulsanne" });
            ViewBag.datasource = car;
            return View();
        }
      public class CarsList
      {
        public string text { get; set; }

      }
  {% endhighlight  %}

![Combobox_getting_started_images](Combobox_getting_started_images/popup.png)

