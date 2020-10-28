---
layout: post
title: Action Buttons | Dialog | ASP.NET Core| Syncfusion
description: How to enable the Interaction button like “Close”, “Minimize” and etc., in Dialog Widget.
platform: aspnet-core
control: Dialog
documentation: ug
keywords : dialog
---

# Action Buttons

The Dialog widget provides the following action buttons.

1. Close

2. Maximize

3. Minimize

4. Pin/Unpin

5. Collapse/Expand

You can display only the necessary buttons in the Dialog widget by configuring the `action-buttons` property.

{% highlight cshtml %}

@{List<string> icon = new List<string>() { "close", "maximize", "minimize" }; }

    <ej-dialog id="dialog" title="Dialog" action-buttons="icon">
        <e-content-template>
            <div>
              <p>This is a Dialog</p>
            </div>
        </e-content-template>
    </ej-dialog>


{% endhighlight %}



![Action Buttons](action-buttons_images\action-buttons_img1.png)

## Customizing Action Buttons

We can customize the action buttons in dialog widget.

You can add new action button in the dialog widget by configuring the `action-button-click` event.

{% highlight cshtml %}

@{List<string> icon = new List<string>() { "close", "maximize", "minimize","collapsible","pin","mediaplay","search"}; }

    <ej-dialog id="dialog" title="Dialog" action-buttons="icon" action-button-click="playMedia">
        <e-content-template>
            <div>
              <p>This is a Dialog</p>
            </div>
        </e-content-template>
    </ej-dialog>

{% endhighlight %}
	

{% highlight javascript %}
          
		  function playMedia(args)
		    {
               console.log(args.buttonID);
            }
		
{% endhighlight %}
      



![Action Buttons](action-buttons_images\action-buttons_img2.png)

