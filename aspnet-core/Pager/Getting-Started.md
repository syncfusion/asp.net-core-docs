---
layout: post
title: Getting-Started | Pager | ASP.NET Core | Syncfusion
description: getting started
platform: aspnet-core
control: Pager
documentation: ug
---

# Getting Started

This section briefly explains about how to create a **Pager** control in your application with ASP.NET Core application.

# Adding Pager control in your Core application

1. Create a ASP.NET core Project and add necessary assemblies and scripts.

2. [Getting Started](/aspnet-core/getting-started) section explains about basic system requirements and the steps to configure the Syncfusion Components in an ASP.NET core application.

3. After successfully adding the necessary dependencies in your solution, make sure to build the solution, so that the necessary assembly files are compiled properly before using it in your project.

4. The Essential ASP.NET Core Pager control based on total records count, page size and page count values. Add the following code example to the corresponding view pages to render the Pager control in your ASP.NET Core application. 

**TotalRecordsCount:** TotalRecordsCount defines the total number of records which is bounded as a single data.

{% highlight CSHTML %}

      /*Razor code to render Pager*/

        @{
           Html.EJ().Pager("pager").TotalRecordsCount(20).Render();
        }
        
{% endhighlight %}

 {% highlight CSHTML %}

        /*ej-Tag Helper code to render Pager*/

        <ej-pager id="pager" total-records-count="20"></ej-pager>

{% endhighlight %}

Run the above sample to get the below output.

![](Getting-Started_images/Getting-Started_img1.png)


 **PageSize:**  PageSize value defines the number of records to be displayed per page. The default value for the PageSize API is 12. 
 
 N> The page count value changes with change in the PageSize value.

  {% highlight CSHTML %}

        /*Razor code to render Pager*/

        @{
          Html.EJ().Pager("pager").TotalRecordsCount(20).PageSize(1).Render();
        }

{% endhighlight %}

{% highlight CSHTML %}

        /*ej-Tag Helper code to render Pager*/

        <ej-pager id="pager" total-records-count="20" page-size="1"></ej-pager>

{% endhighlight %}

Run the above sample to get the below output.

![](Getting-Started_images/Getting-Started_img2.png)

**PageCount:**  PageCount value defines the number of pages to be displayed in the pager control for navigation. The default value for PageCount is 10 and value will be updated based on TotalRecordsCount and PageSize values.

{% highlight CSHTML %}

        /*Razor code to render Pager*/

        @{
           Html.EJ().Pager("pager").TotalRecordsCount(20).PageSize(1).PageCount(3).Render();
        }

{% endhighlight %}

{% highlight CSHTML %}

        /*ej-Tag Helper code to render Pager*/

        <ej-pager id="pager" total-records-count="20" page-size="1" page-count="3"></ej-pager>

{% endhighlight %}

Run the above sample to get the below output.

![](Getting-Started_images/Getting-Started_img3.png)

