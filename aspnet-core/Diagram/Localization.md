---
layout: post
title: Globalize and Localize the Diagram control
description: How to globalize and localize the Diagram control?
platform: ejmvc
control: Diagram
documentation: ug
---

# Localization

* Localization is the process of providing controls in different cultures to help you set your own culture easily. Diagram provides localization support for Context Menu items.
* The Diagram model’s `Locale` property is used to define the culture code. 

The following code illustrates how to provide localization support for Context Menu items.

{% tabs %}
{% highlight razor %}

      ej.datavisualization.Diagram.Locale["es-ES"] = {
                  cut: "Corte",
                  copy: "Copia",
                  paste: "Pasta",
                  undo: "Deshacer",
                  redo: "Rehacer",
                  selectAll: "Seleccionar todo",
                  grouping: "Agrupaci�n",
                  group: "Grupo",
                  ungroup: "Desagrupar",
                  order: "Fin",
                  bringToFront: "Traer a delante",
                  moveForward: "Movimiento adelante",
                  sendToBack: "Enviar a espalda",
                  sendBackward: "Enviar hacia atr�s"

            };
{% endhighlight %}

{% highlight c# %}

            <e-flow-shape name="Rect1" width="100" height="100" offset-X="300" offset-Y="155" fill-color="#1BA0E2" border-color="#1BA0E2" shape="@FlowShapes.Process">
                  <e-labels>
                        <e-diagram-label name="Rect1_Label" text="Rectangle1" font-color="White"></e-diagram-label>
                  </e-labels>
                  </e-flow-shape>

                  <e-flow-shape name="Rect2" width="100" height="100" offset-X="500" offset-Y="155" fill-color="#1BA0E2" border-color="#1BA0E2" shape="@FlowShapes.Process">
                  <e-labels>
                        <e-diagram-label name="Rect2_Label" text="Meeting with board" font-color="White"></e-diagram-label>
                  </e-labels>
                  </e-flow-shape> 

      <e-connector name="Connector1" source-node="Rect1" target-node="Rect2" line-color="#606060" >                                                    
                  </e-connector>

                  model.locale = "es-ES";


{% endhighlight %}

{% endtabs %}

![](Localization_images/Localization_img1.png)

N> You have to define the textual descriptions of the context menu items for your custom cultures.