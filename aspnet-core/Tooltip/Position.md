---
layout: post
title: Position | Tooltip | ASP.NET Core | Syncfusion
description: Positionining support to Tooltip widget for Syncfusion Essential Dotnet Core
platform: aspnet-core
control: Tooltip
documentation: ug
keywords : Dotnetcore Tooltip,ASP Dotnet Core Tooltip, core Tooltip,aspnetcore Tooltip widget,Dotnetcore Tooltip position,Dotnetcore Tooltip collision
---

# Position

The position object defines various attributes of the Tooltip position, including the element it is positioned in relation to, and how the position is adjusted within the defined container.

Lets position the Tooltips (stems) left center corner at the right center of the target element.

{% highlight CSHTML %}
 
    <div class="img" id="sample">
        <a target="_blank" href="image/taj.png">
            <img src="http://aspnetcore.syncfusion.com/images/tooltip/template-05.png" alt="Delphi">
        </a>
        <div class="desc">Delphi Succinctly</div>
    </div>

    <ej-tooltip id="sample" content="Learn the fundamentals of Delphi to build a variety of solutions for many devices and platforms.">
        <e-tooltip-position>
            <e-stem horizontal="left" vertical="center" />
            <e-target horizontal="right" vertical="center" />
        </e-tooltip-position>
    </ej-tooltip>

{% endhighlight %}

Apply the following styles to show the Tooltip.

{% highlight css %}

    <style>
        div.img {
            border: 1px solid #ccc;
            float: left;
            box-sizing: border-box;
            height: 200px;
            width: 146px;
        }
        div.img img{
            width: 100%;
            height: 166px;
        }
        div.desc {
            padding: 6px;
            text-align: center;
        }
    </style>
    
{% endhighlight %}

![](Position_images/position.png)

N> By default, the Tooltips "center bottom" corner is placed at the center top of the target element.

## Containment 

Determines the HTML element in which the Tooltip is appended to e.g. its containing element and The tooltip will be restricted to move only within the specified container element.

Let's append our Tooltip to a custom 'frame' container:

{% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip1"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej-tooltip id="tooltip1" content="JavaScript is the programming language of HTML and the Web." containment=".frame">
    </ej-tooltip>

{% endhighlight %}

N> By default all Tooltips are appended to the document.body element.

## Associates 

 The Tooltip will be positioned in relation to target element. Can also be set to 'mouse' or the window, or an absolute x/y position on the page.
 
 Let's position the Tooltip in relation to the 'a' element inside the div element:
 
 {% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip2"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej-tooltip id="tooltip2" content="JavaScript is the programming language of HTML and the Web." >
    </ej-tooltip>

{% endhighlight %}
 
We can also position the Tooltip in relation to the mouse.
 
{% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip3"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej-tooltip id="tooltip3" content="JavaScript is the programming language of HTML and the Web." associate="mousefollow">
    </ej-tooltip>

{% endhighlight %}

Position the tooltip at the current mouse position, once enter to the target element as follows

{% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip4"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej-tooltip id="tooltip4" content="JavaScript is the programming language of HTML and the Web." associate="mouseenter">
    </ej-tooltip>

{% endhighlight %}


It also possible to place the tooltip relation to the window as follows

{% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip5"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej-tooltip id="tooltip5" content="JavaScript is the programming language of HTML and the Web." associate="window">
        <e-tooltip-position>
            <e-target horizontal="right" vertical="bottom" />
        </e-tooltip-position>
    </ej-tooltip>

{% endhighlight %}
    
And last but not least, absolute positioning via X,Y co-ordinates e.g. a Tooltip at 10px from left and top of the page:

{% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip6"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej-tooltip id="tooltip6" content="JavaScript is the programming language of HTML and the Web." associate="axis">
        <e-tooltip-position>
            <e-target horizontal="10" vertical="10" />
        </e-tooltip-position>
    </ej-tooltip>

{% endhighlight %}

## Collision 

When the positioned element overflows the window in some direction, move it to an alternative position. 

The following values determines the kind of positioning that takes place.

<table>
<tr>
<td>
Value<br/></td><td>
Description<br/></td></tr>
<tr>
<td>
Flip<br/></td><td>
Flips the element to the opposite side of the target if the collision detected.<br/></td></tr>
<tr>
<td>
Fit<br/></td><td>
Shift the element away from the edge of the window.<br/></td></tr>
<tr>
<td>
FlipFit(Default)<br/></td><td>
Ensure as much of the element is visible as possible to showcase.<br/></td></tr>
<tr>
<td>
None<br/></td><td>
Does not apply any collision detection.<br/></td></tr>
</table>

{% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip7"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej-tooltip id="tooltip7" content="JavaScript is the programming language of HTML and the Web." collision="fit">
    </ej-tooltip>

{% endhighlight %}