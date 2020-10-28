---
layout: post
title: Behavior Settings | Pager | ASP.NET Core | Syncfusion
description: behavior settings
platform: aspnet-core
control: Pager
documentation: ug
---

# Behavior Settings

## PageSizeList

The **PageSizeList** property of the pager control allows an option to have multiple options of page size values.By defining PageSizeList, a dropdown will render in a pager with given values along with the current page size as selected value in dropdown. 

Selected value in a dropdown will be set to PageSize API and pager will refresh based on this new page size.

{% highlight CSHTML %}

/*Razor code to render Pager*/

    @{
    List<int> pageSizeList = new List<int>();
    pageSizeList.Add(1);
    pageSizeList.Add(2);
    pageSizeList.Add(3);
    } 

    @{
      Html.EJ().Pager("pager").TotalRecordsCount(20).PageSize(1).PageSizeList(pageSizeList).PageCount(3).Render();
    }


{% endhighlight %}

{% highlight CSHTML %}

/*ej-Tag Helper code to render Pager*/

    @{
    List<int> pageSizeList = new List<int>();
    pageSizeList.Add(1);
    pageSizeList.Add(2);
    pageSizeList.Add(3);
    }  

      <ej-pager id="pager" total-records-count="20" page-size="1" page-size-list="pageSizeList" page-count="3"></ej-pager>

{% endhighlight %}

![](behavior-settings_images\pageSizeList.png)

## PageSizeMessage

The **PageSizeMessage** property allows to show a message along with the dropdown when **PageSizeList** API of pager control is defined. In the below sample, the **PageSizeMessage** of pager displays the current **PageSize** value of the pager control and will also be updated whenever the PageSize value is changed by selecting a value from the dropdown.

{% highlight CSHTML %}

    /*Razor code to render Pager*/

    @{
    List<int> pageSizeList = new List<int>();
    pageSizeList.Add(1);
    pageSizeList.Add(2);
    pageSizeList.Add(3);
    } 

    @{
      Html.EJ().Pager("pager").TotalRecordsCount(20).PageSize(1).PageCount(3).PageSizeList(pageSizeList).PageSizeMessage("PageSize value: 1").ClientSideEvents(eve => eve.PageSizeSelected("pageSizeInfo")).Render();
    } 

<script>
    function pageSizeInfo(e) {
        var a = $("#pager").ejPager("instance");
        a.option("pageSizeMessage", "PageSize value: " + e.pageSize);
    }
</script>

{% endhighlight %}

{% highlight CSHTML %}

   /*ej-Tag Helper code to render Pager*/

    @{
    List<int> pageSizeList = new List<int>();
    pageSizeList.Add(1);
    pageSizeList.Add(2);
    pageSizeList.Add(3);
    } 

    <ej-pager id="pager" total-records-count="20" page-size="1" page-size-list="pageSizeList" page-count="3" page-size-message="PageSize value: 1" page-size-selected="pageSizeInfo"></ej-pager>

<script>
    function pageSizeInfo(e) {
        var a = $("#pager").ejPager("instance");
        a.option("pageSizeMessage", "PageSize value: " + e.pageSize);
    }
</script>

{% endhighlight %}

![](behavior-settings_images\pageSizeMessage.png)

## Responsive

The pager control has responsive support such that control also fit with mobile resolutions. By enabling **IsResponsive** API, you can make the pager control responsive. While resizing the browser window, the inner elements in the pager control will adjust automatically to equalize the size. By default, **IsResponsive** API value is false. 

{% highlight CSHTML %}

    /*Razor code to render Pager*/

    @{
    Html.EJ().Pager("pager").PageCount(3).PageSize(1).IsResponsive(true).TotalRecordsCount(20).Render();
    }

{% endhighlight %}

{% highlight CSHTML %}

    /*ej-Tag Helper code to render Pager*/

    <ej-pager id="pager" total-records-count="20" page-size="1" page-count="3" is-responsive="true"></ej-pager>

{% endhighlight %}

![](behavior-settings_images\pager_Responsive.png)

## CurrentPage

The **CurrentPage** value of the pager determines which page to be displayed currently. The default value of the **CurrentPage** API is 1.

{% highlight CSHTML %}

     /*Razor code to render Pager*/

    @{
      Html.EJ().Pager("pager").PageSize(1).PageCount(3).CurrentPage(2).TotalRecordsCount(20).Render();
    }

{% endhighlight %}

{% highlight CSHTML %}

     /*ej-Tag Helpers code to render Pager*/

    <ej-pager id="pager" total-records-count="20" page-size="1" page-count="3" current-page="2"></ej-pager>

{% endhighlight %}

![](behavior-settings_images\pager_Currentpage.png)

## Enable/Disable

You can enable or disable pager control by using **Enabled** property. Setting enabled API value as false will disable the user interaction with the pager control.

{% highlight CSHTML %}

     /*Razor code to render Pager*/

    @{
     Html.EJ().Pager("pager").PageSize(1).PageCount(3).Enabled(false).TotalRecordsCount(20).Render();
    }

{% endhighlight %}

{% highlight CSHTML %}

     /*ej-Tag Helpers code to render Pager*/

    <ej-pager id="pager" total-records-count="20" page-size="1" page-count="3" enabled="false"></ej-pager>

{% endhighlight %}

![](behavior-settings_images\pager_EnableDisable.png)