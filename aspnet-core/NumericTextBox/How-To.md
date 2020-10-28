---
layout: post
title: Getting Started | NumericTextBox | ASP.NET Core | Syncfusion
description: getting started
platform: aspnet-core
control: NumericTextBox
documentation: ug
---

# How To

## Use Normal Textboxes as Syncfusion textboxes

In an application or a web page, you may use normal textboxes along with other Syncfusion components, since there is no separate Essential JavaScript plugin for textboxes.

So, you may want to make a normal textbox to look like Syncfusion textbox in order to achieve uniform look and appearance in your web page.

This can be achieved by adding **“e-textbox”** class to the HTML element.

By adding this class, the textbox will have standard look and appearance as other components for all the themes supported by Syncfusion.

{% highlight html %}

<input type="text" class="e-textbox" value="This is a normal Textbox"/>
	
{% endhighlight %}

Textbox will be rendered as shown below.

![](How_to/normaltextbox_customize.png)

Normal textbox as Syncfusion textbox
{:.caption}

