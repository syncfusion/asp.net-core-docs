# Documentation Guidelines

This section contains guidelines on naming files, sections, documents and other document elements.

> **NOTE**: Some of the items are marked as TODO which will be documented later.

## File naming Convention:

* All files should have `.md` extension.
* Do not use any special characters except hyphen in folder/file names 
* Separate words in file names should be hyphenated
* File names of the documents should have one or two-word names that describe the material covered in the document. 
* Phrase title and description in a way that users can determine what questions the text will answer, and material that will be addressed, without reading the content. This eases the time spent looking for answers, and improvises search/scanning, and possibly **SEO**.
* Provide titles and headers in the form of “Using foo” over “How to Foo.”

> For example, at the top section of each MD file,

> **Title :** Getting started with Chart widget for Syncfusion Essential JS 

> **Description :** How to create a chart, add series, enable tooltip and other functionalities.

## Adding a Document to left side Tree

* Each new markdown document should be added to the toc.html file, it is available at the root level of the repository

> **Syntax**: <li><a href="/[platform-name]/[control-name]/[topic]">[topic]</a></li>

> **Example**: <li><a href="/js/grid/multi-sorting-in-touch-device">Multi sorting in Touch device</a></li>


## Front Matter

Each markdown file should have the following information at the top of the document.

> **Syntax:**

> \---

> title: page title

> description: page description

> platform: platform name identifier

> control: control name

> documentation: ug/api

> keywords: Search engine will use these keyword to get the search results

> \---

> **Example:**

> \---

> title: Getting started with Chart widget for Syncfusion Essential JS

> description: How to create a chart, add series, enable tooltip and other functionalities

> platform: js

> control: chart

> documentation: ug

> keywords: ejchart, chart, chart widget, js chart

> \---

### Platform Name Identifiers

Please use the following platform names only in the front matter information

> Based on these platform names, we are showing search results, download and forum links

|    Platform       	  	|PlatformName Identifier|
|:-------------------------:|:---------------------:|
| Android           	  	| android				|
| ASP.NET           	  	| aspnet				|
| ASP.NET Classic   	  	| aspnet-classic		|
| ASP.NET MVC             	| ejmvc					|
| ASP.NET MVC Classic     	| aspnetmvc-claasic		|
| ASP.NET MVC Mobile      	| mobileaspnetmvc		|
| BigData			      	| bigdata				|
| Dashboard			      	| dashboard				|
| File Formats			  	| file-formats			|
| Install & Configuration 	| common				|
| iOS					  	| ios					|
| JavaScript			  	| js					|
| JavaScript Mobile		  	| mobilejs				|
| LightSwitch 			  	| lightswitch			|
| Orubase				  	| orubase				|
| Predictive Analytics		| predictive-analytics	|
| Report Server				| report-server			|
| Silverlight				| silverlight			|
| Universal Classic			| universal-classic		|
| UWP						| uwp					|
| Windows Forms				| windowsforms			|
| Windows Phone				| wp8					|
| WinRT						| winrt					|
| WPF						| wpf					|
| Xamarin					| xamarin				|

## Encoding
* Markdown files should be saved with "Encoding without UTF-8" encoding format <http://www.larshaendler.com/2015/01/20/remove-bom-with-notepad>

## Markdown Syntax Guideline
* Follow the syntax mentioned in this [link](http://kramdown.gettalong.org/syntax.html) for most of the elements. There are some elements which need special styling or additional settings to do. They are described in the following topics.

## General
* Do not bold the words unnecessarily.
* Use [inline code style](http://kramdown.gettalong.org/quickref.html#inline-code) wherever it is possible to highlight the keywords, variables or one line code examples that come within the paragraph.

### Cross-reference
* Link within the page (if you have a title with space, use hyphen (-))

>	**Syntax**: \[Link name](#title-name)

>	**Example**: \[How to best read this user guide] (#how-to-best-read-this-user-guide)

* Link to the other page within the same platform documentation (using relative path). Tooltip text is optional.

> **Syntax**: \[Link name](relative path "Tooltip text")

> **Example**: \[Barcode](/js/Barcode/Getting-Started "Barcode Getting Started")

### Table
* Use the [kramdown syntax](http://kramdown.gettalong.org/syntax.html#tables) for creating the tables.
* **Advanced tables**: If you want to create an advanced tables with row span or column span or with code examples, you can go with the standard html table syntax as described below.

> 1. start with `<table>` tag. Tag should be left indented and should have empty space in left side. 

> 2. Provide `TH` tag for table headers.

> 3. Code examples can be included within `<td> [code snippet] </td>`. Follow the same pattern like code examples. 

* Do not provide table captions.
* You can use the following markdown syntax if you want to use markdown syntax within the html tags.

> \{{'<MarkdownSyntax>' | markdownify }}

> **Example**:

> \{{'\[syncfusion](http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js)'| markdownify }}



### Image

* Make sure the image is not resized or blurred. 
* Caption is not necessary for all images except where you have displayed more than one image.

* Adding Image : General markdown [syntax](http://kramdown.gettalong.org/syntax.html#images) will work.

> **Syntax**: \!\[Alt text](imagepath)

> **Example**: \!\[Alt text](/path/to/img.jpg)

* Adding image with caption:

> **Syntax**: 
> \!\[Alt text](/path/to/img.jpg)
>
> Caption Text
> \{:.caption}

> **Example**: 
> \!\[Alt text](/path/to/img.jpg)
>
> Adding Filters in Grid
> {:.caption}

* Maximum width of the image should be 750 PX
* Maximum height of the image should be 550 PX
* Image format should be either .jpeg or .png format 
* Size of the image should not exceed  20 to 40 KB  
* If you are including the image to show an output of a code example, make sure the exact output can see the user also when he executes the same code example.

### Code Blocks
* Refer [this page](http://haisum.github.io/2014/11/07/jekyll-pygments-supported-highlighters/) for Code block syntax and supported languages.
* Align the code examples using following free formatters:
	[JS](http://jsbeautifier.org/) ,
	[HTML](http://www.freeformatter.com/html-formatter.html)
* Remove extra lines added within the code example.
* Make sure the given code block runs without any issues.
* JSRender template syntax can be rendered by using the following syntax :

> \{{"{{"}} code block here {{}}}}


### Bullet style
* Refer the syntax provided in the [Kramdown site](http://kramdown.gettalong.org/syntax.html#lists).
* Do not provide a line gap between the bullet points.

### Notes style

* To add the different type of predefined blockqoute use the follwing syntax. Since the title or relevant icon for this block of content will be added later, do not add the **"Title"**. 

**Information**
> **Syntax**: I> [Content]

> **Example**: I> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis volutpat, elit eget iaculis venenatis

**Notes**
> **Syntax**: N> [Content]

> **Example**: N> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis volutpat, elit eget iaculis venenatis

**Warning**
> **Syntax**: W> [Content]

> **Example**: N> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis volutpat, elit eget iaculis venenatis

**Errors**
> **Syntax**: E> [Content]

> **Example**: E> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis volutpat, elit eget iaculis venenatis

**Tips**
> **Syntax**: T> [Content]

> **Example**: T>  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis volutpat, elit eget iaculis venenatis

### Notes/Info/Warning/Error/Tips multiple paragraph style

> **Syntax**:
>
> N> [Line 1]
> 
> N> [Line 2]
> 
> N> [Line 3]
> 
> N> [Line 4]

> **Example**
> 
> N> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis volutpat, elit eget iaculis venenatis
> 
> N> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis volutpat, elit eget iaculis venenatis
> 
> N> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis volutpat, elit eget iaculis venenatis
> 
> N>
> 
> N> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis volutpat, elit eget iaculis venenatis

### See also

* See also section can be added at the bottom of the page using the below syntax 

> **Syntax**:
> {% seealso %}
>     [Content]
> {% endseealso %}


> **Example**: 
> {% seealso %}
>    [See the Cross Reference section](#Cross-reference)
> {% endseealso %}


### JS Playground integration
* Todo -> How to link the JS Playground link on top of the each code blocks?

### Keyboard shortcuts
* Enclose the each keys with `<kbd>` tag to display the keys with different styling. For ex, <kbd>Ctrl</kbd>+<kbd>A</kbd> .

### Product Release Version variable 
* To add the version number in the documentation, use the following variables that replace the corresponding release version number while publishing. So that, always your content will contains the latest release version number. 

| Variable Name     	           | Output         | Description            					                             |  
| ---------------------------------|:--------------:|:----------------------------------------------------------------------:|  
| {{ site.releaseversion }}        | 13.3.0.7       |Syncfusion Essential Studio version                                     |  
| {{ site.20esreleaseversion }}    | 13.3200.0.7    |Syncfusion Essential Studio assemblies version for .NET Framework 2.0   |  
| {{ site.35esreleaseversion }}    | 13.3350.0.7    |Syncfusion Essential Studio assemblies version for .NET Framework 3.5   |  
| {{ site.40esreleaseversion }}    | 13.3400.0.7    |Syncfusion Essential Studio assemblies version for .NET Framework 4.0   |  
| {{ site.45esreleaseversion }}    | 13.3450.0.7    |Syncfusion Essential Studio assemblies version for .NET Framework 4.5   |  
| {{ site.451esreleaseversion }}   | 13.3451.0.7    |Syncfusion Essential Studio assemblies version for .NET Framework 4.5.1 |  
| {{ site.46esreleaseversion }}    | 13.3460.0.7    |Syncfusion Essential Studio assemblies version for .NET Framework 4.5.1 | 
| {{ site.mvc3releaseversion }}    | 13.3300.0.7    |Syncfusion Essential Studio assemblies based on MVC Version 3.0         |  
| {{ site.mvc4releaseversion }}    | 13.3400.0.7    |Syncfusion Essential Studio assemblies based on MVC Version 4.0         |  
| {{ site.mvc5releaseversion }}    | 13.3500.0.7    |Syncfusion Essential Studio assemblies based on MVC Version 5.0         |  
| {{ site.mvc6releaseversion }}    | 13.3600.0.7    |Syncfusion Essential Studio assemblies based on MVC Version 5.0         |  


## Where can I see my updated changes?

All changes committed/merged to development branch will be automatically published in <http://115.249.201.211:9090> in the following timings.

* 5 AM IST
* 11 AM IST
* 1 PM IST
* 4 PM IST
* 7 PM IST

## API Reference Guideline

### Naming Standards
* Use the JS API naming standards mentioned in the following page - [API Naming Standards](https://syncfusion.atlassian.net/wiki/display/JS/API+Naming+Standards)

# See Also
[Style Guide](https://syncfusion.atlassian.net/wiki/display/SYNC/User+Guide+Documentation+-+Style+Guide)