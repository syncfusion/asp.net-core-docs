---
layout: post
title: Save and Load Report | PivotClient | ASP.NET Core | Syncfusion
description: save and load report
platform: aspnet-core
control: PivotClient
documentation: ug
---

# Save and load report

The save and load report allows you to save the current report collection of the pivot client and render the control later on loading the same.

You can save and load the report in two ways:

* Database
* Local storage

## Save report to database

You can store the report collection of pivot client to database by using the `save-report` event in the pivot client.

N> By default, the online hosted URL link is used for saving the report to database. If you have installed Essential Studio, then you can provide the URL link by hosting “ejServices” in IIS. The “ejServices” folder is available in the below installed location.
Location:  $system drive:\Users\$UserName#\AppData\Local\Syncfusion\EssentialStudio\$Version# \JavaScript\ejservices
Eg: C:\Users\UserName\AppData\Local\Syncfusion\EssentialStudio\{{ site.releaseversion }}\JavaScript\ejservices

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" save-report="saveReportSettings">
      //..
</ej-pivot-client>

<script>
    function saveReportSettings(args) {
        if(args.saveReportSettings)
            return args.saveReportSetting.url = "https://js.syncfusion.com/ejservices/api/PivotClient/Olap"; //You can provide the hosted URL link to save report in DB here.
    }
</script>

{% endhighlight %}

## Save report to local storage

You can store the report collection of the pivot client to local storage by setting the `enable-local-storage` property to true and by defining the `save-report` event of the pivot client.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" save-report="saveReportSettings" enable-local-storage="true">
      //..
</ej-pivot-client>

<script>
    function saveReportSettings(args) {
        var reportCollection = [];
        if ((localStorage.pivotClientRPTCollection != "" && !ej.isNullOrUndefined(localStorage.pivotClientRPTCollection))) {
            reportCollection = JSON.parse(localStorage.pivotClientRPTCollection);
        }
        if(args.saveReportSettings){
            reportCollection.push(({ reportName: args.saveReportSetting.reportName, reportCol: args.saveReportSetting.reportCollection }));
            localStorage.pivotClientRPTCollection = JSON.stringify(reportCollection);;
        }
    }
</script>

{% endhighlight %}

## Load report from database

You can load the stored report collection of the pivot client from database by using the `fetch-report`  and `load-report` events in the pivot client.

N> By default, the online hosted URL link is used to fetch and load the report from the database. If you have installed Essential Studio, then you can provide the URL link by hosting “ejServices” in IIS. The “ejServices” folder is available in the below installed location.
Location:  $system drive:\Users\$UserName#\AppData\Local\Syncfusion\EssentialStudio\$Version# \JavaScript\ejservices
Eg: C:\Users\UserName\AppData\Local\Syncfusion\EssentialStudio\{{ site.releaseversion }}\JavaScript\ejservices

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" load-report="reportSettings" fetch-report="reportSettings">
//..
</ej-pivot-client>

<script>
    function reportSettings(args) {

        if (args.fetchReportSetting)
            return args.fetchReportSetting.url = "https://js.syncfusion.com/ejservices/api/PivotClient/Olap";//you can provide the hosted url link to fetch report from DB here

        else if (args.loadReportSetting)
            return args.loadReportSetting.url = "https://js.syncfusion.com/ejservices/api/PivotClient/Olap";//you can provide the hosted url link to load report from DB here
    }
</script>
{% endhighlight %}

## Load report from local storage

You can load the stored report collection of the pivot client from local storage by setting the `enable-local-storage` property to true and using the `load-report` and `fetch-report` events in the pivot client.

{% highlight CSHTML %}

<ej-pivot-client id="PivotClient1" load-report="reportSettings" fetch-report="reportSettings" enable-local-storage="true">
//..
</ej-pivot-client>

<script>
    function reportSettings(args) {
        var reportCollection = [];
        if ((localStorage.pivotClientRPTCollection != "" && !ej.isNullOrUndefined(localStorage.pivotClientRPTCollection))) {
            reportCollection = JSON.parse(localStorage.pivotClientRPTCollection);
        }
        if (args.fetchReportSetting)
            args.fetchReportSetting.reportList = $.map(reportCollection, function (item, index) { return item.reportName; }).join("__");
        else if (args.loadReportSetting)
            args.loadReportSetting.reportCollection = $.map(reportCollection, function (item, index) { if (item.reportName == args.loadReportSetting.selectedReport) return item.reportCol; });
    }
</script>
{% endhighlight %}