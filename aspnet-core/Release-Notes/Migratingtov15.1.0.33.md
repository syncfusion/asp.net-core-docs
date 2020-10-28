---
title: Essential Studio for ASP.NET Core 2017 Volume 1 Migration document
description: Essential Studio for ASP.NET Core 2017 Volume 1 Migration document
platform: aspnet-core
documentation: ug
keywords: migration, upgradation, upgrade-changes, 2017vol1-changes
---

# Common Changes

* As a part of NET Standard support, we are deprecating the existing packages and adding new packages as mentioned below. So the older packages are no longer shipped along with Essential Studio release.

<table class="params">
<tbody>
<tr>
<th>Deprecated packages</th>
<th>New packages</th>
</tr>
<tr>
<td>Syncfusion.Compression.AspNet.Core</td>
<td>Syncfusion.Compression.Portable</td>
</tr>
<tr>
<td>Syncfusion.DocIO.AspNet.Core</td>
<td>Syncfusion.DocIO.Portable</td>
</tr>
<tr>
<td>Syncfusion.OfficeChart.AspNet.Core</td>
<td>Syncfusion.OfficeChart.Portable</td>
</tr>
<tr>
<td>Syncfusion.Pdf.AspNet.Core</td>
<td>Syncfusion.Pdf.Portable</td>
</tr>
<tr>
<td>Syncfusion.Presentation.AspNet.Core</td>
<td>Syncfusion.Presentation.Portable</td>
</tr>
<tr>
<td>Syncfusion.XlsIO.AspNet.Core</td>
<td>Syncfusion.XlsIO.Portable</td>
</tr>
</tbody>
</table>

## DocIO

As a part of NET Standard support, we have made below changes.

* `Open(string filename)` method of `WordDocument` class has been removed, instead make use of `Open(Stream inputFileStream, FormatType outputFileFormatType)` method.
* `Save(string filename)` method of `WordDocument` class has been removed, instead make use of `Save(Stream OutputFileStream, FormatType outputFileFormatType)` method.
* `HtmlExportCssStyleSheetType`, and `HtmlExportCssStyleSheetFileName` properties of `SaveOptions` class has been removed and now support only inline & internal CSS in HTML export.
* `HTMLExportImagesFolder` property of `SaveOptions` class has been removed, instead make use of `ImageNodeVisited` event of `SaveOptions` to save the images in the specified path and use the saved path as image source during HTML export.
* In HTML import, loading image from absolute/web path has been removed. Instead make use of `ImageNodeVisited` event of `HTMLImportSettings` class to load image from the specified path.
* `IsValidXHTML(string html, XHTMLValidationType type)` and `IsValidXHTML(string html, XHTMLValidationType type, out string exceptionMessage)` methods of `WTextBody` class has been removed, instead make use of [this](http://www.syncfusion.com/downloads/support/directtrac/general/HTMLVA~1-1531659666.ZIP) extension in your application to check the XHTML 1.0 validation. Refer [this](http://www.syncfusion.com/downloads/support/directtrac/general/HTMLCO~1-516511074.ZIP) sample for more details.

## PDF

As a part of NET Standard support, we have made below changes.

* PdfDocument.Save(string filename) has been removed, instead make use of PdfDocument.Save(Stream outputFileStream) method.
* PdfLoadedDocument.Save(string filename) has been removed, instead make use of PdfLoadedDocument.Save(Stream outputFileStream) method.

## Presentation

As a part of NET Standard support, we have made below changes.

* `Open(string filename)` method in `Presentation` class has been removed, instead make use of `Open(Stream inputFileStream)` method.
* `Save(string filename)` method in `Presentation` class has been removed, instead make use of `Save(Stream outputFileStream)` method.

## XlsIO

As a part of NET Standard support, we have made below changes.

* Overloads with file path parameter in `Open` and `Save` methods has been removed. The same can be achieved with "stream" parameter.
* Scope of `SortedList<Tkey,Tvalue>` class is changed from public to internal.
* Scope of `PropertyInfoExtension` class and its extension methods are changed from public to internal.
* Namespace of `SortedList<Tkey,Tvalue>` class is changed from `System.Collections.Generic` to `Syncfusion.XlsIO.Implementation`
* Namespace of `ICloneable` interface is changed from `System` to Syncfusion.CompoundFile.XlsIO.
* Namespace for `RichTextReader` class is given as Syncfusion.XlsIO.
* `Syncfusion.Calculate` namespace is changed as `Syncfusion.XlsIO.Calculate`.
