---
layout: post
title: Working with Lists related operation in RichTextEditor widget for Syncfusion Essential ASP.NET Core
description: Working with Lists related changes in RichTextEditor widget
platform: aspnet-core
control: RTE
documentation: ug
---

# Working with Lists

The editor provides tools to makes your content as list such as an ordered and unordered list.

## Create a Lists

By default, [Insert Lists](http://help.syncfusion.com/js/api/ejrte#members:tools-lists) tool is enabled in the editor’s toolbar.The editor’s have ordered and unordered list types.

{% highlight CSHTML %}

@{
    List<String> toolsList = new List<string>() { "lists" };
    List<String> lists = new List<string>() { "unorderedList", "orderedList" };
}
<ej-rte id="rteSample" tools-list="toolsList" width="820px">
    <e-content-template>
        <div>
            The Rich Text Editor(RTE) control is an easy to render in client side. Customer easy to edit the contents
            and get the HTML content for the displayed content. A rich text editor control provides
            users with a toolbar that helps them to apply rich text formats to the text entered
            in the text area.
        </div>
    </e-content-template>
    <e-tools lists="lists"></e-tools>
</ej-rte>

{% endhighlight %}

## Custom Lists

You can use [custom lists](http://help.syncfusion.com/js/api/ejrte#members:tools-customOrderedList) tools to insert lists with custom behaviors.You can create a list with related attributes (such as listImage, listStyle, title, name, and text) using the custom list tool.Ordered and Unordered list having own customize ways to insert a list into the editor’s content.

* [Insert a customOrderedList](#insert-a-customOrderedList)
* [Insert a customUnorderedList](#insert-a-customUnorderedList)  


### Insert a customOrderedList

you need to enable [customOrderedList](http://help.syncfusion.com/js/api/ejrte#members:tools-customOrderedList) tool on the editor’s toolbar.

The customOrderedList having below options for an ordered list customization.

<table>
<tr>
<th>
Option<br/><br/></th><th>
Summary<br/><br/></th></tr>
<tr><td>name</td><td>Specifies the name for customOrderedList item.</td></tr>
<tr><td>tooltip</td><td>Specifies the title for customOrderedList item.</td></tr>
<tr><td>CSS</td><td>Specifies the styles for customOrderedList item.</td></tr>
<tr><td>text</td><td>Specifies the text for customOrderedList item.</td></tr>
<tr><td>listStyle</td><td>Specifies the list style for customOrderedList item.</td></tr>
<tr><td>listImage</td><td>Specifies the image for customOrderedList item.</td></tr>
</table>

{% highlight CSHTML %}

@{
    List<String> toolsList = new List<string>() { "lists" };
    List<String> lists = new List<string>() { "orderedList" };
}
<ej-rte id="rteSample" tools-list="toolsList">
    <e-content-template>
        <p>
            The Rich Text Editor
            (RTE) control is an easy to render in client side. Customer easy to edit the contents
            and get the HTML content for the displayed content. A rich text editor control provides
            users with a toolbar that helps them to apply rich text formats to the text entered
            in the text area.
        </p>
    </e-content-template>
    <e-tools lists="lists">
        <e-custom-ordered-lists>
            <e-custom-ordered-list css="e-rte-toolbar-icon e-rte-listitems customOrder" list-style="lower-greek" name="orderInsert" tooltip="Custom Orderlist" text="Lower-Greek" />
        </e-custom-ordered-lists>
    </e-tools>
</ej-rte>

{% endhighlight %}

![](WorkingwithLists_images/ordered.png)

### Insert a customUnorderedList

you need to enable [customUnorderedList](http://help.syncfusion.com/js/api/ejrte#members:tools-customUnorderedList) tool on the editor’s toolbar.

The customUnorderedList having below options for an unordered list customization.

<table>
<tr>
<th>
Option<br/><br/></th><th>
Summary<br/><br/></th></tr>
<tr><td>name</td><td>Specifies the name for customUnorderedList item.</td></tr>
<tr><td>tooltip</td><td>Specifies the title for customUnorderedList item.</td></tr>
<tr><td>CSS</td><td>Specifies the styles for customUnorderedList item.</td></tr>
<tr><td>text</td><td>Specifies the text for customUnorderedList item.</td></tr>
<tr><td>listStyle</td><td>Specifies the list style for customUnorderedList item.</td></tr>
<tr><td>listImage</td><td>Specifies the image for customUnorderedList item.</td></tr>
</table>

{% highlight CSHTML %}

@{
    List<String> toolsList = new List<string>() { "lists" };
    List<String> lists = new List<string>() { "unorderedList" };
}
<ej-rte id="rteSample" tools-list="toolsList">
    <e-content-template>
        <p>
            The Rich Text Editor
            (RTE) control is an easy to render in client side. Customer easy to edit the contents
            and get the HTML content for the displayed content. A rich text editor control provides
            users with a toolbar that helps them to apply rich text formats to the text entered
            in the text area.
        </p>
    </e-content-template>
    <e-tools lists="lists">
            <e-custom-unordered-lists>
                <e-custom-unordered-list css="e-rte-toolbar-icon e-rte-unlistitems customUnOrder" list-image="url('../images/rte/smiley-gif.gif')" name="unOrderInsert" text="Smiley" tooltip="Custom UnOrderList" />
            </e-custom-unordered-lists>   
    </e-tools>
</ej-rte>

{% endhighlight %}

![](WorkingwithLists_images/unordered.png)