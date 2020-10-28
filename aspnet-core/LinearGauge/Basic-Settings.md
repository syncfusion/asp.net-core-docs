---
layout: post
title: Basic Settings
description: basic settings
platform: aspnet-core
control: LinearGauge
documentation: ug
---

# Basic Settings

## Adding Dimension

* The basic customization for any control is setting the dimension. Here dimension refers the two major attributes, height and width. The height and width assigned in the control will render the canvas element in the given size. 

* The value attribute is used to set all pointer value in the Linear Gauge control. The attributes, minimum and maximum value are used to set the minimum value and maximum value for all the scales exist in the Linear Gauge control.


{% highlight html %}

<ej-linear-gauge id="lineargauge" height="500" width="300" minimum=10 maximum=110 value=78>
    <e-scales>
       <e-scale background-color="transparent" show-marker-pointers="false" show-bar-pointers="true">
              <e-border color="trasparent" width="0"></e-border>
           <e-bar-pointers>
              <e-bar-pointer  width="5" background-color="grey"></e-bar-pointer>
           </e-barpointers>	
          <e-ticks>
              <e-tick type="majorinterval" width="2" color="#8c8c8c">
                    <e-distance-from-scale x="7" y="0"></e-distance-from-scale>
              </e-tick>
              <e-tick type="minorinterval" height="6" width="1" color="#8c8c8c">
                <e-distance-from-scale x="7" y="0"></e-distance-from-scale>
              </e-tick>
        </e-ticks>
       </e-scale>
    </e-scales>
</ej-linear-gauge>

{% endhighlight %}

Execute the above code to render the following output.



![](Basic-Settings_images/Basic-Settings_img1.png)



## Adding frame

* Frame is the element that decides the appearance of the **Linear Gauge**. You can customize it by using the object called **frame.** It contains frame inner width, frame outer width and frame background image URL properties. 

* The **inner-width** of the frame defines the distance between the canvas element and the frame and the **outer-width** refers to distance from the frame. **background-url** is used to set the background image for the frame.


{% highlight html %}

<ej-linear-gauge id="lineargauge" height="500" width="300" minimum=10 maximum=110 value=80>
    <e-frame inner-width=8 outer-width=10 background-url=""></e-frame>
    <e-scales>
       <e-scale background-color="transparent" show-marker-pointers="false" show-bar-pointers="true">
           <e-border color="trasparent" width="0"></e-border>
           <e-bar-pointers>
              <e-bar-pointer  width="5" background-color="grey"></e-bar-pointer>
           </e-bar-pointers>	
          <e-ticks>
              <e-tick type="majorinterval" width="2" color="#8c8c8c">
                <e-distance-from-scale x="7" y="0"></e-distance-from-scale>
              </e-tick>
              <e-tick type="minorinterval" height="6" width="1" color="#8c8c8c">
                <e-distance-from-scale x="7" y="0"></e-distance-from-scale>
              </e-tick>
        </e-ticks>
       </e-scale>
    </e-scales>
</ej-linear-gauge>

{% endhighlight %}

Execute the above code to render the following output.



![](Basic-Settings_images/Basic-Settings_img2.png)



## Appearance

* The attribute orientation is used to render the Linear Gauges either in horizontal position or vertical position.You can set the background color for the Linear Gauge for better appearance using the backgroundColor property. borderColor specifies the border color of the Linear Gauge. You can also add gradient effects to Linear Gauge with the help of pointerGradient1 and pointerGradient2 attribute.

* Theme is the basic property of any control. It is used to set the theme for Linear Gauge. There are two types of themes used for Linear Gauge such as

 * flat light

 * flat dark


{% highlight html %}

<ej-linear-gauge id="lineargauge" height="100" width="400" minimum=10 maximum=110 
             value=80 orientation="" label-color="Black" theme="saffron" >
             <e-frame inner-width=8 outer-width=10 background-image-url=""></e-frame>
    <e-scales>
       <e-scale background-color="transparent" show-marker-pointers="false" show-bar-pointers="true">
           <e-border color="trasparent" width="0"></e-border>
           <e-bar-pointers>
              <e-bar-pointer  width="5" background-color="grey"></e-bar-pointer>
           </e-bar-pointers>	
          <e-ticks>
              <e-tick type="majorinterval" width="2" color="#8c8c8c">
                <e-distance-from-scale x="7" y="0"></e-distance-from-scale>
              </e-tick>
              <e-tick type="minorinterval" height="6" width="1" color="#8c8c8c">
                <e-distance-from-scale x="7" y="0"></e-distance-from-scale>
              </e-tick>
        </e-ticks>
       </e-scale>
    </e-scales>
</ej-linear-gauge>

{% endhighlight %}


Execute the above code to render the following output.

![](Basic-Settings_images/Basic-Settings_img3.png)



## Responsive 

* For any display devices, the control is to be rendered based on the space in that device. The control must be responsive. For this purpose resizing property is present in **Linear Gauge** control. 

* The **Linear Gauge** renders with the specified value. When the browser changes its size, the canvas element checks the dimension with its parent element and if there are any changes in parent dimension, gauge control also changes the dimension based on its parent changes. You can enable this feature using **isResponsive** property**.**


{% highlight html %}

<ej-linear-gauge id="lineargauge" height="100" width="400" label-color="Black">
    <e-frame inner-width=8 outer-width=10 background-image-url="" theme="saffron" is-responsive="true"></e-frame>
    <e-scales>
       <e-scale backgroundColor="transparent" direction="clockwise" show-marker-pointers="false" 
                         show-bar-pointers="true">
           <e-border color="trasparent" width="0"></e-border>
           <e-bar-pointers>
              <e-bar-pointer  width="5" background-color="grey"></e-bar-pointer>
           </e-bar-pointers>	
          <e-ticks>
              <e-tick type="majorinterval" width="2" color="#8c8c8c">
                 <e-distance-from-scale x="7" y="0"></e-distance-from-scale>
              </e-tick>
              <e-tick type="minorinterval" height="6" width="1" color="#8c8c8c">
                 <e-distance-from-scale x="7" y="0"></e-distance-from-scale>
              </e-tick>
        </e-ticks>
       </e-scale>
    </e-scales>
</ej-linear-gauge>

{% endhighlight %}

Execute the above code to render the following output.


![](Basic-Settings_images/Basic-Settings_img4.png)


Responsiveness of the linear gauge is controlled by using `enable-resize` property.


{% highlight html %}

<%-- For Linear Gauge rendering-- %>

<%-- For enabling responsible layout-- %>

<ej-linear-gauge id="lineargauge" height="100" width="400" enable-resize="true">    
</ej-linear-gauge>

{% endhighlight %}


## Localization

**LinearGauge** supports localization for its axis labels and tooltip. To render the gauge with specific culture you have to refer the corresponding globalize culture script and need to specify the culture name in `locale` property of gauge.

**Enable Group Separator** is used to Convert the date object to string while using the locale settings, you can set `enable-group-separator` property as **true**.



{% highlight html %}

<ej-linear-gauge id="lineargauge" locale="en-fr" enable-group-seperator="true">    
</ej-linear-gauge>

{% endhighlight %}




