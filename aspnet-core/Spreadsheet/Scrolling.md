---
layout: post
title: Scrolling with Spreadsheet widget for Syncfusion Essential ASP.NET Core
description: How to enable Scrolling and its functionalities
platform: aspnet-core
control: Spreadsheet
documentation: ug
--- 

# Scrolling

Scrolling helps you to move quickly to different areas of worksheet. Scrolling can be enabled by setting `allow-scrolling` as `true` in `e-scroll-settings`. 
  
You can scroll through worksheet using one of the following ways,

* Using the arrow keys
* Using the scroll bars
* Using the mouse

## Set height and width for Scrolling

To set height and width in spreadsheet use `height` and `width` property in `e-scroll-settings`.The height and width can be set in pixel.

The following code example describes the above behavior.

{% highlight cshtml %}
<ej-spread-sheet id="Spreadsheet">
    <e-scroll-settings allow-scrolling="true" width="400" height="600"></e-scroll-settings>
</ej-spread-sheet>
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Scrolling_images/Scrolling_img1.png)

N> In ASP.NET Core, we can’t set `width` and `height` as Percentage values. But, it can be achieved by setting percentage values to its parent element.

## Responsive

Spreadsheet has support for responsive behavior based on client browser's width and height. To enable responsive, set `is-responsive` property in `e-scroll-settings` as `true`. The three modes of responsive layout available in Spreadsheet based on client width are,

* Mobile(<420px)
* Tablet (420px to 617px)
* Desktop(>617px)

N> Default value of `is-responsive` property is `true`.

### Mobile Mode

If client width is less than 420px, the spreadsheet will render in mobile mode. In which, you can see that spreadsheet user interface is customized and redesigned for best view in small screens. The customized feature includes filter dialog, format dialog, chart type dialog and ribbon.

![](Scrolling_images/Scrolling_img2.png)

Ribbon in mobile layout
{:.caption}

![](Scrolling_images/Scrolling_img3.png)

Format cell dialog in mobile layout.
{:.caption}

### Tablet Layout

If the client width is between 420px and 617px, then the spreadsheet will render in tablet mode. Also it has customized the dialogs to match tablet screen size.

![](Scrolling_images/Scrolling_img4.png)

Ribbon in tablet layout.
{:.caption}

## Scroll Mode

Spreadsheet supports two type of modes in scrolling. You can use `scroll-mode` property in `e-scroll-settings` to specify the mode of scrolling.

* Normal - This mode doesn't create new row/column when the scrollbar reaches the end.
* Infinite - This mode creates new row/column when the scrollbar reaches the end.

N> Default value of `scroll-mode` property is `Infinite` mode.

## Virtual Scrolling

Spreadsheet has support for virtual scrolling. This allows you to load data that you require (load data based on viewport size) without buffering the entire huge database. You can set `allow-virtual-scrolling` property in `e-scroll-settings` as `true` to enable virtual scrolling.

N> Default value of `allow-virtual-scrolling` property is true.

