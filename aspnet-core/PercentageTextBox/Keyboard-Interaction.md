---
layout: post
title: Keyboard Interaction | PercentageTextBox | ASP.NET Core | Syncfusion
description: keyboard interaction
platform: aspnet-core
control: PercentageTextBox
documentation: ug
---

# Keyboard Interaction

With the keyboard navigation enabled in the PercentageTextBox control, it is possible to control the actions with the provided shortcut keys. Almost all the PercentageTextBox functionality that are done through mouse can be controlled with shortcut keys.

The various keyboard shortcuts available within the PercentageTextBox control are discussed in the following table. 

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
{{ '[Access key](http://en.wikipedia.org/wiki/Access_key)' | markdownify }} + j</td><td>
Focuses the control</td></tr>
<tr>
<td>
Up</td><td>
Increments the value</td></tr>
<tr>
<td>
Down</td><td>
Decrements the value</td></tr>
<tr>
<td>
Tab</td><td>
Focus the next element</td></tr>
</table>

### Configuring Keyboard Navigation

The following steps explain the implementation of keyboard interaction in PercentageTextBox.

In the View page add the below code. Set the access key property to the PercentageTextBox for focusing the control while key is pressed. We need to use ‘HtmlAttributes’ property to add the ”access key” attribute to the Editor elements. ‘HtmlAttributes’ property is used to add HTML attributes like, id, class etc.. to the components. We need to use IDictionary<string,object> to specify the HTML attributes. 

{% highlight CSHTML %}

@{IDictionary<string, object> percentAttribute = new Dictionary<string, object>();

percentAttribute.Add("accesskey", "k");

}

<ej-percentage-text-box id="percent" name="percent" value="22" html-attributes="percentAttribute"/>

{% endhighlight %}

 Run the above example and press [Access key](http://en.wikipedia.org/wiki/Access_key) + j key to focus the PercentageTextBox widget. Perform provided functionality by using keyboard shortcuts.

![](Keyboard-Interaction_images/Keyboard-Interaction_img1.png)