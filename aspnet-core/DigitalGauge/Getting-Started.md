---
layout: post
title: Getting-Started
description: getting started
platform: aspnet-core
control: DigitalGauge
documentation: ug
---

# Getting Started

* The ASP.NET Core 1.0 Digital Gauge provides support to display the DigitalGauge within your web page and allows you to customize it. This section encompasses the details on how to configure DigitalGauge. Here you will learn how to provide data for a DigitalGauge and display the data in the required way. 
* In addition, you will learn how to customize the default DigitalGauge appearance according to your requirements. As a result, you will get a DigitalGauge that shows it as Digital thermometer.
* You can use this DigitalGauge in advertisements, decorative purposes, displaying share details in share market, game score boards, token systems, etc.


![](Getting-Started_images/Getting-Started_img1.png)

Digital Thermometer
{:.caption}

## Create a Digital Gauge

ASP.NET Core Digital Gauge widget basically renders with flexible APIs. You can easily create the Digital Gauge widget by using the following steps.

1. First create an Core Project and add necessary Dll's and scripts with the help of the given [ASP.NET core 1.0-Getting Started](/aspnet-core/getting-started) Documentation.
2. Add the following code example to the corresponding view page to render Digital Gauge.

   ~~~ cshtml
   
	<ej-digital-gauge id="Digitalgauge"></ej-digital-gauge>
		
   ~~~
   {:.prettyprint }

3. Add the following code example in the controller page.

   ~~~ csharp   
   
	public IActionResult Default()		
        
	{
            
		return View();
    
	}		

   ~~~
   {:.prettyprint }


   
Run the above code example and you will get a default Digital Gauge as follows.

![](Getting-Started_images/Getting-Started_img2.png)

Digital Gauge
{:.caption}

## Set Height and Width values

Basic attributes of each canvas elements are height and width. You can set the height and width of the gauge.

{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge" 
                  height="145" 
                  width="260">
</ej-digital-gauge>

{% endhighlight %}

Run the above code example and you will see a default gauge with the specified height and width values.

![](Getting-Started_images/Getting-Started_img3.png)

Digital Gauge with Height and Width
{:.caption}

## Set Items Property

Items have different properties to customize the Digital Gauge.

### Add Segment and Character Properties

* In the Welcome Board, the text color must be attentive in nature. You can give some segment properties such as segment spacing, segment width, segment color, segment length and segment opacity.
* Character type is to define the Digital representation of the character. The five types of character representation available are,
	1. EightCrossEightDotMatrix
	2. SevenSegment
	3. FourteenSegment
	4. SixteenSegment 
	5. EightCrossEightSquareMatrix.

{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge">
        <e-items>
            <e-digital-gauge-items value="102">
                <e-segment-settings length="20"
                                    width="2">
                </e-segment-settings>
                <e-character-settings spacing="12"
                                      type="SevenSegment">
                </e-character-settings>
            </e-digital-gauge-items>
        </e-items>
</ej-digital-gauge>

{% endhighlight %}

Run the above code example and you will see the following output.

![](Getting-Started_images/Getting-Started_img4.png)

Digital Gauge Segment Properties
{:.caption}


## Add Background Image

* Add a <div> element to set the background for the Digital Gauge. 
* Add a style tag in the View page to add the background image for the Digital Gauge.
* Add the required properties to show the background image such as position, margin, display, etc.,


{% highlight CSHTML %}

<div id="frameDiv">

<ej-digital-gauge id="Digitalgauge">

</ej-digital-gauge>

</div>

<style>

#frameDiv {

align : center;

position : relative;

margin : 0px auto;

display :table;

background-image :url("script/frame.png");

background-repeat :no-repeat;

}

</style>


{% endhighlight %}


Run the above code example and you will see the following output.                    

![](Getting-Started_images/Getting-Started_img5.png)

Digital Gauge Background Image
{:.caption}

## Add Location

The Location property is used to position the digital letters inside the canvas element.

{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge">
        <e-items>
            <e-digital-gauge-items value="102">

                <e-digital-position x="15" 
                                    y="40">
                </e-digital-position>

            </e-digital-gauge-items>
        </e-items>
</ej-digital-gauge>

{% endhighlight %}


Run the above code example and you will see the following output. 

![](Getting-Started_images/Getting-Started_img6.png)

Digital Gauge with Segment Location
{:.caption}

## Add Items Collection 

You can further add the Items Collection to display the temperature value like Digital Thermometer.

{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge">
        <e-items>
            <e-digital-gauge-items value="102">
                <e-segment-settings length="20"
                                    width="2">
                </e-segment-settings>
                <e-character-settings spacing="12"
                                      type="SevenSegment">
                </e-character-settings>
                <e-digital-position 
                                    x="15" 
                                    y="40">
                </e-digital-position>
            </e-digital-gauge-items>
            <e-digital-gauge-items value="0">
                <e-segment-settings length="5"
                                    width="2">
                </e-segment-settings>
                <e-character-settings spacing="12"
                                      type="SevenSegment">
                </e-character-settings>
                <e-digital-position x="85"
                                    y="28">
                </e-digital-position>
            </e-digital-gauge-items>
            <e-digital-gauge-items value="F">
                <e-segment-settings length="20"
                                    width="2">
                </e-segment-settings>
                <e-character-settings spacing="12"
                                      type="SevenSegment">
                </e-character-settings>
                <e-digital-position x="170"
                                    y="40">
                </e-digital-position>
            </e-digital-gauge-items>
            <e-digital-gauge-items value="38">
                <e-segment-settings length="9"
                                    width="1"
                                    color="#F5b43f">
                </e-segment-settings>
                <e-character-settings spacing="12"
                                      type="SevenSegment">
                </e-character-settings>
                <e-digital-position x="70"
                                    y="90">
                </e-digital-position>
            </e-digital-gauge-items>
            <e-digital-gauge-items value="0">
                <e-segment-settings length="3"
                                    width="1"
                                    color="#F5b43f">
                </e-segment-settings>
                <e-character-settings spacing="12"
                                      type="SevenSegment">
                </e-character-settings>
                <e-digital-position x="90"
                                    y="80">
                </e-digital-position>
            </e-digital-gauge-items>
            <e-digital-gauge-items value="c">
                <e-segment-settings length="9"
                                    width="1"
                                    color="#F5b43f">
                </e-segment-settings>
                <e-character-settings spacing="12"
                                      type="SevenSegment">
                </e-character-settings>
                <e-digital-position x="120"
                                    y="90">
                </e-digital-position>
            </e-digital-gauge-items>
        </e-items>
</ej-digital-gauge>

{% endhighlight %}


Run the above code example and you will see the following output.                    

![](Getting-Started_images/Getting-Started_img7.png)

Digital Gauge with Item Collection
{:.caption}