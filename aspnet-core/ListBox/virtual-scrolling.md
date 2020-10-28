---
layout: post
title: VirtualScrolling support | ListBox | ASP.NET Core | Syncfusion
description: VirtualScrolling support 
platform: aspnet-core
control: ListBox
documentation: ug
---

# VirtualScrolling support 

ListBox widget provides the VirtualScrolling support, when binding the remote data for the ListBox. It loads partially, only a set of data from remote server loaded initially, and imports data further upon loading. To enable VirtualScrolling support, set the  allow-virtual-scrolling property as true. You can set ItemsCount that specifies number of items in the ListBox. You can load any number of items upon request with ItemRequest ClientSide Event.

The following steps explains you the behavior of VirtualScrolling support in ListBox.

1. Add the below code in your page to render the ListBox


{% highlight CSHTML %}
   
<div class="control">
    <h5 class="ctrllabel">
        Select Customer ID
    </h5>

    <ej-list-box id="customerList" query="ej.Query().from('Customers')" allow-virtual-scrolling="true" item-request="itemRequested">
        <e-datamanager url="//mvc.syncfusion.com/Services/Northwnd.svc/"></e-datamanager>
        <e-list-box-fields text="CustomerID" />
    </ej-list-box>
</div>
  {% endhighlight %}
   
   
{% highlight JS %}
	<script type="text/javascript"> 
		function itemRequested(args) {
		var target = $("#customerList").data("ejListBox");
		//to load 20 items
		target.model.query = ej.Query().from('Customers').range(args.start, args.start + 20);
		this.model.itemsCount = 20; 
		}
	</script>
  {% endhighlight %}
   



2. Output of the above steps.


   ![](Load-on-Demand-support_images/Load-on-Demand-support_img1.png)



