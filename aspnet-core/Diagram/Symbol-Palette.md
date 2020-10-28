---
layout: post
title: ASP.NET Core Diagram Control | Symbolpalette | Syncfusion.
description: "This page explains how to use symbol palette and its features. Also explains about how to work with diagram control along with the symbol palette"
platform: aspnet-core
control: Diagram
documentation: ug
---

# Symbol Palette

The **SymbolPalette** displays a collection of palettes. The Palette shows a set of nodes and connectors. It allows you to drag and drop the nodes and connectors into the Diagram.

## Create symbol palette

The `DiagramId` property of symbolpalette should be set with the corresponding Diagram ID to drag and drop the nodes and connectors into the Diagram. The following code illustrates how to create symbolpalette.  

{% highlight razor %}

    <ej-symbol-palette id="symbolpalette" diagram-id="Diagram1">
    </ej-symbol-palette>
{% endhighlight %}
 

## Add palettes to SymbolPalette

A palette allows to display a group of related symbols and it textually annotates the group with its header.
To initialize a palette, define a JSON object with the property `Name` that is displayed as the header text of palette. The `Expanded` property of palette allows to expand/collapse its palette items.
The following code example illustrates how to define a palette and how its added to symbol palette.

{% highlight razor %}

    @* define a palette with its name and expands its children. *@
            <ej-symbol-palette id="symbolpalette" width="300px" height="500px">
               @* define a palette with its name and expands its children. *@
                <e-palette name="Flow Shapes" Expanded="true">
                </e-palette>
    </ej-symbol-palette>
{% endhighlight %}

You can add any number of palettes to the `Palettes` collection of the symbol palette. The following example illustrates how to define symbol palette with a palette object that is defined in the previous step.

{% highlight razor %}

    <ej-symbol-palette id="symbolpalette" width="300px" height="500px" show-palette-item-text="true" selected-palette-name="Flow Shapes">
        <e-palettes>
           @* define a palette with its name and expands its children. *@
            <e-palette name="Flow Shapes" expanded="true">
                <e-items>
                    <e-basic-shape name="rectangle" height="50" width="50"  border-width="1" offset-x="20" offset-y="20" ></e-basic-shape>
                </e-items>
            </e-palette> 
        </e-palettes>
    </ej-symbol-palette>
    
{% endhighlight %}

The following image shows the symbol palette with multiple palette Items.

![Adding palettes to the symbol palette](Symbol-Palette_images/Symbol-Palette_img3.png)

### Customize the Palette Header

Palettes can be annotated with its header texts and you can change the height of palette header by using `HeaderHeight` property of symbol palette.

Also, you can embed any HTML element into a palette header by defining the ScriptTemplate id to palette's templateId property. Following code example illustrates how to customize palette headers.

{% tabs %} 
{% highlight js %}

    <!--dependency scripts-->
        <script id="svgTemplate" type="text/x-jsrender">
            <!--define html element-->
            <svg version="1.0" xmlns="http://www.w3.org/2000/svg" width="225px" height="28px">
                <g visibility="visible">
                    <image width="26px" height="26px" opacity="1" xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="image.png"></image>
                    <text x="40" y="18" font-size="14">
                        <tspan>Basic Shapes</tspan>
                    </text>
                </g>
            </svg>
        </script>											

{% endhighlight %}

{% highlight razor %}

    <ej-symbol-palette id="symbolpalette" width="300px" height="500px" show-palette-item-text="true" selected-palette-name="Flow Shapes">
        <e-palettes>
        @* define a palette with its name and expands its children. *@
            <e-palette name="Flow Shapes" expanded="true" template-id="svgTemplate"> 
            </e-palette> 
        </e-palettes>
    </ej-symbol-palette>

{% endhighlight %}

{% endtabs %}

The following image shows the customized palette header

![Customizing palettes header](Symbol-Palette_images/customizethepaletteheader_img1.png)

## Add symbols to palette

The symbol need to be defined and added to the `Items` collection of the palette. You can create a symbol as a node, group, connector, lane, or phase except swimlane.  
 
The following code example illustrates how to define a palette with symbols that are defined in the previous section. 

{% highlight razor %}

    <ej-symbol-palette id="symbolpalette" width="300px" height="500px" show-palette-item-text="true" selected-palette-name="Flow Shapes">
        <e-palettes>
            <e-palette name="Flow Shapes" expanded="true">
                <e-items>
                 @* define a node with its size, position and shape. *@
                    <e-basic-shape name="rectangle" height="50" width="50"  border-width="1" offset-x="20" offset-y="20" ></e-basic-shape>
                </e-items>
            </e-palette> 
        </e-palettes>
    </ej-symbol-palette>

{% endhighlight %}

### Customize the size of symbols

You can customize the size of the individual symbol. The `PaletteItem` property of node enables you to define the size of the symbols. The following code example illustrates how to change the size of a symbol.

{% highlight razor %}

    <ej-symbol-palette id="symbolpalette" width="300px" height="500px" show-palette-item-text="true" selected-palette-name="Flow Shapes">
    @* define a palette with its name and expands its children *@
        <e-palettes>
            <e-palette name="Flow Shapes" expanded="true">
                <e-items>
                @* define a node with its size, position and shape. *@
                    <e-basic-shape name="rectangle" height="50" width="50"  border-width="1" offset-x="20" offset-y="20" >
                        <e-palette-item height="50" width="50">
                            <e-margin bottom="20" left="20" right="20" top="20"></e-margin>
                        </e-palette-item>
                    </e-basic-shape>
                </e-items>
            </e-palette> 
        </e-palettes>
    </ej-symbol-palette>

{% endhighlight %}

Symbol size will be set based on the following precedence.

**Precedence**

| Palette Item | Rendering Size |  
|---|---|---|
| Width | PaletteItem.Width > model.PaletteItemWidth > Node.Width |  
| Height | PaletteItem.height > model.PaletteItem.Height > Node.Height | 

* Symbol size will be rendered in the palette based on Node.PaletteItem's `Width` and `Height` property. 
* If PaletteItem's Width and Height property is not specified, symbol size will be rendered in the palette based on model's `PaletteItemWidth` and `PaletteItemHeight` property. 
* If you don't specify above two, then symbol size will be rendered in the palette based on node's `Width` and `Height` property. 
 

### Stretch the symbols into the palette

The `EnableScale` property of the paletteItem enables you to customize the size of the symbol regardless of the precedence. The following code example illustrates how to customize the symbol size.

{% highlight razor %}

    <ej-symbol-palette id="symbolpalette" width="300px" height="500px">
    <e-palettes>
    @* define a palette with its name and expands its children *@
        <e-palette name="Flow Shapes" expanded="true">
            <e-items>
                <e-basic-shape name="rectangle" height="50" width="50"  border-width="1" offset-x="20" offset-y="20" >
                    <e-palette-item enable-scale="true">                  @* When it is set as false, the element is rendered with actual node size *@ 
                    </e-palette-item>
                </e-basic-shape>
            </e-items>
        </e-palette> 
    </e-palettes>
    </ej-symbol-palette>

{% endhighlight %}

![Customizing symbols size ](Symbol-Palette_images/Symbol-Palette_img1.png)

![Symbol size customization regardless of the precedence](Symbol-Palette_images/Symbol-Palette_img2.png)


## Symbol Previews

Image, simple snippet to customize the preview size

You can customize the preview size of the individual palette items. The `PaletteItem` property of node enables you to define the preview size of the symbol items. The following code example illustrates how to change the preview size of a palette item.

{% highlight razor %}

    <ej-symbol-palette id="symbolpalette" width="300px" height="500px">
    <e-palettes>
        <e-palette name="Flow Shapes" expanded="true">
            <e-items>
                <e-basic-shape name="rectangle" height="50" width="50"  border-width="1" offset-x="20" offset-y="20" >
                @* Enables to fit the content into the specified palette item size*@
                    <e-palette-item preview-height="50" preview-width="50"  >                     
                    </e-palette-item>
                </e-basic-shape>
                <e-basic-shape name="ellipse" shape="Ellipse" height="50" width="50" border-width="1" offset-x="20" offset-y="20"></e-basic-shape>
            </e-items>
        </e-palette> 
    </e-palettes>
    </ej-symbol-palette>

{% endhighlight %}

![Customizing previewing size of the palette items](Symbol-Palette_images/Symbol-Palette_img4.png)

You can also customize the preview size of the all palette items. The `PreviewWidth` and `PreviewHeight` property of SymbolPalette enables you to define the preview size to all the symbol palette items. The following code example illustrates how to change the preview size of a symbol palette items.

{% highlight razor %}

    @* Enables to fit the content into the specified palette item size*@
    <ej-symbol-palette id="symbolpalette" width="300px" height="500px" preview-height="50" preview-width="50">
    <e-palettes>
        <e-palette name="Flow Shapes" expanded="true">
            <e-items>
                <e-basic-shape name="rectangle" height="50" width="50"  border-width="1" offset-x="20" offset-y="20" ></e-basic-shape>
                <e-basic-shape name="ellipse" shape="Ellipse" height="50" width="50" border-width="1" offset-x="20" offset-y="20"></e-basic-shape>
            </e-items>
        </e-palette> 
    </e-palettes>
    </ej-symbol-palette>

{% endhighlight %}

![Customizing preview size for the symbol palette items](Symbol-Palette_images/Symbol-Palette_img5.png)

Symbol palette allows to sets the offset of the dragging helper relative to the mouse cursor.

{% tabs %}

{% highlight Razor %}

    @* defines the preview offset *@
    <ej-symbol-palette id="symbolpalette" width="300px" height="500px" preview-offset="ViewBag.previewOffset">
    <e-palettes>
        <e-palette name="Flow Shapes" expanded="true">
            <e-items>
                <e-basic-shape name="rectangle" height="100" width="100"  border-width="1" offset-x="20" offset-y="20" ></e-basic-shape>
            </e-items>
        </e-palette> 
    </e-palettes>
    </ej-symbol-palette>

{% endhighlight %}

{% highlight C# %}

    //Defines the preview offset
    DiagramPoint Point = new DiagramPoint();
    Point.X = 50;
    Point.Y = 50;
    ViewBag.previewOffset = Point;

{% endhighlight %}

{% endtabs %}  

![Defininig preview offset](Symbol-Palette_images/Symbol-Palette_img6.png)


Symbol preview size will be set based on the following precedence.

**Precedence**

| Palette Item |   Preview Size |
|---|---|---|
| Width |  PaletteItem.PreviewWidth > Model.PreviewWidth > Node.Width |
| Height | PaletteItem.PreviewHeight > Model.PreviewHeight > Node.Height |

* Symbol preview size will be set based on node.paletteItem's `PreviewWidth` and `PreviewHeight` property. 
* If paletteItem's width and height property is not specified, symbol size will be set based on model's `PreviewWidth` and `PreviewHeight` property. 
* If you don't specify above two, then symbol size will be rendered in the palette based on node's `Width` and `Height` property. 

## Show/hide the symbol Text 

You can show/hide the symbol text by using the `ShowPaletteItemText` property of symbol palette.

{% highlight Razor %}

    @*Specifies whether palette item text should be visible or not*@ 
    <ej-symbol-palette id="symbolpalette" width="300px" height="500px" show-palette-item-text="true">
    </ej-symbol-palette>

{% endhighlight %}

To explore the properties of symbol palette, refer to [Symbol Palette Properties](https://help.syncfusion.com/cr/aspnetmvc/Syncfusion.JavaScript.DataVisualization.SymbolPalettePropertiesBuilder.html "Symbol Palette Properties").
