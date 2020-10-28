---
layout: post
title: Syncfusion Dialog Getting-Started
description: getting started
platform: aspnet-core
control: Dialog
documentation: ug
---

# Getting Started

This section allows you to learn how to configure and use our Dialog control in your application. It also allows you to learn how to add content to the dialog in different way.

## Create your first Dialog in ASP.NET Core

Refer the [Getting Started](https://help.syncfusion.com/aspnet-core/getting-started) page of the Introduction part to know more about the basic system requirements and the steps to configure the Syncfusion components in an ASP.NET Core application.

Add the following code snippet to the corresponding view page to render dialog with default settings.

{% highlight cshtml %}

        <ej-dialog id="basicDialog" >
          </ej-dialog>

{% endhighlight %}

![Getting Started](Getting-Started_Images/default.png)

## Set content

Add Contents to the dialog using "e-content-template" property, which is given below.

{% highlight cshtml %}

        <ej-dialog id="basicDialog" >
        <e-content-template>
                <div class="cnt">
                                This is sample content.
                     </div>
                       </e-content-template>
          </ej-dialog>

{% endhighlight %}


![Set content](Getting-Started_Images/content.png)
       
## Set Title

The Dialog control's title can be set through the 'title' property. which is shown in the below code snippet.

{% highlight cshtml %}

        <ej-dialog id="basicDialog" title="Dialog">
            <e-content-template>
                <div class="cnt">This is sample content. </div> 
            </e-content-template> 
        </ej-dialog>
     
{% endhighlight %}
  

![Set Title](Getting-Started_Images/title.png)

## Open Dialog dynamically

In most cases, the Dialog controls are needed only in dynamic actions like showing some messages on clicking a button, to provide alert, etc. So the Dialog control provides “open” and “close” methods to open/close the dialogs dynamically.

The Dialog control can be hidden on initialize using **show-on-init** property which should be set to false.
We can open and close the dialog on button click. Refer the below code

{% highlight cshtml %}

        <ej-button id="btnOpen" text="Click to open dialog" click="onclick" />
        <div class="control">
                <ej-dialog id="basicDialog" title="Dialog" is-responsive="true" close="onDialogClose" show-on-init="false">
                <e-content-template>
                        This is sample content.
                </e-content-template>
                </ej-dialog>
        </div>
       
{% endhighlight %}  

{% highlight javascript %}  

        function onclick() {
            $("#basicDialog").ejDialog("open");
            $("#btnOpen").hide();
        }
        function onDialogClose(args) {
            $("#btnOpen").show();
        }

  {% endhighlight %}

![Open Dialog dynamically](Getting-Started_Images/Dialogbtn.png)