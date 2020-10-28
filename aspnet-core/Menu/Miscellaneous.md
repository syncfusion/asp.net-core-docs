---
layout: post
title: Miscellaneous | Menu | ASP.NET Core | Syncfusion
description: miscellaneous
platform: aspnet-core
control: Menu
documentation: ug
---

# Miscellaneous

## Height

Specifies the height of the root menu. You can customize the height of the Menu control by using Height property. 

1. You can specify the height of the Menu control using the below code as follows.

{% highlight CSHTML %}

	// You can specify the height of the Menu control in the CSHTML page as follows.
<ej-menu id="menu" height="50px">
    <e-menu-items>
        <e-menu-item url="" text="File">
            <e-menu-child-items>
                <e-menu-child-item text="New" url=""></e-menu-child-item>
                <e-menu-child-item text="Open" url=""></e-menu-child-item>
                <e-menu-child-item text="Save" url=""></e-menu-child-item>
                <e-menu-child-item text="PrintPreview" url=""></e-menu-child-item>
                <e-menu-child-item text="Print" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Edit" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Undo" url=""></e-menu-child-item>
                <e-menu-child-item text="Redo" url=""></e-menu-child-item>
                <e-menu-child-item text="Mobile MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Services" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="View" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Print Layout" url=""></e-menu-child-item>
                <e-menu-child-item text="Show ruler" url=""></e-menu-child-item>
                <e-menu-child-item text="Show spelling suggestion" url=""></e-menu-child-item>
                <e-menu-child-item text="Compact controls" url=""></e-menu-child-item>
                <e-menu-child-item text="Full screen" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Insert" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Image" url=""></e-menu-child-item>
                <e-menu-child-item text="Link" url=""></e-menu-child-item>
                <e-menu-child-item text="Comments" url=""></e-menu-child-item>
                <e-menu-child-item text="Header" url=""></e-menu-child-item>
                <e-menu-child-item text="Footer" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Help" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Docs Help" url=""></e-menu-child-item>
                <e-menu-child-item text="User Forums" url=""></e-menu-child-item>
                <e-menu-child-item text="Report an Issue" url=""></e-menu-child-item>
                <e-menu-child-item text="Keyboard Shortcuts" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
    </e-menu-items>
</ej-menu>

{% endhighlight %}   

## Width

Specifies the width of the main menu. You can customize the width of the Menu control by using Width property.

1. You can specify the width of the Menu control using helper as follows.

{% highlight CSHTML %}

// You can specify the width of the Menu control in the CSHTML page as follows.

<ej-menu id="menu" width="700px">
    <e-menu-items>
        <e-menu-item url="" text="File">
            <e-menu-child-items>
                <e-menu-child-item text="New" url=""></e-menu-child-item>
                <e-menu-child-item text="Open" url=""></e-menu-child-item>
                <e-menu-child-item text="Save" url=""></e-menu-child-item>
                <e-menu-child-item text="PrintPreview" url=""></e-menu-child-item>
                <e-menu-child-item text="Print" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Edit" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Undo" url=""></e-menu-child-item>
                <e-menu-child-item text="Redo" url=""></e-menu-child-item>
                <e-menu-child-item text="Mobile MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Services" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="View" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Print Layout" url=""></e-menu-child-item>
                <e-menu-child-item text="Show ruler" url=""></e-menu-child-item>
                <e-menu-child-item text="Show spelling suggestion" url=""></e-menu-child-item>
                <e-menu-child-item text="Compact controls" url=""></e-menu-child-item>
                <e-menu-child-item text="Full screen" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Insert" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Image" url=""></e-menu-child-item>
                <e-menu-child-item text="Link" url=""></e-menu-child-item>
                <e-menu-child-item text="Comments" url=""></e-menu-child-item>
                <e-menu-child-item text="Header" url=""></e-menu-child-item>
                <e-menu-child-item text="Footer" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Help" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Docs Help" url=""></e-menu-child-item>
                <e-menu-child-item text="User Forums" url=""></e-menu-child-item>
                <e-menu-child-item text="Report an Issue" url=""></e-menu-child-item>
                <e-menu-child-item text="Keyboard Shortcuts" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
    </e-menu-items>
</ej-menu>

{% endhighlight %}    

## Open on click

Specifies the sub menu items to be show or open only on click. It accepts the Boolean value. Its default value is false. If we set “OpenOnClick” property to true then the submenu items will open only on click. By default the submenu will open when we hover on menu items.

1. Add the following code in your view page to render the menu. 

{% highlight CSHTML %}

// Add the following code in the CSHTML page. 
<ej-menu id="menu" open-on-click="true" width="700px">
    <e-menu-items>
        <e-menu-item url="" text="File">
            <e-menu-child-items>
                <e-menu-child-item text="New" url=""></e-menu-child-item>
                <e-menu-child-item text="Open" url=""></e-menu-child-item>
                <e-menu-child-item text="Save" url=""></e-menu-child-item>
                <e-menu-child-item text="PrintPreview" url=""></e-menu-child-item>
                <e-menu-child-item text="Print" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Edit" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Undo" url=""></e-menu-child-item>
                <e-menu-child-item text="Redo" url=""></e-menu-child-item>
                <e-menu-child-item text="Mobile MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Services" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="View" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Print Layout" url=""></e-menu-child-item>
                <e-menu-child-item text="Show ruler" url=""></e-menu-child-item>
                <e-menu-child-item text="Show spelling suggestion" url=""></e-menu-child-item>
                <e-menu-child-item text="Compact controls" url=""></e-menu-child-item>
                <e-menu-child-item text="Full screen" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Insert" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Image" url=""></e-menu-child-item>
                <e-menu-child-item text="Link" url=""></e-menu-child-item>
                <e-menu-child-item text="Comments" url=""></e-menu-child-item>
                <e-menu-child-item text="Header" url=""></e-menu-child-item>
                <e-menu-child-item text="Footer" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Help" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Docs Help" url=""></e-menu-child-item>
                <e-menu-child-item text="User Forums" url=""></e-menu-child-item>
                <e-menu-child-item text="Report an Issue" url=""></e-menu-child-item>
                <e-menu-child-item text="Keyboard Shortcuts" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
    </e-menu-items>
</ej-menu>

{% endhighlight  %}

Output screenshot for the above code example is as follows.

![](Miscellaneous_images/Miscellaneous_img1.png)

Sub menu items to open on click
{:.caption}

## Animation

Animation type is used to enable or disable the Animation when hover or click on menu items. Its value type is string. It accepts two values such as “none” and “default”. Support to disable the Animation Type when hover or click on menu items is none. Support to enable the Animation Type when hover or click on menu items is default. 

1. Add the following code in your view page to render the menu. 

{% highlight CSHTML %}

// Add the following code in the CSHTML page. 

<ej-menu id="menu" animation-type="@AnimationType.Default" width="700px">
    <e-menu-items>
        <e-menu-item url="" text="File">
            <e-menu-child-items>
                <e-menu-child-item text="New" url=""></e-menu-child-item>
                <e-menu-child-item text="Open" url=""></e-menu-child-item>
                <e-menu-child-item text="Save" url=""></e-menu-child-item>
                <e-menu-child-item text="PrintPreview" url=""></e-menu-child-item>
                <e-menu-child-item text="Print" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Edit" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Undo" url=""></e-menu-child-item>
                <e-menu-child-item text="Redo" url=""></e-menu-child-item>
                <e-menu-child-item text="Mobile MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Services" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="View" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Print Layout" url=""></e-menu-child-item>
                <e-menu-child-item text="Show ruler" url=""></e-menu-child-item>
                <e-menu-child-item text="Show spelling suggestion" url=""></e-menu-child-item>
                <e-menu-child-item text="Compact controls" url=""></e-menu-child-item>
                <e-menu-child-item text="Full screen" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Insert" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Image" url=""></e-menu-child-item>
                <e-menu-child-item text="Link" url=""></e-menu-child-item>
                <e-menu-child-item text="Comments" url=""></e-menu-child-item>
                <e-menu-child-item text="Header" url=""></e-menu-child-item>
                <e-menu-child-item text="Footer" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Help" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Docs Help" url=""></e-menu-child-item>
                <e-menu-child-item text="User Forums" url=""></e-menu-child-item>
                <e-menu-child-item text="Report an Issue" url=""></e-menu-child-item>
                <e-menu-child-item text="Keyboard Shortcuts" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
    </e-menu-items>
</ej-menu>

{% endhighlight  %}

Output screenshot for the above code sample is as follows.

![](Miscellaneous_images/Miscellaneous_img2.png)

Animation
{:.caption}

## Title text

Specifies the title to the responsive menu. You can provide title to the Menu control by using TitleText property. 

1. You can specify the title of the Menu control using helper as follows.

{% highlight CSHTML %}

// You can specify the title of the Menu control in the CSHTML page as follows.

<ej-menu id="menu" title-text="Title of the Menu">
    <e-menu-items>
        <e-menu-item url="" text="File">
            <e-menu-child-items>
                <e-menu-child-item text="New" url=""></e-menu-child-item>
                <e-menu-child-item text="Open" url=""></e-menu-child-item>
                <e-menu-child-item text="Save" url=""></e-menu-child-item>
                <e-menu-child-item text="PrintPreview" url=""></e-menu-child-item>
                <e-menu-child-item text="Print" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Edit" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Undo" url=""></e-menu-child-item>
                <e-menu-child-item text="Redo" url=""></e-menu-child-item>
                <e-menu-child-item text="Mobile MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Services" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="View" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Print Layout" url=""></e-menu-child-item>
                <e-menu-child-item text="Show ruler" url=""></e-menu-child-item>
                <e-menu-child-item text="Show spelling suggestion" url=""></e-menu-child-item>
                <e-menu-child-item text="Compact controls" url=""></e-menu-child-item>
                <e-menu-child-item text="Full screen" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Insert" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Image" url=""></e-menu-child-item>
                <e-menu-child-item text="Link" url=""></e-menu-child-item>
                <e-menu-child-item text="Comments" url=""></e-menu-child-item>
                <e-menu-child-item text="Header" url=""></e-menu-child-item>
                <e-menu-child-item text="Footer" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Help" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Docs Help" url=""></e-menu-child-item>
                <e-menu-child-item text="User Forums" url=""></e-menu-child-item>
                <e-menu-child-item text="Report an Issue" url=""></e-menu-child-item>
                <e-menu-child-item text="Keyboard Shortcuts" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
    </e-menu-items>
</ej-menu>

{% endhighlight  %}

The following screenshot displays the output of the above code.

![](Miscellaneous_images/Miscellaneous_img3.png)

Title text for Responsive Layout
{:.caption}

## Show root level arrows

Specifies the main menu item arrows to display only when it contains child menu items. You can use “ShowRootLevelArrows” property to display the arrows of main menu items only when it contains child menu items. This property accepts Boolean value. Its default value is true. 

1. Add the following code in your view page to render the menu with root level arrows

{% highlight CSHTML %}

<ej-menu id="keyboard" width="60%" show-sub-level-arrows="false">
    <e-menu-items>
        <e-menu-item id="Products" text="Products">
            <e-menu-child-items>
                <e-menu-child-item text="ASP.NET" url=""></e-menu-child-item>
                <e-menu-child-item text="ASP.NET MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Mobile MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Silverlight" url=""></e-menu-child-item>
           </e-menu-child-items>
            <e-menu-child-items>
                <e-menu-child-item text="ASP.NET" url=""></e-menu-child-item>
                <e-menu-child-item text="ASP.NET MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Mobile MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Silverlight" url=""></e-menu-child-item>
                <e-menu-child-item text="Windows Forms" url=""></e-menu-child-item>
                <e-menu-child-item text="Windows Phone" url=""></e-menu-child-item>
                <e-menu-child-item text="" url="ASP.NET MVC"></e-menu-child-item>
                <e-menu-child-item text="" url="ASP.NET"></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Support" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Direct-Trac Support" url=""></e-menu-child-item>
                <e-menu-child-item text="Community Forums" url=""></e-menu-child-item>
                <e-menu-child-item text="Knowledge Base" url=""></e-menu-child-item>
                <e-menu-child-item text="Online Documentation" url=""></e-menu-child-item>
                <e-menu-child-item text="Services" url=""></e-menu-child-item>
            </e-menu-child-items>
            <e-menu-child-items>
                <e-menu-child-item text="Consulting" url=""></e-menu-child-item>
                <e-menu-child-item text="Training" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Purchase" id="Purchase" url="">
        </e-menu-item>
        <e-menu-item text="Downloads" id="Downloads" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Evaluation" url=""></e-menu-child-item>
                <e-menu-child-item text="Free E-Books" url=""></e-menu-child-item>
                <e-menu-child-item text="Metro Studio" url=""></e-menu-child-item>
                <e-menu-child-item text="C" url=""></e-menu-child-item>
                <e-menu-child-item text="Version History" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item id="Resources" Text="Resources" Url="">
            <e-menu-child-items>
                <e-menu-child-item text="E-Books" url=""></e-menu-child-item>
                <e-menu-child-item text="White Papers" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
    </e-menu-items>
</ej-menu>

{% endhighlight %}

The following screenshot displays the output of the above code.

![](Miscellaneous_images/Miscellaneous_img4.png)

Show root level arrows
{:.caption}

## Show sub level arrows

Specifies the sub menu items arrows to display only when it contains child menu items. You can use “ShowSubLevelArrows” property to show the arrows of sub menu items only when it contains child menu items. This property accepts Boolean value. Its default value is true. 

1. Add the following code in your view page to render the menu with sub level arrows

{% highlight CSHTML %}

// Add the following code in the CSHTML page.

<ej-menu id="keyboard" width="60%" show-sub-level-arrows="false">
    <e-menu-items>
        <e-menu-item id="Products" text="Products">
            <e-menu-child-items>
                <e-menu-child-item text="ASP.NET" url=""></e-menu-child-item>
                <e-menu-child-item text="ASP.NET MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Mobile MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Silverlight" url=""></e-menu-child-item>
           </e-menu-child-items>
            <e-menu-child-items>
                <e-menu-child-item text="ASP.NET" url=""></e-menu-child-item>
                <e-menu-child-item text="ASP.NET MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Mobile MVC" url=""></e-menu-child-item>
                <e-menu-child-item text="Silverlight" url=""></e-menu-child-item>
                <e-menu-child-item text="Windows Forms" url=""></e-menu-child-item>
                <e-menu-child-item text="Windows Phone" url=""></e-menu-child-item>
                <e-menu-child-item text="" url="ASP.NET MVC"></e-menu-child-item>
                <e-menu-child-item text="" url="ASP.NET"></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Support" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Direct-Trac Support" url=""></e-menu-child-item>
                <e-menu-child-item text="Community Forums" url=""></e-menu-child-item>
                <e-menu-child-item text="Knowledge Base" url=""></e-menu-child-item>
                <e-menu-child-item text="Online Documentation" url=""></e-menu-child-item>
                <e-menu-child-item text="Services" url=""></e-menu-child-item>
            </e-menu-child-items>
            <e-menu-child-items>
                <e-menu-child-item text="Consulting" url=""></e-menu-child-item>
                <e-menu-child-item text="Training" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item text="Purchase" id="Purchase" url="">
        </e-menu-item>
        <e-menu-item text="Downloads" id="Downloads" url="">
            <e-menu-child-items>
                <e-menu-child-item text="Evaluation" url=""></e-menu-child-item>
                <e-menu-child-item text="Free E-Books" url=""></e-menu-child-item>
                <e-menu-child-item text="Metro Studio" url=""></e-menu-child-item>
                <e-menu-child-item text="C" url=""></e-menu-child-item>
                <e-menu-child-item text="Version History" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
        <e-menu-item id="Resources" Text="Resources" Url="">
            <e-menu-child-items>
                <e-menu-child-item text="E-Books" url=""></e-menu-child-item>
                <e-menu-child-item text="White Papers" url=""></e-menu-child-item>
            </e-menu-child-items>
        </e-menu-item>
    </e-menu-items>
</ej-menu>

{% endhighlight %}

The following screenshot displays the output of the above code.

![](Miscellaneous_images/Miscellaneous_img5.png)

Show sub level arrows
{:.caption}