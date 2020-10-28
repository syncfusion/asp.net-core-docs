---
layout: post
title: Character Settings in ASP.NET Core DigitalGauge widget | Syncfusion
description: Learn about character settings support in Syncfusion ASP.NET Core DigitalGauge control and more details.
platform: aspnet-core
control: DigitalGauge
documentation: ug
---

# Character Settings in ASP.NET Core DigitalGauge

## Appearance

The opacity of the character is adjustable with the help of opacity property. The space between two characters are adjusted with spacing property as like in the segment settings.



{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge" width="800" value="SYNCFUSION">
<e-items>
<e-digital-gauge-items >
<e-character-settings opacity="0.3" spacing="4" ></e-character-settings>
</e-digital-gauge-items>
</e-items>
</ej-digital-gauge>


{% endhighlight %}

Execute the above code examples to render the DigitalGauge as follows.


![Appearence using DigitalGauge in ASP.NET Core](Character-Settings_images/Character-Settings_img1.png)

Digital Gauge control with character setting
{:.caption}



## Count and Type

* The number of text to be displayed can be limited by the attribute called count. In Digital Gauge five different types of characters are supported. They are as follows, 
1. EightCrossEightDotMatrix
2. SevenSegment
3. FourteenSegment
4. SixteenSegment 
5. EightCrossEightSquareMatrix.


{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge" width="800" value="123456789">
<e-items>
<e-digital-gauge-items >
<e-character-settings count="10" type="@CharacterType.SevenSegment" spacing="10" >
</e-character-settings>
<e-segment-settings length="8" width="1"></e-segment-settings>
</e-digital-gauge-items>
</e-items>
</ej-digital-gauge>

{% endhighlight %}


Execute the above code examples to render the DigitalGauge as follows.



![Count and Type using DigitalGauge in ASP.NET Core](Character-Settings_images/Character-Settings_img2.png)

Digital Gauge control with character type as seven segment
{:.caption}

## Text Positioning

The text in the DigitalGauge is positioned with position object. This object contains two attributes such as x and y. The x variable positions the text in the horizontal axis and the y variable positions the text in the vertical axis.

{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge" height="300" width="800" >
<e-frame background-image-url="../Content/images/gauge/board1.jpg" >
</e-frame>
<e-items>
<e-digital-gauge-items value="Yellow">
<e-segment-settings color="Yellow"></e-segment-settings>
<e-digital-position x="80" y="10"></e-digital-position>
</e-digital-gauge-items>
</e-items>
</ej-digital-gauge>

{% endhighlight %}


Execute the above code examples to render the DigitalGauge as follows.



![Text Positioning using DigitalGauge in ASP.NET Core](Character-Settings_images/Character-Settings_img3.png)

Digital Gauge control with position text based on the background image
{:.caption}

## Shadow Effects

The text in the Digital Gauge is positioned with position object. This object contains two attributes such as x and y. The x variable positions the text in the horizontal axis and y variable positions the text in the vertical axis.

{% highlight CSHTML %}

<ej-digital-gauge id="Digitalgauge" width="800" >
<e-items>
<e-digital-gauge-items value="WELCOME" shadow-blur="20" 
shadow-color="red" shadow-offset-x="15" shadow-offset-y="15">
<e-segment-settings length="3" width="4"></e-segment-settings>
</e-items>
</ej-digital-gauge>

{% endhighlight %}


Execute the above code examples to render the DigitalGauge as follows.



![Shadow Effects using DigitalGauge in ASP.NET Core](Character-Settings_images/Character-Settings_img4.png)

Digital Gauge control with shadow option
{:.caption}

## Font Customization

You can customize the **font** of the text as per your requirement. To customize the font, you have to set `enable-custom-font`. Following font customization options are available.

**Font-family**- used to set the font-family of the text.

**Font-style**- used to set the font-style of the text.

**Font-size**- used to set the font-size of the text.

{% highlight html %}

<ej-digital-gauge id="DigitalGauge1">
    <e-items>
        <e-font font-family="Arial" font-style="Italic" size="18px" opacity="0.5"> </e-font>
    </e-items>
</ej-digital-gauge>

{% endhighlight %}




