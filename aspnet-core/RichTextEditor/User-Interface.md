---
layout: post
title: User Interface for the RichTextEditor widget for Syncfusion Essential ASP.NET Core
description: User Interface for RichTextEditor widget (toolbar, content area, and footer)
platform: aspnet-core
control: RTE
documentation: ug
keywords: RichTextEditor, Toolbar Configuration, Toolbar Items

---
# Toolbar Configuration

The editor’s toolbar contains a collection of tools such as bold, italic and text alignment buttons that are used to format the content.

However, in most integrations, it's desirable to change the toolbar configuration to suit needs. Fortunately, that's quite easy to do too.

<table>
<tr>
    <th> Property <br/><br/></th>
    <th> Description <br/><br/></th>
</tr>
<tr>
    <td> {{'[toolsList](http://help.syncfusion.com/js/api/ejrte#members:toolslist)'| markdownify }} <br/><br/></td>
    <td>  The toolsList option allows you to choose which tools appear on the toolbar, as well as the order and grouping of those items <br/><br/></td>
</tr>
<tr>
    <td> {{'[tools](http://help.syncfusion.com/js/api/ejrte#members:tools)'| markdownify }} <br/><br/></td>
    <td> The toolsList property is used to get the root group order and tools property is used to get the inner order of the corresponding groups displayed.<br/><br/></td>
</tr>
</table>

N> By default, when you tab from the textbox to the RTE, the first tools in the Toolbar of RTE will get focus not in the text area. <BR>
But we can able to focus the RTE text area by setting the tab index attribute as -1 to avoid the focus on RTE toolbar when we tab from textbox to RTE - {{'[Demo](http://jsplayground.syncfusion.com/Sync_1rlmhqbz)'| markdownify }}

## Toolbar Items

The following table lists the available buttons and dropdowns on the toolbar:

<table>
<tr>
<td>
Name<br/></td><td>
Summary<br/></td><td>
Initialization<br/></td><td>
isDefault?<br/></td></tr>
<tr>
<td>
Font <br/></td><td>
Applies font type, size, and color to the content<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() {" font"};<br/>List&lt;String> font = new List&lt;string>() { "fontName", "fontSize", "fontColor", "backgroundColor" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools font="font"></e-tools></ej-rte><br/></td><td>
No<br/></td></tr>
<tr>
<td>
Font style<br/></td><td>
Applies bold, italic, underline, and strikethrough formatting to the content<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() { " style"};<br/>List&lt;String> style = new List&lt;string>() { "bold", "italic", "underline", "strikethrough" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools styles="style"></e-tools></ej-rte><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Alignment<br/></td><td>
Align the content with left, center, and right margin.<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() { " alignment"};<br/>List&lt;String> alignment = new List&lt;string>() { "justifyLeft", "justifyCenter" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools alignment="alignment"></e-tools></ej-rte><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
List<br/></td><td>
Create a new list item (bulleted/numbered).<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() { "lists"};<br/>List&lt;String> lists = new List&lt;string>() { "unorderedList", "orderedList" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools lists="lists"></e-tools></ej-rte><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Indents<br/></td><td>
Allows to increase/decrease the indent level of the content.<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() { "indenting"};<br/>List&lt;String> indenting = new List&lt;string> { "outdent", "indent" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools indenting="indenting"></e-tools></ej-rte><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Undo/Redo Action<br/></td><td>
Allows to undo/redo the actions<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() {"doAction"};<br/>List&lt;String> doAction = new List&lt;string>() { "undo", "redo" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools do-action="doAction"></e-tools></ej-rte><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Hyperlink<br/></td><td>
Creates a hyperlink to a text or image to a specific location in the content.<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() {"links"};<br/>List&lt;String> links = new List&lt;string>() { "createLink", "removeLink" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools links="links"></e-tools></ej-rte><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Images<br/></td><td>
Inserts an image from an online source or local computer.<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() {"images"};<br/>List&lt;String> images = new List&lt;string>() { "image" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools images="images"></e-tools></ej-rte><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Media<br/></td><td>
Allows to embed a video into the document.<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() {"media"};<br/>List&lt;String> media = new List&lt;string>() { "video" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools media="media"></e-tools></ej-rte><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Table<br/></td><td>
Allows to add or modify Tables<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() {"tables"};<br/>List&lt;String> tables = new List&lt;string>() { "createTable", "addRowAbove", "addRowBelow", "addColumnLeft", "addColumnRight", "deleteRow", "deleteColumn", "deleteTable" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools tables="tables"></e-tools></ej-rte><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Casing<br/></td><td>
Change the case of selected text in the content<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() {"casing"};<br/>List&lt;String> casing = new List&lt;string>() { "upperCase", "lowerCase" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools casing="casing"></e-tools></ej-rte><br/></td><td>
no<br/></td></tr>
<tr>
<td>
Scripts<br/></td><td>
Makes the selected text as superscript (higher) or subscript (lower).<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() {"effects"};<br/>List&lt;String> effects = new List&lt;string>() { "superscript", "subscript" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools effects="effects"></e-tools></ej-rte><br/></td><td>
no<br/></td></tr>
<tr>
<td>
Format<br/></td><td>
Clears the formatting options like bold, italic, underline and more.<br/></td><td>
List&lt;String> toolsList = new List&lt;string>() {"formatStyle"};<br/>List&lt;String> formatStyle = new List&lt;string>() { "format" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools format-style="formatStyle"></e-tools></ej-rte><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Clipboard Actions<br/></td><td>
Controls the clipboard actions by applying specific action on the selected content.<br/></td><td>
List &lt;String> toolsList = new List&lt;string>() {"clipboard"};<br/>List&lt;String> clipboard = new List&lt;string>() { "cut", "copy", "paste" };<br/><ej-rte id="rteSample" tools-list="toolsList"><e-tools clipboard="clipboard"></e-tools></ej-rte><br/></td><td>
no<br/></td></tr>
</table>

## Rearrange Group

The toolbar contains groups, which are similar or related functionalities of toolbar items for efficient access. By default, the groups are arranged using the following order:

{% highlight CSHTML %}

List<String> toolsList = new List<string>() { "formatStyle", "font", "style", "effects", "alignment", "lists", "indenting", "clipboard", "doAction", "clear", "links", "images", "media", "tables", "casing", "customTool","view" };
	
{% endhighlight %}

The group can be rearranged on customization using the ToolsList property.

{% highlight CSHTML %}

@{
    List<String> toolsList = new List<string>() { "style", "lists", "doAction", "links", "images" };
    List<String> style = new List<string>() { "bold", "italic", "underline", "strikethrough" };
    List<String> lists = new List<string>() { "unorderedList", "orderedList" };
    List<String> doAction = new List<string>() { "undo", "redo" };
    List<String> links = new List<string>() { "createLink" };
    List<String> images = new List<string>() { "image" };

}

<ej-rte id="rteSample" tools-list="toolsList">
    <e-tools styles="style" lists="lists" do-action="doAction" links="links" images="images"></e-tools>
</ej-rte>

{% endhighlight %}

N> If you are not specifying any group in **ToolsList** property, the editor will create the toolbar with default group.

## Undo and Redo 

Undo and Redo buttons allow you to editing the text by disregard/cancel the recently made changes and restore it to previous state. It is a useful tool to restore the performed action which got changed by mistake. Up to 50 actions can be undo/redo in the editor by default. 

To undo and redo operations, do one of the following:

* Press the undo/redo button on the toolbar
* Press the <kbd> Ctrl </kbd> + <kbd> Z </kbd> ,  <kbd>Ctrl </kbd> + <kbd> Y </kbd> combination on the keyboard


{% highlight CSHTML %}

@{
    List<String> toolsList = new List<string>() { "doAction" };
    List<String> doAction = new List<string>() { "undo", "redo" };
}

<ej-rte id="rteSample" tools-list="toolsList">
    <e-tools do-action="doAction"></e-tools>
</ej-rte>

{% endhighlight %}

## Clipboard Operations

The editor provides support for the clipboard operations (cut, copy, and paste) in all text and images using the toolbar buttons and the keyboard shortcuts. Toolbar includes buttons through which the clipboard operations, such as Cut, Copy, and Paste can be accessed.

You can use the keyboard shortcuts to perform the clipboard operations.

* Cut - <kbd>CTRL</kbd> + <kbd>X</kbd>  
* Copy - <kbd>CTRL</kbd> + <kbd>C</kbd> 
* Paste - <kbd>CTRL</kbd> + <kbd>V</kbd> 

Some browsers block the clipboard access from JavaScript. If you want to use the Cut, Copy, and Paste buttons on the toolbar, you need to allow JavaScript to use the clipboard. If you don’t want to do this configuration, use CTRL+C, CTRL+X, and CTRL+V keyboard commands.

{% highlight CSHTML %}

@{
    List<String> toolsList = new List<string>() { "doAction" };
    List<String> clipboard = new List<string>() { "cut", "copy", "paste" };
}

<ej-rte id="rteSample" tools-list="toolsList">
    <e-tools clipboard="clipboard"></e-tools>
</ej-rte>

{% endhighlight %}