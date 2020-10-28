---
layout: post
title: Customization of Syncfusion treeMap control for ASP.NET Core
description: Learn how to customize the treemap control
platform: aspnet-core
control: TreeMap
documentation: ug
---

# Customization

TreeMap control supports color customization to determine the exact combination of colors for tree nodes displayed in TreeMap and tooltip support to display additional information of treemap data.

## Color Customization

You can customize the colors of the leaf nodes of TreeMap using the ColorMapping support of the TreeMap. 

`ColorMapping` is categorized into three different types such as,

* `UniColorMapping`
* `RangeBrushColorMapping`
* `DesaturationColorMapping`

## UniColorMapping

You can color, all the leaf nodes with the same color by setting the color value of the `UniColorMapping` property of the TreeMap.

{% highlight CSHTML %}

<div style="height:400px;width:700px;">
<ej-tree-map id="treemap" datasource="ViewBag.datasource" weight-value-path="Population" color-value-path="Growth">
    <e-levels><e-level group-path="Continent" group-gap="5"></e-level></e-levels>
    <e-uni-color-mapping color="crimson"></e-uni-color-mapping>
</ej-tree-map>
</div>

{% endhighlight %}

![](Customization_images/Customization_img1.png)


## Range Color Mapping

You can group the leaf nodes based on the range of the data’s color values. You can set a unique color for every ranges. To achieve this, specify the `To` and `From` values as range bound and `Color` value to fill the leaf nodes of the particular range, through the `RangeColorMapping` property of the TreeMap.

{% highlight CSHTML %}

<div style="height:400px;width:700px;">
<ej-tree-map id="treemap" datasource="ViewBag.datasource" weight-value-path="Population" color-value-path="Growth">
    <e-levels><e-level group-path="Continent" group-gap="5"></e-level></e-levels>
    <e-range-color-mappings>
        <e-range-color-mapping to="1" from="0" color="#77D8D8" legendlabel="Range1"></e-range-color-mapping>
        <e-range-color-mapping to="2" from="0" color="#AED960" legendlabel="Range2"></e-range-color-mapping>
        <e-range-color-mapping to="3" from="0" color="#FFAF51" legendlabel="Range3"></e-range-color-mapping>
        <e-range-color-mapping to="4" from="0" color="#F3D240" legendlabel="Range4"></e-range-color-mapping>
    </e-range-color-mappings>
</ej-tree-map>
</div>

{% endhighlight %}

![](Customization_images/Customization_img2.png)


## Desaturation Color Mapping

You can differentiate all the leaf nodes using the `DesaturationColorMapping` property of the TreeMap. Differentiation is achieved, even though same color is applied for all the leaf nodes by varying the opacity of the leaf nodes based on the color value specified in the color value range using `RangeMinimum` and `RangeMaximum` value of the data collection. You can also bound the opacity range by setting from and to property of the `DesaturationColorMapping`.

{% highlight CSHTML %}

<div style="height:400px;width:700px;">
<ej-tree-map id="treemap" datasource="ViewBag.datasource" weight-value-path="Population" color-value-path="Growth">
    <e-levels><e-level group-path="Continent" group-gap="5"></e-level></e-levels>
    <e-desaturation-color-mapping to="0.2" from="1" color="DeepSkyBlue" range-maximum="4" range-minimum="0"></e-desaturation-color-mapping>
</ej-tree-map>
</div>

{% endhighlight %}

![](Customization_images/Customization_img3.png)

## Tooltip

You can enable the tooltip support for the TreeMap by setting the `ShowTooltip` property to true. By default, it takes the property of the bound object that is referred to in the `GroupPath` and displays its content when the corresponding node is tapped. The `TooltipTemplate` is a HTML element that is used to expose the custom template for the tooltip.

## Leaf Item Setting

You can customize the Leaf level TreeMap items using `LeafItemsSetting`. The Label and tooltip values take the property of bound object that is referred in the LabelPath when defined.

You can specify the border color using `BorderBrush` property.

* For customizing border thickness, you can use `BorderThickness` property.

* To customize the gap between the leaf items, you can use `Gap` property.

* You can specify the label template for the leaf item using `ItemTemplate` property.

* The Label and tooltip values take the property of bound object that is referred in the `LabelPath` when defined.

* You can specify the position of the leaf labels using `LabelPosition` property.

* You can control the mode of label visibility of the labels using `LabelVisibilityMode` property.

* To show or hide the visibility of the leaf item labels you can use `ShowLabels` property.

* For specifying over flow action of left item labels you can use `TextOverflow` property.


{% highlight CSHTML %}

<div style="height:400px;width:700px;">  <ej-tree-map id="treemap" datasource="ViewBag.datasource" show-tooltip="true" tooltip-template="tooltiptemplate" weight-value-path="Population" color-value-path="Growth">
    <e-levels><e-level group-path="Continent" group-gap="5"></e-level></e-levels>
    <e-range-color-mappings>
        <e-range-color-mapping to="1" from="0" color="#77D8D8"></e-range-color-mapping>
        <e-range-color-mapping to="2" from="0" color="#AED960"></e-range-color-mapping>
        <e-range-color-mapping to="3" from="0" color="#FFAF51"></e-range-color-mapping>
        <e-range-color-mapping to="4" from="0" color="#F3D240"></e-range-color-mapping>
    </e-range-color-mappings>
    <e-leaf-item-settings label-path="Region" show-labels="true"></e-leaf-item-settings>
</ej-tree-map>
</div>

<script  id="tooltiptemplate" type="application/jsrender">

<div  style="margin-left:17px;margin-top:-45px;">      

    <div style="height:auto;width:auto;background:black;border-radius:3px;opacity:0.6">

        <div style="margin-top:-20px;margin-left:9px;padding-top:3px;margin-right:9px;">

            <label style="margin-top:-20px;font-weight:normal;font-size:12px;color:white;font-family:Segoe UI;">{{:Region}}</label>

        </div>

        <div style="height:10px;"></div>

        <div style="margin-top:-10px;margin-left:9px;margin-right:9px;padding-bottom:3px;">

            <label style="margin-top:-10px;font-weight:normal;font-size:14px;color:white;font-family:segoe ui light;">{{:Population}}</label>

        </div>

    </div>

</div>            

</script>

{% endhighlight %}

![](Customization_images/Customization_img4.png)


### Border Brush

You can able to customize the border color of the treemap using the property `BorderBrush`. 

{% highlight CSHTML %}

<ej:tree-map id="treemap" border-brush="white">
</ej:tree-map>

{% endhighlight %}

### Border Thickness

For customizing the border thickness of the treemap, you can use the `BorderThickness` property.

{% highlight CSHTML %}

 <ej:tree-map  id="treemap" border-thickness="1">
 </ej:tree-map>

{% endhighlight %}

## Dock Position

You can position the legend at top, bottom, left and right side of the treemap as per your requirement. For changing the position as per your requirement, you can use `DockPosition` property.

<ts name="ej.datavisualization.TreeMap.DockPosition"/>
Specifies the dockPosition for legend



{% highlight CSHTML %}

 <ej:tree-map  id="treemap">
    <e-tree-map-legend dock-position="Top"></e-tree-map-legend>
 </ej:tree-map>

{% endhighlight %}

### Clicking and Dragging

You can select the single treemap element on click and drag. To click and drag treemap items, you have to enable the `draggingOnSelection` property.

{% highlight CSHTML %}

<ej:tree-map ID="treemap"  dragging-on-selection="false">
</ej:tree-map>

{% endhighlight %}

For selecting the group element of treemap while clicking and dragging, you can use `draggingGroupOnSelection` property.

{% highlight CSHTML %}

<ej:tree-map ID="treemap" dragging-group-on-selection="false">
</ej:tree-map>

{% endhighlight %}

### Fill with Gradient

You can customize that whether gradient color have to be applied for treemap or not. This can be customized using the property `enableGradient`.

{% highlight CSHTML %}

<ej:tree-map ID="treemap"  enable-gradient="false">
</ej:tree-map>

{% endhighlight %}

### Responsive Treemap

You can customize whether treemap have to be responsive or not while resizing the container. For making treemap responsive you can use `enableResize` or `isResponsive` property.

{% highlight CSHTML %}

<ej:tree-map ID="treemap"  enable-resize="true">
</ej:tree-map>

{% endhighlight %}

### GroupColorMapping

You can customize the color of the each group using `GroupColorMapping` property. To use group color mapping, kindly specify `GroupID` and `RangeColorMapping` inside the `GroupColorMapping`. 

{% highlight CSHTML %}

<ej:tree-map ID="treemap">
    <e-tree-map-group-color-mapping> 
        // ..
    </e-tree-map-group-color-mapping>
</ej:tree-map>
  
{% endhighlight %}

### GroupSelectionMode

You can specifies the selection mode of the treemap using `groupSelectionMode` property. You can set either group selection mode value as `Default` or  `Multiple`. 

{% highlight CSHTML %}

<ej:tree-map ID="treemap"  group-selection-mode="Default">
</ej:tree-map>

{% endhighlight %}

### Header

You can specify the header for the parent item using the property `Header`. This is applicable only for hierarchical data source. 

{% highlight CSHTML %}

<ej:tree-map ID="treemap"  header="Country">
</ej:tree-map>

{% endhighlight %}

### Specifying HierarchicalDatasource

You can specify whether data source bound for the treemap is hierarchical or not using the property `IsHierarchicalDatasource`.

{% highlight CSHTML %}

<ej:tree-map ID="treemap"  is-hierarchical-datasource="true">
</ej:tree-map>

{% endhighlight %}

### Treemap Items

You can specify the treemap items which you want to display in the treemap using the property `TreeMapItems`.

{% highlight CSHTML %}

<ej:tree-map ID="treemap">
    <e-tree-map-items>
        //..
    </e-tree-map-items>
</ej:tree-map>

{% endhighlight %}
