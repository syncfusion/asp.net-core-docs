---
title: Customization | FileExplorer | ASP.NET Core | Syncfusion
description: Customization support in FileExplorer
platform: Asp.Net Core
control: FileExplorer
documentation: UG
keywords: FileExplorer,  Syncfusion, Asp.Net Core FileExplorer, UG document, Customization
---
# Customization

## Dimension Customization

The dimension of the file explorer can be customized through the “[Height](http://help.syncfusion.com/js/api/ejfileexplorer#members:height)” and “[Width](http://help.syncfusion.com/js/api/ejfileexplorer#members:width)” property. The dimension can be set in percentage (e.g., width: “100 %”), so that the control inherits the width from the parent element.

In the view page, add file explorer with custom height and width.
    
{% highlight CSHTML %}

<ej-file-explorer id="custom" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" height="300px" width="900px">
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>

{% endhighlight %}
    
## Customizing the Navigation pane

The navigation pane contains the tree view element that displays all the folders from the filesystem in a hierarchical manner. This is useful for a quick navigation of any folder in the filesystem.

The visibility of the navigation pane can be controlled by the “[ShowNavigationPane](http://help.syncfusion.com/js/api/ejfileexplorer#members:shownavigationpane)” property. By disabling this property, you can hide the navigation pane from file explorer.

In the view page, add file explorer and specify the navigation pane as false.
    
{% highlight CSHTML %}

<ej-file-explorer id="custom" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")"show-navigation-pane="false">
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>
    
        
{% endhighlight %}
    
## Customizing the Content pane

The content pane is the main part of the file explorer UI that displays all the files and folders from the filesystem. The content pane supports the following types of layout views:

* Grid
* Tile
* Large Icons

The **grid view** displays the files and folders in a grid layout with the details in separate columns. By default, the grid view has four columns that displays the file name, type, date modified, and size of the file. For more details about grid view customization, refer [here](#customizing-the-grid-view).

The **tile view** display the files and folders like a small sized icons in the left side and file details in the right. It allows the thumbnails for the image files so that you can view the tiny preview of all image files.

The **large icons view** display the files and folders like a large sized icons with name. It allows the thumbnails for the image files so that you can view the tiny preview of all image files.

**Changing the Layout views**
You can change the layout of current view by the switcher that is displayed in the right-bottom of footer in the file explorer. By clicking the grid and large icons view buttons you can change the layout of current view.

![](Customization_images/Customization_img1.jpeg)

You can change the layout using the toolbar option. While clicking this tool, popup opens with different layout types. Here you can choose any options.

![](Customization_images/Customization_img2.jpeg)

Also the layout views can be changed through the “[Layout](http://help.syncfusion.com/js/api/ejfileexplorer#members:layout)” property. The [layoutChange](https://help.syncfusion.com/api/js/ejfileexplorer#events:layoutchange) event will be triggered whenever the layout view type is changed.
    
### Customizing the Grid view

By default, sorting is enabled in grid view of file explorer, it helps you to sort each columns in ascending or descending order by pressing the corresponding column header. The sorting functionality can be disabled by setting the “[AllowSorting](http://help.syncfusion.com/js/api/ejfileexplorer#members:gridsettings-allowsorting)” property to false.

The behavior of the columns can be customized through the “[Columns](http://help.syncfusion.com/js/api/ejfileexplorer#members:gridsettings-columns)” property.

In the view page, add file explorer with custom grid settings.

{% highlight CSHTML %}

<ej-file-explorer id="custom" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")">
    <e-file-grid-settings>
        <e-file-columns>
          <e-column-field header-text="Name" field="name" width="150"></e-column-field>    
          <e-column-field header-text="DateModified" field="dateModified" width="150"></e-column-field>
          <e-column-field header-text="size" field="size" width="90" text-align="Right"></e-column-field>
        </e-file-columns>
    </e-file-grid-settings>
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>

{% endhighlight %}
    
## Footer Customization

The footer displays the details of the currently selected files and folders, and it contains the switcher to change the layout view. The visibility of the footer can be customized by the “[ShowFooter](http://help.syncfusion.com/js/api/ejfileexplorer#members:showfooter)” property.

In the view page, add file explorer helper and hides the footer as shown in the following.

{% highlight CSHTML %}
<ej-file-explorer id="custom" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" show-footer="false">
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>
{% endhighlight %}
    
## Customize the Root Folder name in FileExplorer

You can set the alias name to the root folder of FileExplorer by using `rootFolderName` API. It is used to replace the actual root folder name in the FileExplorer UI. Refer to the below code to set the alias name for the root folder of FileExplorer.

{% highlight CSHTML %}
<ej-file-explorer id="root" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" root-folder-name="This PC">
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>
{% endhighlight %}