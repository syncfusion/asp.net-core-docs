---
layout: post
title: Behaviour Settings | Slider | ASP.NET Core | Syncfusion
description: behaviour settings
platform: aspnet-core
control: Slider
documentation: ug
---

# Behavior Settings

### Height

By default, Slider renders with a height of 14px. You can change the Slider height using Height property. Specify the value for this property in string format.

### Width

By default, Slider widget renders with 100% width. You can customize the width of the Slider using Width property. Specify the value for this property in string format.

The following steps explains you on how to configure the Height and Width of the Slider.

1. In an view page, add a Tag helper element to render it as a Slider widget.

{% highlight CSHTML %}

	@*Add this code in your view page*@ 

	<ej-slider id="basicSlider" height="20px" width="500px"/>

{% endhighlight %}

Execute the above code example to render the following output.

![](Behaviour-Settings_images/Behaviour-Settings_img1.png)


### IncrementStep

This property sets the incremental step value for the Slider. When the Slider handle slides through mouse or keyboard, it increments / decrements the value based on the step value. By default, when the slider handle is moved, single value increments / decrements. Using IncrementStep property you can change the increment step value. Data type of this property is number.

The following steps explains you on how to configure the IncrementStep property.

1. In an view page, add a Tag helper element to render it as a Slider widget.


{% highlight CSHTML %}

	@*Add this code in your view page*@ 

	<ej-slider id="basicSlider" height="20px" width="500px" increment-step="5" />

{% endhighlight %}

Execute the above code example to render the following output.

![](Behaviour-Settings_images/Behaviour-Settings_img2.png)



In the above example, value for IncrementStep property is specified as “5” therefore, when you move the Slider handle, value “5” increments/decrements from the current Slider value.

### ReadOnly

This feature prevents you from interacting with the Slider. That is you can only view the Slider value and cannot change it.

The following steps explains you on how to enable the ReadOnly property.

1. In an view page, add a Tag helper element to render it as a Slider widget.

{% highlight CSHTML %}

 	@*Add this code in your view page*@

    <ej-slider id="basicSlider" height="20px" width="500px" read-only="true" />

{% endhighlight %}

After you execute the above code example, the Slider values cannot be changed in any ways.

![](Behaviour-Settings_images/Behaviour-Settings_img3.png)