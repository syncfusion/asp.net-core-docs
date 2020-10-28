---
layout: post
title: Text Configuration | Tile | ASP.NET Core | Syncfusion
description: text configuration
platform: aspnet-core
control: Tile
documentation: ug
keywords: text
---

# Text Configuration

show-text property is used to show or hide the Tile caption. By default, the show-text property is to true on initialization.text property is used to set the caption of a Tile as a Text on initialization. text-alignment property is used to align the Tile text as Normal on initialization. The possible position values for text-alignment are as follows: 

1. Normal
2. Left
3. Right
4. Center



Refer to the following code examples.


{% highlight CSHTML %}

<ej-tile id="tile" image-position="@TileImagePosition.Center" tile-size="@TileSize.Medium" text="Camera" text-alignment="Center" image-url="../images/tile/windows/camera.png"></ej-tile>

{% endhighlight %}



![](Text-Configuration_images/Text-Configuration_img1.png)



