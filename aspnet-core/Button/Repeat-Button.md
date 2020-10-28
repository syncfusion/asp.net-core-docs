---
layout: post
title: Repeat Button | Button | ASP.NET Core | Syncfusion
description: repeat button
platform: aspnet-core
control: Button
documentation: ug
---

# Repeat Button

When you press button continuously, click event is raised at each specific time interval. This type of button is called Repeat Button. This functionality repeatedly raises the click event of button in both button click and from button in pressed state to the released state. TimeInterval property is used to specify the time Interval for triggering click event, when the button is in pressed state. RepeatButton property is used to set the button in repeat mode.

The following steps explains you the details about rendering the Repeat Button.

1. In the CSHTML page, configure the Button widget as follows.
 
   ~~~ cshtml

    /*ej-Tag Helper code to render Button*/

	@*Add the code in CSHTML page to configure and initialize the control*@
	@* Enable the button in repeat action mode and specifies time interval.*@
	<div class="control"> 
	<div class="align">  
	    <ej-button id="repeatButton" text="click" size="Mini" show-rounded-corner="true" repeat-button="true" time-interval="200" click="btnClick" />
    </div>
	<div class="align">    
	<div><b>Event Trace</b></div> 
	<div class="eventTrace"></div>  
	</div> 
	</div>

   ~~~

{% highlight html %}

/*Razor code to render Button*/

	 @{ Html.EJ().Button("repeatButton").Text("click").Size(ButtonSize.Mini).ShowRoundedCorner(true).RepeatButton(true).TimeInterval("200").ClientSideEvents(e => e.Click("btnClick")).Render(); }

{% endhighlight %}

N> To render the Button Control you can use either Razor or Tag helper code as given in the above code snippet.
  
   
   ~~~ javascript
   
		//Add this script section that is used to handle the click event
		<script type="text/javascript"> 
		function btnClick(e) { 
		$(".eventTrace").html("click event has been triggered..</br>" + $(".eventTrace").html());
        }   
		</script>
		</table>

   ~~~
  


2. Configure the CSS styles to apply on button

   ~~~ css

	<style>

		.align {

			display: table-cell;

			padding-left: 50px;

		}

	</style>

   ~~~
  

Execute the above code to render the following output.

![](Repeat-Button_images/Repeat-Button_img1.png)

Output for repeat button
{:.caption}
