---

layout: post
title: Load on demand in DropDownList control for Syncfusion ASP.NET Core
description: Describes about Load on demand in DropDownList control for Syncfusion ASP.NET Core
platform: aspnet-core
control: DropDownList, loadOnDemand
documentation: ug

---

## Load On Demand

Load on demand feature allows the DropDownList items load on request from the service/database, during only on click the DropDown icon or DropDownList. This functionality helps to improve performance on control initial rendering time. Because data items load on request. 

The loadOnDemand property is used to enable or disable the load on demand functionality of the DropDownList.

{% highlight html %}

     <ej-drop-down-list id="selectCar" target-id="carsList" width="100%" watermark-text="Select a Car" load-on-demand=”true”></ej-drop-down-list>
            <div id="carsList">
                <ul>
                    <li>Audi A4</li>
                    <li>Audi A5</li>
                    <li>Audi A6</li>
                    <li>Audi A7</li>
                    <li>Audi A8</li>
                </ul>
            </div>

     
{% endhighlight %}


![](LoadOnDemand_images/loadondemand.png)