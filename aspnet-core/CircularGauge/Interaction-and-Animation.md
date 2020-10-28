---
layout: post
title: Interaction and Animation | CircularGauge | Syncfusion
description: interaction and animation
platform: aspnet-core
control: CircularGauge
documentation: ug
---

# Interaction and Animation

## Interaction

* Circular Gauge control contains Interaction feature. You can use this interaction feature to change the pointer values manually. You can achieve this by clicking and dragging the pointer over the Gauge and you can see the value of pointer changes dynamically while dragging.
* To Enable/Disable the user interaction you can use the Boolean property called `read-only`. The user interaction option is enabled when you set the value as false for the property readOnly.By default it holds the true value.That is by default it does not support interaction. 

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge" read-only="false" >
</ej-circular-gauge>

{% endhighlight  %}

Execute the above code to render the following output.



![](Interaction-and-Animation_images/Interaction-and-Animation_img1.png)

Circular Gauge with basic interaction property
{:.caption}

## Animations

* Circular Gauge contains an attractive concept called Animation. The animation option enables the pointer to rotate from the minimum value to the current value with animation effects. By using this animation you can change the pointer value dynamically.You can apply the animation on  pointer either by clockwise or counterclockwise based on the scale direction. 
* You can enable / disable it using the property `enable-animation`. Animation is enabled when you set enable-animation as ‘true’. By default it holds the true value. You can control the speed of the pointer during animating by using the property `animation-speed`. It is a numerical value that holds the time in milliseconds. That is when the value is given as 1000, it is considered as 1 second.

{% highlight CSHTML %}

<ej-circular-gauge id="circulargauge" enable-animation=true animation-speed="1000" >
</ej-circular-gauge>

{% endhighlight  %}

Execute the above code to render the following output.



![](Interaction-and-Animation_images/Interaction-and-Animation_img2.png)

Circular Gauge with basic Animation property
{:.caption}


## Gradient

You can change the interior gradient of **Circular Gauge** by using `InteriorGradient` property. The `isRadialGradient` property is used to check whether the gradient is circular or not.  

{% highlight html %}

<ej-circular-gauge id="circularGauge1" is-radial-gradient ="true" >
    
    <% Code %>

    <% Code %>
    
</ej-circular-gauge>
    
{% endhighlight %}

## Distance From Corner

You can display the circular gauge from distance apart from the corner by specifying value for `distance-from-corner` property. 

{% highlight html %}

<ej-circular-gauge id="circularGauge1" distance-from-corner="5" >
        
</ej-circular-gauge>

{% endhighlight %}

## Resize

Circular gauge can be responsive while resizing by specifying `enable-resize` property as true. 

{% highlight html %}

<ej-circular-gauge id="circularGauge1" enable-resize="true" >
        
</ej-circular-gauge>

{% endhighlight %}

## Localization

The circular gauge can be localized based on name of culture specified in `Locale` property.

{% highlight html %}

<ej-circular-gauge id="circularGauge1" locale="en-fr" >
        
</ej-circular-gauge>

{% endhighlight %}

## Themes

**CircularGauge** `Theme` is a set of pre-defined options that are applied to the control before **CircularGauge** is instantiated. Following predefined themes are available in JavaScript **CircularGauge**.

1. flat light
2. flat dark
3. gradient light 
4. gradient dark 
5. azure                      
6. azure dark               
7. lime 
8. lime dark
9. saffron
10. saffron dark
11. gradient azure
12. gradient azure dark
13. gradient lime
14. gradient lime dark
15. gradient saffron
16. gradient saffron dark

The theme for circular gauge can be specified using `Theme` property.

{% highlight html %}

<ej-circular-gauge id="circularGauge1" theme="saffron" >
        
</ej-circular-gauge>

{% endhighlight %}

## Circular Gauge Values 

The `minimum`, `maximum`, `radius` and `value` attributes of circular gauge are used to render the circular gauge with specified location. 

{% highlight html %}

<ej-circular-gauge id="circularGauge1" minimum="10"  maximum="100" radius="50" value="30">
        
</ej-circular-gauge>

{% endhighlight %}





