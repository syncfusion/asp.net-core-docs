---
layout: post
title: Behavior and Settings | WaitingPopup | ASP.NET Core | Syncfusion
description: behavior and settings
platform: aspnet-core
control: WaitingPopup
documentation: ug
---

# Behavior and Settings

## Automatic Initializing WaitingPopup widget

WaitingPopup widget contains ShowOnInit property that allows the popup to display over a target on page load automatically. By default, ShowOnInit property is set as false.

The following steps explains you on how to display the WaitingPopup on page load.

1. In an VIEW page, add the below code to render WaitingPopup widget.

{% highlight CSHTML %}
    
<div id="target">
	<ej-waiting-popup id="target" show-on-init="true" />
</div>

{% endhighlight %}
   
2. Add the following styles to render WaitingPopup widget.

{% highlight css %}

	<style type="text/css" class="cssStyles">

    #target {
        height: 320px;
        width: 600px;
    }

	</style>

{% endhighlight %}
   
The following screenshot illustrates the WaitingPopup when ShowOnInit is set to “true”.

![](Behavior-and-Settings_images/Behavior-and-Settings_img1.png)

WaitingPopup with enabled showOnInit property
{:.caption}

### Enable / Disable Popup Indicator

You can show or hide the popup indicator of WaitingPopup widget using ShowImage property. By default, ShowImage property is set as true.

The following steps explains you to enable / disable popup indicator in WaitingPopup widget.

1. In the VIEW page, add the below code to render WaitingPopup widget.

{% highlight CSHTML %}

Enable popup indicator:

<div id="target">
	
	<ej-waiting-popup id="target" show-on-init="true" show-image="true" text="Loading... Please wait..."/>

</div>

Disable popup indicator:

<div id="target">
	
	<ej-waiting-popup id="target" show-on-init="true" show-image="false" text="Loading... Please wait..."/>

</div>

{% endhighlight %}   

2. Add the following styles to render WaitingPopup widget.

{% highlight css %}

<style type="text/css" class="cssStyles">

#target {
	height: 320px;
	width: 600px;
}

</style>

{% endhighlight %}
   
Execute the above code to render the following output.

![](Behavior-and-Settings_images/Behavior-and-Settings_img2.png)

Enabled popup indicator WaitingPopup widget
{:.caption}

![](Behavior-and-Settings_images/Behavior-and-Settings_img3.png)

Disabled popup indicator WaitingPopup widget
{:.caption}

## Show / Hide WaitingPopup

Using Show() and Hide() methods, you can display or hide the WaitingPopup widget over the target area.

The following steps explains you to show / hide the WaitingPopup widget.

1. In the VIEW page, add the below code to render WaitingPopup widget.

{% highlight CSHTML %}

<div id="target">        
    <ej-waiting-popup id="target" show-on-init="true" /> 
</div>
	
Show WaitingPopup:

<script type="text/javascript"> 
var popUpObj;   
$(function () {
	$("#target").ejWaitingPopup();
	popUpObj = $("#target").data("ejWaitingPopup");
	popUpObj.show();  
});
</script>

Hide WaitingPopup:

<script type="text/javascript"> 
var popUpObj   
$(function () {  
	$("#target").ejWaitingPopup();
	popUpObj = $("#target").data("ejWaitingPopup"); 
	popUpObj.hide(); 
});
</script>

{% endhighlight %}   
   
2. Add the following styles to render WaitingPopup widget.

{% highlight css %}

<style type="text/css" class="cssStyles">

#target {
	height: 320px;
	width: 600px;
}

</style>

{% endhighlight %}

The following screenshot illustrates a WaitingPopup when Show() method is invoked.

![](Behavior-and-Settings_images/Behavior-and-Settings_img4.png)

WaitingPopup with Show() method
{:.caption}