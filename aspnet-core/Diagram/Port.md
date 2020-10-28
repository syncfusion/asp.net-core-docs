---
layout: post
title: Create custom connection points to draw connections with any specific point of node
description: How to draw connections with specific points of node?
platform: aspnet-core
control: Diagram
documentation: ug
---

# Port

Essential Diagram for JS provides support to define custom ports for making connections.

![](Port_images/Port_img3.png)

When a connector is connected between two nodes, its end points are automatically docked to node's nearest boundary as shown in the following image. 

![](Port_images/Port_img4.png)

Ports act as the connection points of node and allows to create connections with only those specific points as shown in the following image.

![](Port_images/Port_img5.png)

## Create Port

### Add ports when initializing nodes

To add a connection port, you need to define the port object and add it to node's `Ports` collection. The `Offset` property of port accepts an object of fractions and used to determine the position of ports. The following code illustrates how to add ports when initializing the node.

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-nodes>
        <e-node name="node1" width="100" height="100" offset-X="250" offset-Y="250" fill-color="darkcyan" border-width="2">
          <e-ports>
            <e-port name="port1">
              <e-offset x="0" y="0.5f"></e-offset>
            </e-port>
          </e-ports>
        </e-node>  
      </e-nodes>
    </ej-diagram>

{% endhighlight %} 

### Add ports at runtime

You can add ports at runtime by using the client side method `addPorts`. The following code illustrates how to add ports to node at runtime.

{% highlight js %}

    // Defines a collection of ports that have to be added at runtime
    var ports = [
        {
            name: "port1",
            // Specifies the port offset – fraction value relative
            to node bounds – determines the position of port on node
            offset: {	
                x: 0,	
                y: 0.5
            }
        },
        { name: "port2",offset: {x: 1,y: 0.5 }},
        { name: "port3",offset: {x: 0.5,y: 0 }},
        { name: "port4",offset: {x: 0.5,y: 1 }}
    ];

    // Gets the instance for the Diagram
    var diagram = $("#diagram").ejDiagram("instance");
    // Adds the ports to the node of name "node"
    diagram.addPorts("node", ports)

{% endhighlight %}

![](Port_images/Port_img1.png)

To explore the set of properties for defining a port, refer to [Port Properties](http://help.syncfusion.com/cr/aspnetmvc/Syncfusion.JavaScript.DataVisualization.Models.Diagram.Port.html  "Port Properties")

### Update Port at runtime

The client side API `updatePort` is used to update the ports at run time. The following code example illustrates how to change the port properties.

{% highlight js %}

    var diagram = $("#diagram").ejDiagram("instance");
    var selectedObject = diagram.model.selectedItems.children[0];
    var visibility = ej.datavisualization.Diagram.PortVisibility.Visible;
    diagram.updatePort(selectedObject.name, selectedObject.ports[0], { fillColor: "red", visibility: visibility });

{% endhighlight %}

## Connect with ports

Connector’s `SourcePort` and `TargetPort` properties allow to create connections between some specific points of source/target nodes. 
For more information about creating connections with port, refer to [Connections with ports](/aspnet-core/Diagram/Connector#connections-with-ports "Connections with ports")

## Appearance 

You can change the shape of port by using its `Shape` property. To explore the different types of port shapes, refer to [Port Shapes](https://help.syncfusion.com/cr/aspnetmvc/Syncfusion.JavaScript.DataVisualization.Models.Diagram.Port.html#Syncfusion_JavaScript_DataVisualization_Models_Diagram_Port_Shape "Port Shapes").
The appearance of ports can be customized with a set of style specific properties. 

The following code illustrates how to change the appearance of port.

{% highlight razor %}

    <ej-diagram id="diagram" width="900px" height="600px">
      <e-nodes>
        <e-node name="node1" width="100" height="100" offset-X="250" offset-Y="250" fill-color="darkcyan" border-width="2">
          <e-ports>
            <e-port name="port1" shape="Circle" fill-color="yellow" visibility="Visible" size="12" border-color="black" border-width="2">
              <e-offset x="1" y="0.5f"></e-offset>
            </e-port>
          </e-ports>
        </e-node>  
      </e-nodes>
    </ej-diagram>

{% endhighlight %}

![](Port_images/Port_img2.png)

## Constraints

The `Constraints` property allows to enable/disable certain behaviors of ports. For more information about port constraints, refer to [Port Constraints](/aspnet-core/Diagram/Constraints#portconstraints)