---
layout: post
title: Pointers | ASP.NET Core | PivotGauge | Syncfusion
description: This document illustrates that how to enable pointers and its customization in ASP.NET Core PivotGauge control
platform: aspnet-core
control: PivotGauge
documentation: ug
---

# Pointers

## Pointer types

The pivot gauge has two types of pointers as follows:

* Needle
* Marker

Needle type pointer is the default pointer which is always located at the center of the gauge. Following are supported shapes for the needle pointers:

* Rectangle
* Triangle
* Trapezoid
* Arrow
* Image.

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-scales>
        <e-circular-scales>
            <e-pointer-collections>
                <e-pointers type="Needle" marker-type="Trapezoid"></e-pointers>
            </e-pointer-collections>
        </e-circular-scales>
    </e-scales>
</ej-pivot-gauge>

{% endhighlight %}

![Needle pointer in ASP NET Core pivot gauge control](Pointers_images/NeedlePointer.png) 

For marker pointer, the available shapes are Rectangle, Triangle, Ellipse, Diamond, Pentagon, Circle, Slider, Pointer, Wedge, Trapezoid, RoundedRectangle, and Image.

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-scales>
        <e-circular-scales>
            <e-pointer-collections>
                <e-pointers type="Marker" marker-type="Diamond"></e-pointers>
            </e-pointer-collections>
        </e-circular-scales>
    </e-scales>
</ej-pivot-gauge>

{% endhighlight %}

![Marker pointer in ASP NET Core pivot gauge control](Pointers_images/MarkerPointer.png) 

## Adding pointer collection

The pointer collection can be directly added to the scales option within the  pivot gauge control. 

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-scales>
        <e-circular-scales>
            <e-pointer-collections>
                <e-pointers type="Needle" marker-type="Triangle"></e-pointers>
                <e-pointers type="Marker" marker-type="Diamond"></e-pointers>
            </e-pointer-collections>
        </e-circular-scales>
    </e-scales>
</ej-pivot-gauge>

{% endhighlight  %}

![Collection of pointers in ASP NET Core pivot gauge control](Pointers_images/AddingPointerCollection.png)

## Appearance customization

The appearance of the pointer can be customized through the following properties:

* **e-border**: Sets the color and width of the pointer border.
* **background-color**: Sets the background color of the pointer.
* **length**: Sets the length of the pointer.
* **width**: Sets the width of the pointer.
* **opacity**: Sets the opacity of the pointer. By default, the value is 1.
* **type**: Sets the type of the pointer. By default, the type is Needle.

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-scales>
        <e-circular-scales>  
            <e-pointer-collections>
                //For customizing needle pointer
                <e-pointers type="Needle" marker-type="Triangle" background-color="yellow" length="120" width="7" opacity="60">
                    <e-border color="green" width="2"></e-border>
                </e-pointers>
                //For customizing marker pointer
                <e-pointers type="Marker" marker-type="Diamond" background-color="yellow" length="25" width="15" opacity="80">
                    <e-border color="green" width="2"></e-border>
                </e-pointers>
            </e-pointer-collections>
        </e-circular-scales>
    </e-scales>
</ej-pivot-gauge>

{% endhighlight %}

![Custom appearance of ASP NET Core pivot gauge control](Pointers_images/AppearanceCustomization.png) 

## Pointer position

The pointer can be positioned with the help of following two properties:

* **DistanceFromScale**: Defines the distance between the scale and pointer. By default, the value is 0.
* **Placement**: Defines the location of the pointer. By default, the value is center.

N> Both the properties can be applied only if the pointer type is set to marker. The needle type pointer appears only at the center of the control, which is its default position.

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-scales>
        <e-circular-scales>  
            <e-pointer-collections>
                <e-pointers type="Marker" distance-from-scale="2" placement="Far"></e-pointers>
            </e-pointer-collections>
        </e-circular-scales>
    </e-scales>
</ej-pivot-gauge>

{% endhighlight %}

![Pointer position in ASP NET Core pivot gauge control](Pointers_images/PointerPosition.png)

## Pointer image

It is possible to replace the pointers with an image. To view the pointers as an image, set the appropriate location in the `image-url` property.

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-scales>
        <e-circular-scales>  
            <e-pointer-collections>
               //For replacing needle pointer with image
                <e-pointers type="Needle" needle-type="Image" image-url="../image.png"></e-pointers>
                //For replacing marker pointer with image
                <e-pointers type="Marker" marker-type="Image" image-url="../image.png"></e-pointers>
            </e-pointer-collections>
        </e-circular-scales>
    </e-scales>
</ej-pivot-gauge>

{% endhighlight %}

![Pointer image in ASP NET Core pivot gauge control](Pointers_images/PointerImage.png)

## Pointer value text

To display the current value of pointers in the pivot gauge control, the **"e-pointer-value-text"** option is used.  Following are the properties used to enable and customize the pointer value text:
 
* **show-value**: Enables the pointer value text by setting the property to true. By default, its value is true.
* **distance**: Sets the distance between the pointer and the text.
* **color**: Sets the color of the text.
* **opacity**: Sets the opacity of the text. By default, its value is 1.
* **angle**: Sets the rotation angle of the text. By default, its value is 0.
* **font**: Sets the font size, font style, and font family of the text.

{% highlight cshtml %}

<ej-pivot-gauge id="PivotGauge1">
    <e-scales>
        <e-circular-scales>  
            <e-pointer-collections>
                <e-pointers type="Needle">
                //For needle type
                    <e-pointer-value-text show-value="true" distance="10" color="red" opacity="70" angle="20">
                        <e-font font-family="Arial" font-style="Normal" size="15px"></e-font>
                    </e-pointer-value-text>
                </e-pointers>
                <e-pointers type="Marker">
                //For marker type
                    <e-pointer-value-text show-value="true" distance="40" color="red" opacity="70" angle="-40">
                        <e-font font-family="Arial" font-style="Normal" size="15px"></e-font>
                    </e-pointer-value-text>
                </e-pointers>
            </e-pointer-collections>
        </e-circular-scales>
    </e-scales>
</ej-pivot-gauge>

{% endhighlight %}

![Pointer value text in ASP NET Core pivot gauge control](Pointers_images/PointerValueText.png)