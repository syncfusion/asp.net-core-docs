---
layout: post
title: Animation | Dialog | ASP.NET Core  | Syncfusion
description: How to apply animation effects.
platform: aspnet-core
control: Dialog
documentation: ug
keywords : dialog, animation
---

## Animation

The Dialog widget can be animated while opening and closing the dialog.

We can specify the effect and the duration for the animation. There are two types of effects (slide and fade). We can configure these settings separately for open and close dialog actions.


{% highlight cshtml %}



@{List<string> icon = new List<string>() { "close", "maximize", "minimize", "collapsible" }; }

<div class="control">
    <ej-dialog id="dialog" title="Dialog" action-buttons="icon">
        <e-animation>
            <e-show duration="500" effect="Slide" />
            <e-hide duration="500" effect="Fade" />
        </e-animation>
        <e-content-template>
            <div>
                <p>This is a Dialog</p>
            </div>
        </e-content-template>
    </ej-dialog>
</div>


{% endhighlight %}



![](animation_images\animation_img1.png)

