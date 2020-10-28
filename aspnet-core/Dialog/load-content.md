---
layout: post
title: Load Content | Dialog | ASP.NET Core | Syncfusion
description: How to load content to dialog widget either using the Ajax, iframe, and Image.
platform: aspnet-core
control: Dialog
documentation: ug
keywords : dialog, content
---

# Load content

By default, the content inside the content-template property element is considered as the content for the Dialog widget.

Also, we can render the Dialog widget content through the following ways.

1. Request through AJAX

2. Request iframe content

3. Request image content

This settings can be specified through `content-type` property.

{{ 'N> Create a view page (AjaxContent.cshtml) which contains the content of the dialog.' | markdownify }}

{% highlight cshtml %}

<div class="control">
    <ej-dialog id="dialog" title="Dialog" content-type="ajax" content-url="@Url.Content("~/dialog/ajaxcontent").ToString()">
    </ej-dialog>
</div>


{% endhighlight %}

AjaxContent.cshtml

{% highlight cshtml %}


    <div id="content"> This content is loaded via AJAX request. </div>



{% endhighlight %}



![Load content](load-content_images\load-content_img1.png)

We can handle the AJAX request’s success and failures through the events “ajax-success” and “ajax-error” events respectively. 

You can modify the previous example as below to handle the success and failure events.

{% highlight razor %}


<div class="control">
    <ej-dialog id="dialog" title="Dialog" content-type="ajax" ajax-success="onSucess" ajax-error="onerror" content-url="@Url.Content("~/dialog/ajaxcontent").ToString()">
    </ej-dialog>
</div>

{% endhighlight %}


Add the below script to the view page

{% highlight js %}


    <script>
        function onSuccess(args) {
            //handle success event
        }
        function onError(args) {
            //handle success event
        }
    </script>



{% endhighlight %}


N> The same way we can render the iframe and image content for the Dialog widget by specifying the `content-type` as “iframe” and “image” respectively and also by specifying the proper location in the `content-url` property.  If you wish to dynamically change the dialog content, you can set the `content-url` and the `content-type` property through setModel on any action.