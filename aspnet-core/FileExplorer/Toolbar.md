---
title: Toolbar | FileExplorer | ASP.NET Core | Syncfusion
description: Toolbar support in FileExplorer control
platform: Asp.Net Core
control: FileExplorer
documentation: UG
keywords: FileExplorer,  Syncfusion, Asp.Net Core FileExplorer, UG document, Toolbar
---
# Toolbar

The toolbar element have number of tools, and each tool can be configured.

## Toolbar items

The toolbar has the list of items to perform various operations and it is grouped into some categorizes.

 
The following table explains the functionality of each toolbar item:

<table>
<tr>
<td>
Tool name
</td>
<td>
Description
</td>
</tr>
<tr>
<td>
Layout
</td>
<td>
In file explorer, files have been displayed in 3 types of views “Grid”, “Tile”, and “Large Icons”. Using this tool, you can change the view type from one to another.

</td>
</tr>
<tr>
<td>
NewFolder <br/><br/></td>
<td>
It creates a new folder on the current directory.<br/><br/>While click on the NewFolder item, the dialog displays to get the folder name. Based on the user input, FileExplorer creates new folder on the current directory.
Also {{'[createFolder](https://help.syncfusion.com/api/js/ejfileexplorer#events:createfolder)'| markdownify}} event will be triggered when new folder is created successfully in the file system.<br/><br/><br/><br/></td></tr>
</tr>
<tr>
<td>
Back <br/><br/></td>
<td>
It navigates to the previous directory from the user history. When the backward history is not available, it will be in disabled state.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Forward <br/><br/></td>
<td>
It navigates to the next directory from the user history. When the forward history is not available, it will be in disable state.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Upward <br/><br/></td>
<td>
It navigates to the parent directory of the current folder.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Address bar<br/><br/></td>
<td>
The “address bar” is the textbox that displays the path of the current directory, as a series of its parent directory will be separated by slash (“/”).<br/><br/>And the address bar is an editable area, where you can enter any directory’s path for a quick navigation.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Refresh <br/><br/></td>
<td>
It refreshes the current directory.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Upload <br/><br/></td>
<td>
It uploads a file or list of files into the current directory.<br/><br/>And you can customize the upload configurations, for details check {{'[here](https://help.syncfusion.com/js/fileexplorer/toolbar#customizing-the-upload-functionality)'| markdownify }}.
<br/><br/><br/><br/></td></tr>
</tr>
<tr>
<td>
Delete <br/><br/></td>
<td>
It deletes the currently selected file or folder. The delete icon will be in enable state, when you select any file or folder.<br/><br/>If you select multiple files, it deletes all the selected items.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Rename <br/><br/></td>
<td>
This is used to rename the currently selected file or folder. The rename icon will be in enable state, when you select any file or folder.<br/><br/>Even if you select multiple files, it renames the last selected file only.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Download <br/><br/></td>
<td>
It downloads the selected files. The download icon is enable state if you select any file or folder.<br/><br/>
The {{'[beforeDownload](https://help.syncfusion.com/api/js/ejfileexplorer#events:beforedownload)'| markdownify}} event will be triggered before the files are downloaded.
<br/><br/>If you select multiple files, it downloads all the files in a zip format.<br/><br/><br/><br/></td></tr>
</tr>
<tr>
<td>
Cut <br/><br/></td>
<td>
It makes the copy of the selected files or folders into the clipboard. When the user paste the files in any location, the files are removed from the source location.
The {{'[cut](https://help.syncfusion.com/api/js/ejfileexplorer#events:cut)'| markdownify}} event will be triggered when files or folders are removed from the source.<br/><br/><br/><br/></td></tr>
</tr>
<tr>
<td>
Copy <br/><br/></td>
<td>
It makes the copy of the selected files or folders into the clipboard. When the user paste the files, the copy of the files are pasted in the target location.
The {{'[copy](https://help.syncfusion.com/api/js/ejfileexplorer#events:copy)'| markdownify}} event will be triggered when file or folder is copied.<br/><br/><br/><br/></td></tr>
</tr>
<tr>
<td>
Paste <br/><br/></td>
<td>
It pastes the files from the clipboard into the currently selected folder. <br/><br/>Note: Only when the files are copied into the clipboard it is enabled.
The {{'[paste](https://help.syncfusion.com/api/js/ejfileexplorer#events:paste)'| markdownify}} event will be triggered when file or folder is pasted.<br/><br/><br/><br/></td></tr>
</tr>
<tr>
<td>
Details <br/><br/></td>
<td>
It displays the details of the currently selected file or folder.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Search bar<br/><br/></td>
<td>
The Search bar is the textbox that is used to search the files from the current directory. It list the files based on the user search.<br/><br/>The search behavior of the “search bar” can be customized. For more details, check <br/>{{'[here](#_Search_bar)'| markdownify }}.<br/><br/></td>
</tr>
<tr>
<td>
Sort by <br/><br/></td><td>
It is used to sort the files from the current directory. The sorting can be done based on the columns available from grid, in both ascending and descending order.<br/><br/><br/><br/></td>
</tr>
</table>

## Toolbar visibility

The visibility of the toolbar can be customized through the “[ShowToolbar](http://help.syncfusion.com/js/api/ejfileexplorer#members:showtoolbar)” property. By disabling this property you can remove the toolbar from the file explorer. Also you can remove the particular toolbar item by using [removeToolbarItem](https://help.syncfusion.com/api/js/ejfileexplorer#methods:removetoolbaritem) method.

In the view page, add FileExplorer and specify “ShowToolbar” as false.

{% highlight CSHTML %}

<ej-file-explorer id="default" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" width="100%" is-responsive="true" show-toolbar="false" >
<e-file-ajax-settings>
    <e-download url="/FileExplorer/Download{0}"></e-download>
    <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
    <e-upload url="/FileExplorer/Upload{0}"></e-upload>
</e-file-ajax-settings>
</ej-file-explorer>

{% endhighlight %} 



## Toolbar configuration

From the list of available items, you can configure and group your required toolbar items only through the “[Tools](http://help.syncfusion.com/js/api/ejfileexplorer#members:tools)” property. And also, you can arrange the toolbar items by the “[ToolsList](http://help.syncfusion.com/js/api/ejfileexplorer#members:toolslist)” property.

  
{% highlight CSHTML %}

<ej-file-explorer id="default" tools-list="@(new List<string>() {"creation","Navigation","addressBar", "copyPaste", "searchBar"})"  path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" width="100%" is-responsive="true"  >
    <e-file-tools creation="@(new List<string>() {"NewFolder"})" address-bar="@(new List<string>() {"Addressbar"})" copy-paste="@(new List<string>() {"Cut", "Copy","Paste"})" navigation="@(new List<string>() {  "Back","Forward", "Upward"})" search-bar="@(new List<string>() {"Searchbar"})">
    </e-file-tools>
<e-file-ajax-settings>
    <e-download url="/FileExplorer/Download{0}"></e-download>
    <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
    <e-upload url="/FileExplorer/Upload{0}"></e-upload>
</e-file-ajax-settings>
</ej-file-explorer>

{% endhighlight %} 
    
## Search bar

The Search bar can be customize through the “[FilterSettings](http://help.syncfusion.com/js/api/ejfileexplorer#members:filtersettings)” property. By default, the search does not consider the case sensitivity, and the search work is based on the “[FilterType](http://help.syncfusion.com/js/api/ejfileexplorer#members:filtersettings-filtertype)”.

The file explorer allows the following filter types in the search functionality.

* “FilterOperator.StartsWith”: Supports to search text with starts with

* “FilterOperator.Contains”: Supports to search text with contains with

* “FilterOperator.EndsWith”: Supports to search text with ends with

In the view page, you can configure the filter type with enabling case sensitivity and filter type like in the following:

{% highlight CSHTML %}
    
<ej-file-explorer id="default" path="wwwroot/images/FileExplorer" ajax-action="@Url.Content("FileActionDefault")" width="100%" is-responsive="true" >
    <e-file-filter-settings case-sensitive-search ="true" filter-type="EndsWith" />
<e-file-ajax-settings>
    <e-download url="/FileExplorer/Download{0}"></e-download>
    <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
    <e-upload url="/FileExplorer/Upload{0}"></e-upload>
</e-file-ajax-settings>
</ej-file-explorer>

{% endhighlight %} 


## Custom Tool in Toolbar

From the toolbar items, you can see the list of built-in tools to perform the operations. Along with this built-in tools, you can add your custom tool with the custom functionality.
You can find an online demo sample of file explorer with custom tool from [here](http://aspnetcore.syncfusion.com/fileexplorer/customtool).

In the view page, add FileExplorer and specify custom tool as shown in the following:
    
{% highlight CSHTML %}

   <ej-file-explorer id="custom" path="wwwroot/images/FileExplorer" layout="Tile" ajax-action="@Url.Content("FileActionDefault")" width="100%" is-responsive="true" tools-list='@new List<string>(){"creation","navigation","addressBar", "copyPaste", "searchBar", "customTool"}'>
        <e-file-ajax-settings>
            <e-download url="/FileExplorer/Download{0}"></e-download>
            <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
            <e-upload url="/FileExplorer/Upload{0}"></e-upload>
        </e-file-ajax-settings>
        <e-file-tools>
            <e-file-custom-tools>
                <e-file-custom-tool name="help" tooltip="help" css="e-fileExplorer-toolbar-icon Help" action="dialogOpen">
                </e-file-custom-tool>
            </e-file-custom-tools>
        </e-file-tools>
    </ej-file-explorer>

 <ej-dialog id="helpDialog" title="FileExplorer Help" enable-resize="false" enable-modal="true" show-on-init="false" width="350" max-height="100" css-class="e-fe-dialog">
        <e-content-template>
            <div class="text-content">
                <div class="header-content">Need assistance?</div>
                <div class="header-content">Our help document assists you to know more about FileExplorer control.</div>
                <div class="header-content">
                    Please refer -> <a href="https://help.syncfusion.com/aspnetmvc/fileexplorer/overview"  target="_blank">Help Document</a>
                </div>
            </div>
        </e-content-template>
    </ej-dialog>
{% endhighlight %}

{% highlight javascript %}
        <script>
            //click handler of custom tool
            function dialogOpen() {
                alert("custom tool item clicked");
            }
        </script>
{% endhighlight%}
{% highlight css %}
        @*Define the CSS that needs to apply for the custom tool.*@
        <style class="cssStyles">
            .e-fileExplorer-toolbar-icon {
                height: 22px;
                width: 22px;
                font-family: 'ej-webfont';
                font-size: 18px;
                margin-top: 2px;
                text-align: center;
            }
            .e-fileExplorer-toolbar-icon.Help:before {
                content: "\e72b";
            }
        </style>
{% endhighlight %}
    
## Enable/Disable the Toolbar item

Each toolbar item can be enabled or disabled through the following client-side public methods.

* [enableToolbarItem](http://help.syncfusion.com/js/api/ejfileexplorer#methods:enabletoolbaritem)

* [disableToolbarItem](http://help.syncfusion.com/js/api/ejfileexplorer#methods:disabletoolbaritem)

These methods accepts the tool name as the parameter. It also allows the parameter as tool item index or the jQuery object of the tool item.
    
    {% highlight javascript %}
    
            $(function () {
                var fileExpObj = $("#fileExplorer").data("ejFileExplorer");
                // this disables the NewFolder item
                fileExpObj.disableToolbarItem("NewFolder");
                // this disables the Layout item (since index of Layout is 0)
                fileExpObj.disableToolbarItem(0);
                // this enables the NewFolder item
                fileExpObj.enableToolbarItem("NewFolder");
            });
    
    {% endhighlight %}

### Enable / Disable the custom added tool in Toolbar Item

If you want to enable / disable the custom added tool in toolbar, you need to pass the corresponding li elements of custom added tool in [enableToolbarItem](https://help.syncfusion.com/api/js/ejfileexplorer#methods:enabletoolbaritem) / [disableToolbarItem](https://help.syncfusion.com/api/js/ejfileexplorer#methods:disabletoolbaritem) method of FileExplorer. Since we have consider this custom tool as a object type.

{% highlight javascript %}
        
        var fileExpObj = $("#fileExplorer").data("ejFileExplorer");
        
        //tool is a cssClass of FileExplorer 
        // this disables the custom tool item 
        
        var li = $(".tool").find(".Help").closest('li'); 
        fileExpObj.disableToolbarItem(li); 
        
        // this enables the custom tool item 
        fileExpObj.enableToolbarItem(li);

{% endhighlight %}

## Customizing the Upload Functionality

The file explorer helps you to upload the file using the “[Upload](http://help.syncfusion.com/js/uploadbox/overview#)” component. File upload can be done through the toolbar item or context menu item. The “[UploadSettings](http://help.syncfusion.com/js/api/ejfileexplorer#members:uploadsettings)” property is used to configure the upload functionalities.

This property has the following sub properties with the default values:
        
**AllowMultipleFile**: This property is used to control the behavior of multiple files upload and this is enabled by default, so you can upload multiple files at a time. If you disable this “AllowMultipleFile” property, you can upload only one file at a time.

**MaxFileSize**: The property limits the maximum file size to upload. It accepts the value in bytes.

**AutoUpload**: When you enable this property, the upload action is performed automatically after selecting the files. When you disable this property, it shows a confirmation dialog with the selected file details and perform the upload action by pressing the “upload” button.

During upload process following events will be triggered, {{'[beforeUploadSend](https://help.syncfusion.com/api/js/ejfileexplorer#events:beforeuploadsend)'| markdownify}}, {{'[beforeUploadDialogOpen](https://help.syncfusion.com/api/js/ejfileexplorer#events:beforeuploaddialogopen)'| markdownify}}, {{'[beforeUpload](https://help.syncfusion.com/api/js/ejfileexplorer#events:beforeupload)'| markdownify}}, {{'[uploadError](https://help.syncfusion.com/api/js/ejfileexplorer#events:uploaderror)'| markdownify}}, {{'[uploadSuccess](https://help.syncfusion.com/api/js/ejfileexplorer#events:uploadsuccess)'| markdownify}} and {{'[uploadComplete](https://help.syncfusion.com/api/js/ejfileexplorer#events:uploadcomplete)'| markdownify}}. You can customize the upload settings with these events.

In the view page, add file explorer and specify the upload settings as shown in the following:
    
   {% highlight CSHTML %}

<ej-file-explorer id="custom" path="wwwroot/images/FileExplorer" layout="Tile" ajax-action="@Url.Content("FileActionDefault")" width="100%" is-responsive="true">
    <e-file-upload-settings allow-multiple-file="false" auto-upload="true" />
    <e-file-ajax-settings>
        <e-download url="/FileExplorer/Download{0}"></e-download>
        <e-get-image url="/FileExplorer/GetImage{0}"></e-get-image>
        <e-upload url="/FileExplorer/Upload{0}"></e-upload>
    </e-file-ajax-settings>
</ej-file-explorer>
        
    {% endhighlight %}
    
