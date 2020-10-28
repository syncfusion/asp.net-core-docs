---
title: SpellCheck - Customization
description: SpellCheck Customization
platform: aspnet-core
control: spellcheck
documentation: ug
keywords: customization, spellcheck customization, misspell word appearance, restrict suggestion count
---
# SpellCheck Customization

The SpellCheck control provides option to customize the following scenarios.

* Misspell Word Appearance
* Restrict Suggestion Count
    
## Misspell Word Appearance

The SpellCheck control provide the option **MisspellWordCss** to display the error word in user defined style. By default, displays the error words with the red underline. 

The following code example depicts the way to customize the error word highlight (displaying error word with red color font and lightblue background).

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
        The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div><br />

<ej-spell-check id="SpellCheck" controls-to-validate="#TextArea" misspell-word-css="highlight">
        <e-dictionary-settings custom-dictionary-url="http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary" dictionary-url="http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords"></e-dictionary-settings>
</ej-spell-check>
<ej-button id="CheckButton" width="200px" height="25px" text="Spell check using dialog" click="checkErrors" />

<script>
        function checkErrors() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.showInDialog();
        }
</script>

<style>
        .highlight {
            background-color: lightblue;
            color: red;
        }
</style>

{% endhighlight %}

## Restrict Suggestion Count

The SpellCheck control provide the option **MaxSuggestionCount** to restrict the number of items to be displayed in the suggestion list.

The following code example describes the way to control the suggestion count.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
        The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div><br />

<ej-spell-check id="SpellCheck" controls-to-validate="#TextArea" max-suggestion-count="2">
        <e-dictionary-settings custom-dictionary-url="http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary" dictionary-url="http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords">
        </e-dictionary-settings>
</ej-spell-check>
<ej-button id="CheckButton" width="200px" height="25px" text="Spell check" click="checkErrors" />

<script>
        function checkErrors() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.validate();
        }
</script>

{% endhighlight %}