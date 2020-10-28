---
layout: post
title: Getting-Started
description: getting started
platform: aspnet-core
control: RichTextEditor
documentation: ug
---
# Getting Started

This section explains the step-by-step instructions to create RichTextEditor in an ASP.NET Core application.

## Create your first RichTextEditor in ASP.NET Core.

1.  Create Syncfusion ASP.NET Core application. You can refer [ASP.NET Core Getting Started](https://help.syncfusion.com/aspnet-core/getting-started) documentation to initially configure the common specifications.

2.Add RichTextEditor control by using the below code.

	{% highlight CSHTML %}
	
	 /*ej-Tag Helper code to render RTE*/

		<ej-rte id="RteTaghelper" width="820px"></ej-rte>
		   
	{% endhighlight %}

	{% highlight Razor %}
	
	 /*Razor code to render RTE*/
		
		@{Html.EJ().RTE("rteSample").Width("820px").Render();}
			
	{% endhighlight %}



+N> To render the RichTextEditor Control you can use either Razor or Tag helper code as given in the above code snippet.


## Toolbar-Configuration

You can configure the toolbar with the tools as your application requires.

	{% highlight CSHTML %}

		 /*ej-Tag Helper code to render RTE*/

		@{
		   List<String> toolsList = new List<string>() { "style", "lists", "doAction", "links", "images"};
		   List<String> style = new List<string>() { "bold", "italic", "underline", "strikethrough" };
		   List<String> lists = new List<string>() { "unorderedList", "orderedList" };
		   List<String> doAction = new List<string>() { "undo", "redo" };
		   List<String> links = new List<string>() { "createLink", "removeLink" };
		   List<String> images = new List<string>() { "image" };               
		 }

		<ej-rte id="rteSample" tools-list="toolsList" width="820px">
				<e-tools  styles="style" lists="lists" do-action="doAction" links="links" images="images"></e-tools>              
		</ej-rte>
			
	{% endhighlight %}
	
	{% highlight Razor %}
	
		/*Razor code to render RTE*/

		@{
			List<String> toolsList = new List<string>() { "style", "lists", "doAction", "links", "images" };
			List<String> style = new List<string>() { "bold", "italic", "underline", "strikethrough" };
			List<String> lists = new List<string>() { "unorderedList", "orderedList" };
			List<String> doAction = new List<string>() { "undo", "redo" };
			List<String> links = new List<string>() { "createLink", "removeLink"  };
			List<String> images = new List<string>() { "image" };
		}
		@{Html.EJ().RTE("rteSample").Width("820px").ToolsList(toolsList).Tools(tool => tool.Styles(style).Lists(lists).DoAction(doAction).Links(links).Images(images)).Render();}

	{% endhighlight %}
	
![](Getting-Started-images/Toolbar.png)


## Setting and Getting Content

You can set the content of the editor as follows.

	{% highlight CSHTML %}
	
		/*ej-Tag Helper code to render RTE*/

		<ej-rte id="RteTaghelper" width="820px"> 
			<e-content-template><div>
				The Rich Text Editor (RTE) control is an easy to render in client side.
				Customer easy to edit the contents and get the HTML content for the displayed content.
				A rich text editor control provides users with a toolbar that helps them to apply rich text formats to the text entered in the text area.
			</div></e-content-template>  
		</ej-rte>

	{% endhighlight %}
	
	{% highlight Razor %}
	
		/*Razor code to render RTE*/

		@{Html.EJ().RTE("rteSample").Width("820px").ContentTemplate(@<div>
			The Rich Text Editor (RTE) control is an easy to render in client side.
			Customer easy to edit the contents and get the HTML content for the displayed content.
			A rich text editor control provides users with a toolbar that helps them to apply rich text formats to the text entered in the text area.
		</div>).Render();}

	{% endhighlight %}
	

To retrieve the editor contents using Value property in Post Back action,

{% highlight CSHTML %}

[HttpPost]
[ValidateInput(false)]
public ActionResult RichTextEditorFeatures(string rteSample)
{
    ViewBag.data = rteSample;
    return View();
}

{% endhighlight %}


