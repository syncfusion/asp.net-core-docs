---
layout: post
title: Import and Export in RichTextEditor widget for Syncfusion Essential ASP.NET Core
description: Import a word document into the RichTextEditor and Export the widget's content into a word or PDF file
platform: aspnet-core
control: RTE
documentation: ug
---

## Import 

Import feature provides support to import a word document into the editor `textarea`. To enable import option in the RTE tool bar,  `import` toolbar items needs to be added in RTE toolbar toolsList using `importExport` which adds the tool in the toolbar. In `ImportSettings` Url option, the server page for import is needed to be mapped. When you click the toolbar import icon, it opens a dialog to browse the select a word file. The selected word file will be imported into the editor `textarea`.

{% highlight CSHTML %}

@{
    List<String> toolsList = new List<string>() { "importExport" };
    List<String> ImportExport = new List<string>() { "import" };
}
<ej-rte id="rteSample" tools-list="toolsList" width="820px">
    <e-content-template>
        <div>
            The Rich Text Editor(RTE) control is an easy to render in client side. Customer easy to edit the contents
            and get the html content for the displayed content. A rich text editor control provides
            users with a toolbar that helps them to apply rich text formats to the text entered
            in the text area.
        </div>
    </e-content-template>
    <e-tools import-export="ImportExport"></e-tools>
    <e-import-settings url="//js.syncfusion.com/demos/ejServices/api/RTE/Import" />
</ej-rte>

{% endhighlight %}

![](ImportAndExport_images/import_images.png)

## Export 

Export feature provides support to export editor `textarea` content into word and PDF files. To enable Export option in the RTE tool bar,  `wordExport` , `pdfExport` toolbar items needs to be added in RTE toolbar toolsList using `importExport` which adds the tool in the toolbar. `ExportToWordSettings` consists of Url and FileName sub properties. In Url property, the server page for export to word is needed to be mapped and In FileName property, the name for the exported word file is given. `ExportToPdfSettings` consists of Url and FileName sub properties. In Url property, the server page for export to PDF is needed to be mapped and In FileName property, the name for the exported PDF file is given. When you click the toolbar pdfExport or wordExport icon, the contents of RTE are sent to the server. It performs XHTML Validation on the editor `textarea` content on the server. Once the XHTML validation and formatting is successful, it exports the content into a Word or PDF File.

{% highlight CSHTML %}

@{
    List<String> toolsList = new List<string>() { "importExport" };
    List<String> ImportExport = new List<string>() { "import", "wordExport", "pdfExport" };
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
    <e-tools import-export="ImportExport"></e-tools>
    <e-import-settings url="//js.syncfusion.com/demos/ejServices/api/RTE/Import" />
    <e-export-to-word-settings url="//js.syncfusion.com/demos/ejServices/api/RTE/WordExport" fileName="WordExport" />
    <e-export-to-pdf-settings url="//js.syncfusion.com/demos/ejServices/api/RTE/PdfExport" fileName="PdfExport" />
</ej-rte>

{% endhighlight %}

### Word Export
![](ImportAndExport_images/export_word_images.png)

### PDF Export
![](ImportAndExport_images/export_pdf_images.png)