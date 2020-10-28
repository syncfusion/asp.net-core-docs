---
layout: post
title: Exporting | TreeGrid | ASP.NET Core | Syncfusion
description: exporting
platform: aspnet-core
control: TreeGrid
documentation: ug
---
# Export

Exporting feature provides support to export TreeGrid content to excel and PDF files. To export the contents, the `ExcelExport` and `PdfExport` toolbar items must be added in the toolbar using the `ToolbarItems` property of `ToolbarSettings`. When you click, the toolbar exporting icons, it internally invokes the export public method of TreeGrid object to export.

The below code snippet explains the above behavior,

{% tabs %}
{% highlight CSHTML %}

<ej-tree-grid id="TreeGridControlExporting" child-mapping="SubTasks" tree-column-index="1" is-responsive="true" on-server-pdf-exporting="TreeGridControlExporting_ServerPdfExporting" on-server-excel-exporting="TreeGridControlExporting_ServerExcelExporting" >
            <e-tree-grid-columns>
                <e-tree-grid-column header-text="Task Id" field="TaskID" width="80" />
                <e-tree-grid-column header-text="Task Name" field="TaskName" />
                <e-tree-grid-column header-text="Start Date" field="StartDate" />
                <e-tree-grid-column header-text="End Date" field="EndDate" />
                <e-tree-grid-column header-text="Duration" field="Duration" />
            </e-tree-grid-columns>
            <e-tree-grid-edit-settings allow-deleting="false" ></e-tree-grid-edit-settings>
            <e-tree-grid-size-settings width="100%" height="450px"></e-tree-grid-size-settings>
            <e-tree-grid-toolbar-settings show-toolbar="true" toolbar-items="@(new List<string>() { "pdfExport","excelExport"})"></e-tree-grid-toolbar-settings>
</ej-tree-grid>

{% endhighlight %}

{% highlight c# %}

    public partial class TreeGridExporting : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            TaskDetailsCollection TaskCollection = new TaskDetailsCollection();
            this.TreeGridControlExporting.DataSource = TaskCollection.GetDataSource();
            this.TreeGridControlExporting.DataBind();
        }

        protected void TreeGridControlExporting_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.TreeGridEventArgs e)
        {
            PdfExport exp = new PdfExport();
            TreeGridExportSettings settings = new TreeGridExportSettings();
            settings.Theme = ExportTheme.FlatLime;
            exp.Export(this.TreeGridControlExporting.Model, (IEnumerable)this.TreeGridControlExporting.DataSource, settings, "Export");
        }

        protected void TreeGridControlExporting_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.TreeGridEventArgs e)
          {
            ExcelExport exp = new ExcelExport();
            TreeGridExportSettings settings = new TreeGridExportSettings();
            settings.Theme = ExportTheme.FlatLime;
            exp.Export(this.TreeGridControlExporting.Model, (IEnumerable)this.TreeGridControlExporting.DataSource, "Export.xlsx", ExcelVersion.Excel2010, new TreeGridExportSettings() { Theme = ExportTheme.BootstrapTheme });
          }
    }

{% endhighlight %}
{% endtabs %} 

The below screen shot shows TreeGrid with excel and PDF exporting enabled.
![](Export_images/Export_img1.png)

## Server dependencies
Export Helper functions are available in the Assembly `Syncfusion.EJ.Export`, which is available in the Essential Studio & Essential ASP.NET builds. The list of assemblies needed for TreeGrid Export as follows

* Syncfusion.EJ
* Syncfusion.EJ.Export
* Syncfusion.Linq.Base
* Syncfusion.Compression.Base
* Syncfusion.XlsIO.Base
* Syncfusion.PDF.Base

## Supported Export Types
Currently server helper function allows following two types of exporting.

* Excel
* PDF

## Multiple exporting
Multiple export is used for export more than one TreeGrid object in the same file. 

The following code example describes exporting multiple TreeGrid in PDF

{% tabs %} 
{% highlight CSHTML %}

    <div>
        <ej-tree-grid id="TreeGridControlExporting" child-mapping="SubTasks" tree-column-index="1" is-responsive="true" on-server-pdf-exporting="TreeGridControlExporting_ServerPdfExporting">
            <e-tree-grid-columns>
                <e-tree-grid-column header-text="Task Id" field="TaskID" width="80"/>
                <e-tree-grid-column header-text="Task Name" field="TaskName" />
                <e-tree-grid-column header-text="Start Date" field="StartDate" />
                <e-tree-grid-column header-text="End Date" field="EndDate" />
                <e-tree-grid-column header-text="Duration" field="Duration"/>
            </e-tree-grid-columns>
            <e-tree-grid-edit-settings allow-deleting="false"></e-tree-grid-edit-settings>
            <e-tree-grid-size-settings width="100%" height="250px"></e-tree-grid-size-settings>
            <e-tree-grid-toolbar-settings show-toolbar="true" toolbar-items="@(new List<string>() { "pdfExport"})"></e-tree-grid-toolbar-settings>
        </ej-tree-grid>
    </div>
   
     <div>
        <ej-tree-grid id="TreeGridControlDesign" child-mapping="SubTasks" tree-column-index="1" enable-resize="true">
            <e-tree-grid-columns>
                <e-tree-grid-column header-text="Task Id" field="TaskID" width="80"/>
                <e-tree-grid-column header-text="Task Name" field="TaskName" />
                <e-tree-grid-column header-text="Start Date" field="StartDate" />
                <e-tree-grid-column header-text="End Date" field="EndDate" />
                <e-tree-grid-column header-text="Duration" field="Duration"/>
            </e-tree-grid-columns>
            <e-tree-grid-edit-settings allow-deleting="false"></e-tree-grid-edit-settings>
            <e-tree-grid-size-settings width="100%" height="200px"></e-tree-grid-size-settings>
        </ej-tree-grid>
    </div>
     
     <div>
        <ej-tree-grid id="TreeGridControlImplementation" child-mapping="SubTasks" tree-column-index="1" enable-resize="true">
            <e-tree-grid-columns>
                <e-tree-grid-column header-text="Task Id" field="TaskID" width="80"/>
                <e-tree-grid-column header-text="Task Name" field="TaskName" />
                <e-tree-grid-column header-text="Start Date" field="StartDate" />
                <e-tree-grid-column header-text="End Date" field="EndDate" />
                <e-tree-grid-column header-text="Duration" field="Duration"/>
            </e-tree-grid-columns>
            <e-tree-grid-edit-settings allow-deleting="false"></e-tree-grid-edit-settings>
            <e-tree-grid-size-settings width="100%" height="250px"></e-tree-grid-size-settings>
        </ej-tree-grid>
    </div>

{% endhighlight %}

{% highlight c# %}

   public partial class TreeGridMultipleExporting : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            ExportTaskDetailsCollection TaskCollection = new ExportTaskDetailsCollection();
            this.TreeGridControlExporting.DataSource = TaskCollection.GetDataSource();
            this.TreeGridControlExporting.DataBind();
            this.TreeGridControlDesign.DataSource = TaskCollection.GetDesignPhaseDataSource();
            this.TreeGridControlDesign.DataBind();
            this.TreeGridControlImplementation.DataSource = TaskCollection.GetImplementationPhaseDataSource();
            this.TreeGridControlImplementation.DataBind();
        }

        protected void TreeGridControlExporting_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.TreeGridEventArgs e)
        {
            PdfExport exp = new PdfExport();
            PdfDocument document = exp.Export(this.TreeGridControlExporting.Model, (IEnumerable)this.TreeGridControlExporting.DataSource, new TreeGridExportSettings(){ Theme = ExportTheme.FlatLime},false,"Planning Phase");
            document = exp.Export(this.TreeGridControlDesign.Model, (IEnumerable)this.TreeGridControlDesign.DataSource, new TreeGridExportSettings() { Theme = ExportTheme.FlatLime }, "Export", document, false, "Design Phase");
            exp.Export(this.TreeGridControlImplementation.Model, (IEnumerable)this.TreeGridControlImplementation.DataSource, new TreeGridExportSettings() { Theme = ExportTheme.FlatLime }, "Export", document, true, "Implementation Phase");
        }
    }

{% endhighlight %}
{% endtabs %} 


## Export Theme
The TreeGrid export supports the below themes, 

* flat-azure
* flat-azure-dark
* flat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark
* bootstrap-theme

The desired theme should be passed as a parameter to the Export method and the code snippet for this as follows

{% highlight c# %}

        protected void TreeGridControlExporting_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.TreeGridEventArgs e)
        {
            PdfExport exp = new PdfExport();
            TreeGridExportSettings settings = new TreeGridExportSettings();
            settings.Theme = ExportTheme.FlatLime;
            exp.Export(this.TreeGridControlExporting.Model, (IEnumerable)this.TreeGridControlExporting.DataSource, settings, "Export");
        }

        protected void TreeGridControlExporting_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.TreeGridEventArgs e)
          {
            ExcelExport exp = new ExcelExport();
            TreeGridExportSettings settings = new TreeGridExportSettings();
            settings.Theme = ExportTheme.FlatLime;
            exp.Export(this.TreeGridControlExporting.Model, (IEnumerable)this.TreeGridControlExporting.DataSource, "Export.xlsx", ExcelVersion.Excel2010, new TreeGridExportSettings() { Theme = ExportTheme.BootstrapTheme });
          }

{% endhighlight %}