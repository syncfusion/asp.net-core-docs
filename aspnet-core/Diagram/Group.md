---
layout: post
title: Group two or more relevant objects
description: How to group two or more nodes and connectors?
platform: aspnet-core
control: Diagram
documentation: ug
---

# Group

Group is used to cluster multiple nodes and connectors into a single element. It acts like a container for its children (nodes, groups, and connectors). Every change made to the group also affects the children. Child elements can be edited individually. 

## Create Group

### Add group when initializing diagram

You can add a group to the Diagram model through `Nodes` collection. You can create Group like node and you need to add the child objects to the `Children` collection of the group. The following code illustrates how to create a group node.

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-nodes>
        <e-group name="group1">
          <e-children>
            <e-node name="node1" width="100" height="100" offset-x="100" offset-y="100" fill-color="darkCyan" border-width="2">
              <e-labels>
                <e-diagram-label text="Rectangle1"></e-diagram-label>
              </e-labels>
            </e-node>
            <e-node name="node2" width="100" height="100" offset-x="200" offset-y="200" fill-color="darkCyan" border-width="2">
              <e-labels>
                <e-diagram-label text="Rectangle2"></e-diagram-label>
              </e-labels>
            </e-node>
          </e-children>
        </e-group>
      </e-nodes>
    </ej-diagram>
    
{% endhighlight %}

### Add group at run time

You can add a group node at runtime by using the client side method `add`.

The following code illustrates how a group node is added at run time.

{% highlight js %}
var group = {
	name: "group1",
	type: "group",
	children: [{
		name: "rectangle1",
		offsetX: 100,
		offsetY: 100,
		width: 100,
		height: 100,
		type: "node",
		fillColor: "darkCyan",
		borderWidth: 2,
		labels: [{
			text: "rectangle1"
		}]
	}, {
		name: "rectangle2",
		offsetX: 200,
		offsetY: 200,
		width: 100,
		height: 100,
		type: "node",
		fillColor: "darkCyan",
		borderWidth: 2,
		labels: [{
			text: "rectangle2"
		}]
	}]
};

var diagram = $("#DiagramContent").ejDiagram("instance");
// Adds group to the Diagram.
diagram.add(group);
{% endhighlight %}

### Group from palette

Group nodes can be predefined and added to symbol palette. You can drop those groups into Diagram, when required.

To explore how to add groups from symbol palette, refer to [Symbol Palette](/aspnetmvc/Diagram/Symbol-Palette "Symbol Palette")

## Container

Containers are used to automatically measure and arrange the size and position of the child elements in a predefined manner.
There are two types of containers available.

### Canvas

* The Canvas panel supports absolute positioning and provides the least layout functionality to its contained Diagram elements. 
* Canvas allows you to position its contained elements by using margin and alignment properties.
* It allows elements to be either vertically or horizontally aligned.

The `Container` property of group should be defined and its `Type` should be set as `Canvas` to create a canvas panel. The following code illustrates how to add a canvas panel.

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-nodes>
        <e-group name="canvas" offset-x="400" offset-y="400" fill-color="#E7EBF4" padding-bottom="30" padding-left="30" padding-right="30" padding-top="30">
          <e-container type="Canvas"></e-container>
          <e-children>
            <e-node name="node1" width="100" height="100" fill-color="darkCyan" margin-top="0" margin-left="0"></e-node>
            <e-node name="node2" width="100" height="100" fill-color="white"  margin-top="30" margin-left="30"></e-node>
            <e-node name="node3" width="100" height="100" fill-color="darkCyan" margin-top="60" margin-left="60"></e-node>
            <e-node name="node4" width="100" height="100" fill-color="white" margin-top="90" margin-left="90"></e-node>
          </e-children>
        </e-group>
      </e-nodes>
    </ej-diagram>

{% endhighlight %}

![](Group_images/Group_img9.png)

### Stack

* Stack panel is used to arrange its children in a single line or stack order, either vertically or horizontally.
* It controls spacing by setting margin properties of child and padding properties of group. By default, a Stack Panel’s `Orientation` is vertical. 

The `Container` property of group should be defined and its `Type` should be set as `Stack` to create a canvas panel The following code illustrates how to add a stack panel.

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-nodes>
        <e-group name="stack" offset-x="600" offset-y="200" fill-color="#E7EBF4"  min-height="300" min-width="300">
          <e-container type="Stack"></e-container>
          <e-children>
            <e-node name="node1" width="100" height="100" fill-color="darkCyan" horizontal-align="Left"></e-node>
            <e-node name="node2" width="100" height="100" fill-color="darkCyan" horizontal-align="Right"></e-node>
            <e-node name="node3" width="100" height="100" fill-color="darkCyan" horizontal-align="Stretch"></e-node>
          </e-children>
        </e-group>
      </e-nodes>
    </ej-diagram>

{% endhighlight %}

![](Group_images/Group_img10.png)

## Difference between a basic group and containers

| Group | Container |
|---|---|
| It arranges the child elements based on the child elementâ??s position and size properties. | Each container has a predefined behaviour to measure and arrange its child elements. Canvas and stack containers are supported in the Diagram. |
| Padding, Min and Max Size properties are not applicable for basic group. | It is applicable for container. |
| Children's margin and alignment properties are not applicable for basic group. | It is applicable for container. |

## Interaction

You can edit the group and its children at runtime. For more information about how to interact with a group, refer to [Edit Groups](/aspnetmvc/Diagram/Interaction#selection "Interaction").