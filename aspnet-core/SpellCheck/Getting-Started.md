---
title: Getting started | ASP.NET Core | Syncfusion
description: Rendering a basic SpellCheck
platform: aspnet-core
control: spellcheck
documentation: ug
keywords: SpellCheck, Getting Started, Service Reference, Content Checking
---
# Getting Started 

Refer the [Getting Started](/aspnet-core/getting-started) page of the Introduction part to know more about the basic system requirements and the steps to configure the Syncfusion components in an ASP.NET Core application.

Ensure once whether all the necessary dependency packages are included within the *bower.json* file as mentioned [here](/aspnet-core/getting-started#configure-syncfusion-components-in-aspnet-core-application), so that the required scripts and CSS to render the SpellCheck control gets installed and loads into the mentioned location (**wwwroot -> lib**) within your project.

Also, check whether the assembly dependency package **Syncfusion.EJ** added within the *project.json* file.

Now, refer the necessary scripts and CSS files into your *_Layout.cshtml* page from the **wwwroot -> lib -> syncfusion-javascript** folder.

{% highlight cshtml %}

<html>
<head>
    <environment names="Development">
        <link rel="stylesheet" href="~/lib/bootstrap/dist/css/bootstrap.css" />
        <link rel="stylesheet" href="~/css/site.css" />
        <link href="~/lib/syncfusion-javascript/Content/ej/web/default-theme/ej.web.all.min.css" rel="stylesheet" />
        <link href="~/lib/syncfusion-javascript/Content/ej/web/responsive-css/ej.responsive.css" rel="stylesheet" />
    </environment>
</head>
<body>

    <environment names="Development">
        <script src="~/lib/jquery/dist/jquery.js"></script>
        <script src="~/lib/bootstrap/dist/js/bootstrap.js"></script>
        <script src="~/js/site.js" asp-append-version="true"></script>
        <script src="~/lib/syncfusion-javascript/Scripts/ej/web/ej.web.all.min.js"></script>
    </environment>

</body>
</html>

{% endhighlight %}

It is necessary to define the following namespace within the *_viewImports.cshtml* page in order to make use of the SpellCheck component with the tag helper support.
 
{% highlight cshtml %}
 
    @using Syncfusion.JavaScript
    @addTagHelper "*, Syncfusion.EJ"
    
{% endhighlight %}

N> Script manager must be defined at the bottom of the *_Layout.cshtml* page.

Add the SpellCheck code within the View page as given below with proper field values.

{% highlight cshtml %}
<div>
    <ej-spell-check id="SpellCheck">
    </ej-spell-check>
</div>
{% endhighlight %}

Add the target element and map its id or class name to the SpellCheck control.

{% highlight cshtml %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div><br />

<ej-spell-check id="SpellCheck" controls-to-validate="#TextArea">
</ej-spell-check>

{% endhighlight %}

Adding the Service Reference

{% highlight cshtml %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div><br />

<ej-spell-check id="SpellCheck" controls-to-validate="#TextArea">
        <e-dictionary-settings custom-dictionary-url="http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary">
        </e-dictionary-settings>
</ej-spell-check>

{% endhighlight %}

Assign the service method (CheckWords) path reference to the property **DictionaryUrl**, which is mandatory to check the spelling of the word.

The CheckWords method will perform the splitting of target sentence into separate words and check each word is that an erroneous or not. If the word is erroneous fetching the possible suggestions for it and returns those details as a result.

Spell Checking the Content

To spell check the content of the target element, you need to add one button and calling any one of the SpellCheck method **showInDialog** or **validate** by clicking the button to highlight the error words.

The following code example depicts that checking the spelling of the target element through the "validate" method.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div><br />

<ej-spell-check id="SpellCheck" controls-to-validate="#TextArea">
        <e-dictionary-settings custom-dictionary-url="http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary" dictionary-url="http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords">
        </e-dictionary-settings>
</ej-spell-check>
<ej-button id="CheckButton" width="200px" height="25px" text="Spell check" click="checkErrors" />

<script type="text/javascript">
        function checkErrors() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.showInDialog();
        }
</script>

{% endhighlight %}