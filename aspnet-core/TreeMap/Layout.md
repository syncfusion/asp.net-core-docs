---
layout: post
title: Layout in treeMap control
description: Learn how to apply the layout in treeMap control
platform: aspnet-core
control: TreeMap
documentation: ug
---

# Layout

You can decide on the visual representation of nodes belonging to all the treemap levels using the `ItemsLayoutMode` property of the TreeMap.

There are four different TreeMap layouts such as

* Squarified Layout
* SliceAndDiceAuto Layout
* SliceAndDiceHorizontal Layout
* SliceAndDiceVertical Layout

## Squarified Layout

`Squarified layout` creates rectangles with best aspect ratio.

{% highlight CSHTML %}

	<ej-tree-map id="treemap" datasource="ViewBag.datasource" weight-value-path="Population" color-value-path="Growth" items-layout-mode="Squarified">
		<e-levels><e-level group-path="Continent" group-gap="5"></e-level></e-levels>
	</ej-tree-map>

{% endhighlight %}

![](Layout_images/Layout_img1.png)

## SliceAndDiceAuto Layout

`SliceAndDiceAuto` layout creates rectangles with high aspect ratio and displays them sorted both horizontally and vertically.

{% highlight CSHTML %}

	<ej-tree-map id="treemap" datasource="ViewBag.datasource" weight-value-path="Population" color-value-path="Growth" items-layout-mode="SliceAndDiceAuto">
		<e-levels><e-level group-path="Continent" group-gap="5"></e-level></e-levels>
	</ej-tree-map>

{% endhighlight %}

![](Layout_images/Layout_img2.png)

## SliceAndDiceHorizontal Layout

`SliceAndDiceHorizontal` layout creates rectangles with high aspect ratio and displays them sorted horizontally.

{% highlight CSHTML %}

	<ej-tree-map id="treemap" datasource="ViewBag.datasource" weight-value-path="Population" color-value-path="Growth" items-layout-mode="SliceAndDiceHorizontal">
		<e-levels><e-level group-path="Continent" group-gap="5"></e-level></e-levels>
	</ej-tree-map>

{% endhighlight %}

![](Layout_images/Layout_img3.png)

## SliceAndDiceVertical Layout

`SliceAndDiceVertical` layout creates rectangles with high aspect ratio and displays them sorted vertical.

{% highlight CSHTML %}

	<ej-tree-map id="treemap" datasource="ViewBag.datasource" weight-value-path="Population" color-value-path="Growth" items-layout-mode="SliceAndDiceVertical">
		<e-levels><e-level group-path="Continent" group-gap="5"></e-level></e-levels>
	</ej-tree-map>

{% endhighlight %}

![](Layout_images/Layout_img4.png)