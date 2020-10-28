---
layout: post
title: Stacked Header | TreeGrid | ASP.NET Core | Syncfusion
description: stacked header
platform: aspnet-core
control: TreeGrid
documentation: ug
---

# Stacked Headers

The stacked headers helps you to group the logical columns in treegrid. It can be shown by setting `ShowStackedHeader` as `true` and by defining `StackedHeaderRows`.

## Adding Stacked header columns

To stack columns in stacked header, you need to define `Column` property in `StackedHeaderColumns` with field names of visible columns.

{% highlight CSHTML %}

<ej-tree-grid id="TreeGridControl" show-stacked-header="true" >
            <e-tree-grid-columns>
                <e-tree-grid-column headerText="S.No" field="ID" width="45" />
                <e-tree-grid-column headerText="Shipment Name" field="Name" />
                <e-tree-grid-column headerText="Category" field="Category" />
                <e-tree-grid-column headerText="Units" field="Units" />
                <e-tree-grid-column headerText="Unit Price($)" field="UnitPrice" />
                <e-tree-grid-column headerText="Price($)" field="Price" />
            </e-tree-grid-columns>            
            <e-tree-grid-stacked-header-rows>
                <e-tree-grid-stacked-header-row>
                    <e-tree-grid-stacked-header-columns>
                        <e-tree-grid-stacked-header-column column="ID,Name,Category,Units" header-text="Shipment Details" text-align="center" />
                        <e-tree-grid-stacked-header-column column="UnitPrice,Price" header-text="Price Details" text-align="center"  />
                    </e-tree-grid-stacked-header-columns>
                </e-tree-grid-stacked-header-row>
            </e-tree-grid-stacked-header-rows>
        </ej-tree-grid>

{% endhighlight %}

![](Stacked-header_images/Stacked-Header-img1.png)

## Stacked header column customization

we can customize the stacked header cells with more options as described below.

### CSS Class

You can provide external CSS styles to the stacked header with the help of `CssClass` property.

{% highlight CSHTML %}

<style>
  .stack {
            background-color: #ffb3b3; 
        }
</style>

 <ej-tree-grid id="TreeGridControl" show-stacked-header="true">
            <e-tree-grid-stacked-header-rows>
                <e-tree-grid-stacked-header-row>
                    <e-tree-grid-stacked-header-columns>
                        <e-tree-grid-stacked-header-column column="ID,Name,Category,Units" header-text="Shipment Details" css-class="stack" />
                        <e-tree-grid-stacked-header-column column="UnitPrice,Price" header-text="Price Details"  />
                    </e-tree-grid-stacked-header-columns>
                </e-tree-grid-stacked-header-row>
            </e-tree-grid-stacked-header-rows>
        </ej-tree-grid>
{% endhighlight %}
![](Stacked-header_images/Stacked-Header-img2.png)

### Text Align

There is an option to align the stacked header text inside the header cell using `TextAlign` property as follows.

{% highlight CSHTML %}
 <ej-tree-grid id="TreeGridControl" show-stacked-header="true">
            <e-tree-grid-stacked-header-rows>
                <e-tree-grid-stacked-header-row>
                    <e-tree-grid-stacked-header-columns>
                        <e-tree-grid-stacked-header-column column="ID,Name,Category,Units" header-text="Shipment Details" text-align="left"  />
                        <e-tree-grid-stacked-header-column column="UnitPrice,Price" header-text="Price Details" text-align="right"  />
                    </e-tree-grid-stacked-header-columns>
                </e-tree-grid-stacked-header-row>
            </e-tree-grid-stacked-header-rows>
        </ej-tree-grid>
{% endhighlight %}

![](Stacked-header_images/Stacked-Header-img4.png)

### Tooltip

We can have the customized tooltip for the stacked header text with the help of `ToolTip` property. JsRender template script id can be assigned to this property to get tooltip.

{% highlight html %}
<ej-tree-grid id="TreeGridControl" show-stacked-header="true" show-grid-cell-tooltip="true">
            <e-tree-grid-stacked-header-rows>
                <e-tree-grid-stacked-header-row>
                    <e-tree-grid-stacked-header-columns>
                        <e-tree-grid-stacked-header-column column="ID,Name,Category,Units" header-text="Shipment Details"  />
                        <e-tree-grid-stacked-header-column column="UnitPrice,Price" header-text="Price Details" toolTip="#tooltip"  />
                    </e-tree-grid-stacked-header-columns>
                </e-tree-grid-stacked-header-row>
            </e-tree-grid-stacked-header-rows>
        </ej-tree-grid>
<script id="tooltip" type="text/x-jsrender">
        <div>Custom Tooltip</div>
</script> 

{% endhighlight %}

![](Stacked-header_images/Stacked-Header-img3.png)

N>
To enable stacked header tooltip we need to set `ShowGridCellTooltip` as `true`.
