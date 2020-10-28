---
layout: post
title: Working with content selection in RichTextEditor widget for Syncfusion Essential ASP.NET Core
description: Working with content selection in RichTextEditor widget
platform: aspnet-core
control: RTE
documentation: ug
---
# Working with Selection

The editor control provides option to select the all content and in addition to selection of a particular range of content. 

## Select All 

The [selectAll](http://help.syncfusion.com/js/api/ejrte#methods:selectall) method enables you to select the entire content including images in the editor by programmatically.

N> the selection highlight is invisible if the editor does not have focus. So, if you want to call the selectAll method, focus the editor before.

{% highlight CSHTML %}

<ej-rte id="rteSample" width="820px" select="selectAll">
    <e-content-template>
        <div>
            The Rich Text Editor (RTE) control is an easy to render in client side.
            Customer easy to edit the contents and get the HTML content for the displayed content.
            A rich text editor control provides users with a toolbar that helps them to apply rich text formats to the text entered in the text area.
        </div>
    </e-content-template> 
</ej-rte>

<script>
    function selectAll() {
        var editor = $("#rteSample").ejRTE("instance");
        editor.selectAll();
    }
</script>

{% endhighlight %}

## Select a Range 

You can programmatically select a range of content in the editor using the [selectRange](http://help.syncfusion.com/js/api/ejrte#methods:selectrange) method.  To select a range, create a range object with desired offset position and pass it as arguments to selectRange method. The range object is created from [createRange](http://help.syncfusion.com/js/api/ejrte#methods:createrange) method. 

{% highlight CSHTML %}

<ej-rte id="rteSample" width="820px">
    <e-content-template>
        <div>
            <ul>
                <li>Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</li>
                <li>Aliquam tincidunt mauris eu risus.</li>
                <li>Vestibulum auctor dapibus neque.</li>
            </ul>
        </div>
    </e-content-template> 
</ej-rte>
<ej-button id="button" text="Select" click="select">

<script>
    function select() {
        var editor = $("#rteSample").ejRTE("instance");
        range = editor.createRange();
        var liTag = $(editor.getDocument().body).find("li");
        if (!editor._isIE8()) {
            range.setStart(liTag[1], 0);
            range.setEnd(liTag[2], 1);
        }
        else {
            range = editor.getDocument().body.createTextRange()
            range.moveToElementText(liTag[2]);
        }
        editor.selectRange(range);
    }
</script>

{% endhighlight %}

## Get Selection

The following public methods helps you to retrieve the selected content from the editor:

* [getText](http://help.syncfusion.com/js/api/ejrte#methods:gettext) method is used to get the currently selected content as raw text.
* [getSelectedHtml](http://help.syncfusion.com/js/api/ejrte#methods:getselectedhtml) method is used to get the HTML source of currently selected content.

{% highlight CSHTML %}

<ej-rte id="rteSample" width="820px">
    <e-content-template>
        <div>
            <ul>
                <li>Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</li>
                <li>Aliquam tincidunt mauris eu risus.</li>
                <li>Vestibulum auctor dapibus neque.</li>
            </ul>
        </div>
    </e-content-template> 
</ej-rte>
<ej-button id="button" text="Select" click="select">

<script>
    function select() {
        var editor = $("#rteSample").ejRTE("instance");
        var selectedText = editor.getText();
        var selectedHtml = editor.getSelectedHtml();
        alert(selectedHtml);
    }
</script>

{% endhighlight %}