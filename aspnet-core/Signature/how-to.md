---
layout: post
title: How To | Signature | ASP.NET Core | Syncfusion
description: How To
platform: aspnet-core
control: Signature
documentation: ug
keywords: save, signature
---

# How To

## Save signature image with user defined format

By default, the downloaded image form the signature canvas will be in **png** format. We can define our own format to download the image with **save-image-format** property. And we can also save the image along with the background by using the **save-with-background** property.

In the View page, define the following code.

{% highlight CSHTML %}


<ej-signature id="mySign" height="400px" width="500" stroke-width="3" background-image="../images/water.png" is-responsive="true" save-with-background="true" />

<ej-button id="signsave" text="Save" show-rounded-corner="true" click="onSave" />

{% endhighlight %}

Add the following script to define the download format for the canvas.

{% highlight js %}

<script type="text/javascript">
        
         function onSave() {
            var sign = $("#mySign").ejSignature("instance");
            sign.option("saveImageFormat", "jpg") 
            sign.save("mySignature");
        }

    </script>

{% endhighlight %}


The following screenshot illustrates the Signature with saving (downloading) the drawn image along with its background.

![How to](how_to_images\savesignatureimagewithuserdefinedformat_img1.png)


## To clear the Signature

To clear the signature, you can simply use the **clear()** method. This method will clear all the drawn strokes in the signature canvas and leaves it empty.

{% highlight razor %}

<ej-signature id="mySignature" height="400px" width="500" stroke-width="3" is-responsive="true" />

<ej-button id="signclear" text="Clear" show-rounded-corner="true" click="onClear" />

{% endhighlight %}

{% highlight js %}

<script type="text/javascript">
    function onClear() {
            var sign = $("#mySignature").ejSignature("instance");
            sign.clear();
        }
 </script>

{% endhighlight %}

## Make signature as responsive

When the signature control is resized or even the window is resized the strokes drawn in the signature will be disappeared. To make the strokes visible even after resizing the window, we must set the **is-responsive** property as true.

In the View page, define the following code to render signature with responsive.

{% highlight CSHTML %}

<ej-signature id="mySign"  is-responsive="true"/>

{% endhighlight %}


The following screenshot illustrates the Signature with responsiveness.

Before Responsiveness:

![Signature as responsive](how_to_images\makesignatureasresponsive_img1.png)

After giving the Responsiveness:

![signature as responsive](how_to_images\makesignatureasresponsive_img2.png)

## To check whether any input to the signature control since render

We can detect whether not there has been any input to the signature control since render. To detect we can use the storeSnap public variable, which is an array that stores all the canvas inputs. At initial rendering this array is empty and we can use this variable to check for the drawn strokes.


{% highlight js %}

   <script type="text/javascript">
      var sign = $("#signature").ejSignature("instance");

            if (ej.isNullOrUndefined(sign.storeSnap)) {
               
                //Something

            }
    </script>   

{% endhighlight %}