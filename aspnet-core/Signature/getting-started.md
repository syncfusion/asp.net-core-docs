---
layout: post
title: getting started | Signature | ASP.NET Core | Syncfusion
description: getting started
platform: ASP.NET core
control: Signature
documentation: ug
---

# Getting Started

The Essential ASP.NET core Signature simplifies creation of a signature capture in a browser, allowing a user to draw a signature using mouse or touch.

This section explains briefly about how to create a **Signature** control in your application with ASP.NET core by the following step-by-step instructions.

The following screenshot demonstrates the output of the Signature control in ASP.NET core  

![](Getting_Started_images\gettingstarted_img1.png)

## Create a Simple Signature

Refer the [Getting Started](https://help.syncfusion.com/aspnet-core/getting-started) page of the Introduction part to know more about the basic system requirements and the steps to configure the Syncfusion components in an ASP.NET Core application.

Once you have done all the basic configurations which is mentioned in the ASP.NET Core getting started page, now you can create and deploy our Signature Control.

Initialize the AutoComplete control in the view page by using the below code.

{% highlight razor %}

<ej-signature id="signature" height="400px" > </ej-signature>

{% endhighlight %}

After Execute the above code the Signature control appears as follows.

![](Getting_Started_images\createasimplesignature_img1.png)


## Adjusting Signature Size

You can customize the width and height of the Signature by **width** and **height** properties. These properties completely depend on signature canvas. The width and height are adjusted within the signature canvas.

The following code example is used to render the Signature control with customized width and height.

{% highlight razor %}

<ej-signature id="signature" height="300px" width="200px" > </ej-signature>

{% endhighlight %}


After Execute the above code the Signature control appears as follows.

![](Getting_Started_images\adjustingsignaturesize_img1.png)





