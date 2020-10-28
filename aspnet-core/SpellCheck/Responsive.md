---
title: SpellCheck - Responsive
description: How to set the spellcheck, responsive to screen resolutions
platform: aspnet-core
control: spellcheck
documentation: ug
keywords: Responsive, Responsive spellcheck dialog, Resize spellcheck dialog
---
# Responsive

The SpellCheck control has support for responsive behavior based on client browser’s width and height. To enable responsive, **IsResponsive** property should be true.

The following code example describes the above behavior.

{% highlight cshtml %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div><br />

<ej-spell-check id="SpellCheck" controls-to-validate="#TextArea" is-responsive="true">
        <e-dictionary-settings custom-dictionary-url="http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary" dictionary-url="http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords"></e-dictionary-settings>
</ej-spell-check>
{% endhighlight %}

The dialog of SpellCheck control is rendering based on the client browser’s width and height. Refer to the following code to render the SpellCheck dialog control with responsive.

{% highlight cshtml %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div><br />

<ej-spell-check id="SpellCheck" controls-to-validate="#TextArea" is-responsive="true">
        <e-dictionary-settings custom-dictionary-url="http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary" dictionary-url="http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords"></e-dictionary-settings>
</ej-spell-check>
<ej-button id="CheckButton" width="200px" height="25px" text="Spell check" click="checkErrors" />

<script type="text/javascript">
        function checkErrors() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.showInDialog();
        }
</script>
{% endhighlight %}

Mobile Rendering Screenshot:

![](Responsive_Images/Responsive_Image.png)