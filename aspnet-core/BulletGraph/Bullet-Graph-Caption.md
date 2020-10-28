---
layout: post
title: Bullet Graph Caption | BulletGraph |  Syncfusion
description: bullet graph caption
platform: aspnet-core
control: BulletGraph	
documentation: ug
---

# Bullet Graph Caption

Bullet Graph supports title and subtitle to convey what is represented in Bullet Graph. They are customized using `e-caption-settings` property.

## Title

Title is set to Bullet Graph using Text property in `e-caption-settings`. The e-caption-settings also include properties like e-location, e-bullet-font, and Text-Angle for customizing the caption of Bullet Graph.


{% highlight cshtml %}

<ej-bullet-graph id="Bullets" width="600" height="700">
<e-quantitative-scale-settings interval="1" maximum="5" minimum="0">
<e-location x="110" y="200"></e-location>
</e-quantitative-scale-settings>
<e-feature-measures><e-feature-measure comparative-measure="3.5" value="4">
</e-feature-measure></e-feature-measures>
<e-caption-settings text="Revenue YTD">
<e-location  y="220"></e-location>
<e-bullet-font  font-style="bold" font-color="Gray" font-size="14px"></e-bullet-font>    
</e-caption-settings>
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays a Bullet Graph with customized caption using the above code

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img1.png)

Bullet Graph with title
{:.caption}


## Subtitle

Subtitle is added to Bullet Graph using Text property of `e-sub-title` in e-caption-settings. Subtitle also provides properties like e-location, Text-Angle and e-bullet-font to customize subtitle similar to caption.


{% highlight cshtml %}

<ej-bullet-graph id="Bullets" width="600" height="700">
<e-quantitative-scale-settings interval="1" maximum="5" minimum="0">
<e-location x="110" y="200"></e-location>
</e-quantitative-scale-settings>
<e-feature-measures><e-feature-measure comparative-measure="3.5" value="4">
</e-feature-measure></e-feature-measures>
<e-caption-settings text="Revenue YTD">
<e-sub-title text="Subtitle">
<e-location x="20" y="225"></e-location>
<e-bullet-font font-style="italic" font-size="16px"></e-bullet-font>
</e-sub-title>
<e-location  y="210"></e-location>
<e-bullet-font  font-style="bold" font-color="Gray" font-size="14px">
</e-bullet-font>    
</e-caption-settings>
</ej-bullet-graph>

{% endhighlight %}
The following screenshot displays Bullet Graph with a subtitle

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img2.png)

Bullet Graph with subtitle
{:.caption}

## Indicator

You can add Indicator to bullet graph by enabling Visible and setting Text properties of `e-indicator` in e-caption-settings. Indicator is used to represent whether target is achieved or not with text and symbol by comparing current and target values in bullet graph. 

Indicator displays a symbol along with text which is different from caption and subtitle. Images like logos can be used in indicator instead of symbols. Indicator has properties such as `e-symbol`, Text, `Text-spacing`, `Text-Angle`, `e-location` and `e-bullet-font`. 

{% highlight cshtml %}

<ej-bullet-graph id="Bullets" width="600" height="700">
<e-quantitative-scale-settings interval="1" maximum="5" minimum="0">
<e-location x="110" y="200"></e-location>
</e-quantitative-scale-settings>
<e-feature-measures><e-feature-measure comparative-measure="3.5" value="4">
</e-feature-measure></e-feature-measures>
<e-caption-settings text="Revenue YTD">
<e-indicator visible="true" text="+ $0.5 K">
<e-location x="15" y="240"></e-location>
<e-bullet-symbol shape="@SymbolShape.Triangle" color="green">  
<e-bullet-border color="green" width="1"></e-bullet-border>         
</e-bullet-symbol>
</e-indicator>
<e-sub-title text="Subtitle">
<e-location x="20" y="225"></e-location>
<e-bullet-font font-style="italic" font-size="16px"></e-bullet-font>
</e-sub-title>
<e-location  y="210"></e-location>
<e-bullet-font  font-style="bold" font-color="Gray" font-size="14px">
</e-bullet-font>    
</e-caption-settings>
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays a bullet graph with indicator.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img3.png)

Bullet Graph with indicator
{:.caption}

## Trim

The title, subtitle and indicator text can be overlapped to the scale group. You can avoid the overlapped text by using the `enable-trim` property of thee-caption-settings. The default value of the `enable-trim` is true.

{% highlight cshtml %}

<ej-bullet-graph id="Bullets">
<e-caption-settings text="Revenue YTD" enable-trim="true">
</e-caption-settings>
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays the BulletGraph with Trim.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img4.png)

BulletGraph with trim
{:.caption}

## Text Placement

All the caption group elements (caption, subtitle, and indicator) in the Bullet Graph support text positioning by using the property TextPosition available in all caption group elements. The properties, TextAlignment and TextAnchor are used to customize text placement further.

### Text Position

The property `text-position`, is used to position the text at the top, bottom, left, and right side of the quantitative scale. The default value of this property is Float. By default, text can be placed at any desired location by using the Location property. 

{% highlight cshtml %}

<ej-bullet-graph id="Bullets" width="650" height="150" value="8" 
comparative-measure-value="5">
<e-caption-settings text="Bullet Graph Title" text-position="@BulletTextPosition.Top">
<e-bullet-font  font-weight="bold"  font-size="20px">
</e-bullet-font> 
</e-caption-settings>
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays the Bullet Graph with the title positioned above.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img5.png)

Bullet Graph with title automatically positioned above the scale
{:.caption}


### Text Alignment

Alignment of text at different positions with respect to scale can be customized by using the `text-alignment` property. Text can be aligned in the near, center, and far locations of the scale. Text alignment depends upon TextPosition property and is not applicable when the value of the TextPosition property is Float. The default value of the TextAlignment property is Near. 

{% highlight cshtml %}

<ej-bullet-graph id="Bullets" width="650" height="150" value="8" 
comparative-measure-value="5">
<e-caption-settings text="Revenue" text-position="@BulletTextPosition.Left"
text-anchor="@BulletTextAnchor.Middle">
<e-bullet-font  font-weight="bold"  font-size="16px">
</e-bullet-font> 
<e-sub-title text="$ in thousands" text-position="@BulletTextPosition.Left"
text-alignment="@BulletTextAlignment.Center">
<e-bullet-font font-weight="bold" font-size="12px"></e-bullet-font>
</e-sub-title>
</e-caption-settings>
<e-quantitative-scale-settings>
<e-location x="120" y="40"></e-location>
</e-quantitative-scale-settings>
</ej-bullet-graph>

{% endhighlight %}

The following screenshot displays the Bullet Graph with the title and subtitle at different alignments.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img6.png)

Bullet graph with the title aligned at near and sub title aligned at center positions
{:.caption}

### Text Anchor

Text elements aligned at the same position are anchored by using the `text-anchor` property. These can be anchored at the Start, Middle, and End. The default value of this property is Start and applicable only when two or more text elements are aligned at the same position. 

{% highlight cshtml %}

<ej-bullet-graph id="Bullets" width="650" height="150" value="8" 
comparative-measure-value="5">
<e-caption-settings text="Revenue" text-position="@BulletTextPosition.Left"
text-anchor="@BulletTextAnchor.Middle">
<e-bullet-font  font-weight="bold"  font-size="16px">
</e-bullet-font> 
<e-sub-title text="$ in thousands" text-position="@BulletTextPosition.Left"
text-alignment="@BulletTextAlignment.Center">
<e-bullet-font font-weight="bold" font-size="12px"></e-bullet-font>
</e-sub-title>
</e-caption-settings>
<e-quantitative-scale-settings>
<e-location x="120" y="40"></e-location>
</e-quantitative-scale-settings>
</ej-bullet-graph>

{% endhighlight %}

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img7.png)

Bullet Graph with title text anchored at the center with respect to subtitle text
{:.caption}

### Padding

The space required between text and quantitative scale is customized by using the `padding` property. The default value of this property is 5 and not applicable when the value of the TextPosition property is Float. 

{% highlight cshtml %}

<ej-bullet-graph id="Bullets" width="650" height="150" value="8" 
comparative-measure-value="5">
<e-caption-settings text="Profit in %" text-position="@BulletTextPosition.Left"
text-alignment="@BulletTextAlignment.Center" padding="10">
<e-bullet-font  font-weight="bold"  font-size="16px">
</e-bullet-font> 
</e-caption-settings>
<e-quantitative-scale-settings>
<e-location x="120" y="40"></e-location>
</e-quantitative-scale-settings>
</ej-bullet-graph>

{% endhighlight %}

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img8.png)

Bullet graph with 10 pixel padding between the title text and quantitative scale
{:.caption}


## Localization

Bullet graph supports localization for its axis labels and tooltip. To render the bullet graph with specific culture you have to refer the corresponding globalize culture script and need to specify the culture name in locale property of bullet graph.

Enable Group Separator is used to Convert the date object to string while using the locale settings, you can set enableGroupSeparator property as true.



{% highlight html %}

<ej-bullet-graph id="bullet1" locale="fr-FR" enable-group-seperator="true">         
          
</ej-bullet-graph>

{% endhighlight %}

