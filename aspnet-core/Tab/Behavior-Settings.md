---
layout: post
title: Behavior Settings | Tab  | ASP.NET Core | Syncfusion
description: behavior settings
platform: aspnet-core
control: Tab 
documentation: ug
---

# Behavior Settings

## Close button

By default, the tab contents are rendered without the CloseButton. You can add the CloseButton by setting the **ShowCloseButton** property to true. The CloseButton is displayed when the cursor moves over the tab headers.

The following code example is used to render the tab widget with CloseButton.

1. Add the following code in your view page for simple tab creation with CloseButton.

{% highlight CSHTML %}
   
// Add the following code example to the corresponding CSHTML page to render the tab with close button.

<div style="width: 500px">

    <ej-tab id="tabSample" show-close-button="true">
        <e-tab-items>
            <e-tab-item id="pizzatype" text="Pizza Type">
                <e-content-template>
                    <div>
                        Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
                    </div>
                </e-content-template>
            </e-tab-item>
            <e-tab-item id="sandwichtype" text="Sandwich Type">
                <e-content-template>
                    <div>
                        Sandwich cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
                    </div>
                </e-content-template>
            </e-tab-item>
        </e-tab-items>
    </ej-tab>

</div>

{% endhighlight %}

2. The following screenshot illustrates the tab with CloseButton.

![](Behavior-Settings_images/Behavior-Settings_img1.png)


## Orientation

By default, the tab control is rendered in horizontal orientation. You can change the orientation to vertical by using the **HeaderPosition** property. Use this property to customize the header in Top, Bottom, Left, and Right position.

The following code example is used to render the sub tab widget in the vertical orientation.

1. Add the following code in your view page for tab orientation.

{% highlight CSHTML %}
   
// Add the following code example to the corresponding CSHTML page to render the tab with customized orientation.

<div style="width: 500px">

    <ej-tab id="tabSample" header-position="@HeaderPosition.Left" height="220px">
        <e-tab-items>
            <e-tab-item id="pizzatype" text="Pizza Type">
                <e-content-template>
                    <div>
                        Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
                    </div>
                </e-content-template>
            </e-tab-item>
            <e-tab-item id="sandwichtype" text="Sandwich Type">
                <e-content-template>
                    <div>
                        Sandwich cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
                    </div>
                </e-content-template>
            </e-tab-item>
        </e-tab-items>
    </ej-tab>

</div>

{% endhighlight %}

2. The following screenshot illustrates the sub tab with vertical orientation.

![](Behavior-Settings_images/Behavior-Settings_img2.png)

## State maintenance

When the page gets refreshed or reloaded, the tab state is changed (i.e.) the focus is moved to the start tab. You can maintain the state of the tab by using the **EnablePersistence** property. When this property is set to true, it retains the state.

The following code example is used to render the tab widget with state maintenance.

1. Add the following code in your view page for tab state maintenance.

{% highlight CSHTML %}

// Add the following code example to the corresponding CSHTML page to render the tab with state maintenance.

<div style="width: 500px">

    <ej-tab id="tabSample" enable-persistence="true">
        <e-tab-items>
            <e-tab-item id="pizzatype" text="Pizza Type">
                <e-content-template>
                    <div>
                        Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
                    </div>
                </e-content-template>
            </e-tab-item>
            <e-tab-item id="sandwichtype" text="Sandwich Type">
                <e-content-template>
                    <div>
                        Sandwich cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.
                    </div>
                </e-content-template>
            </e-tab-item>
        </e-tab-items>
    </ej-tab>

</div>

{% endhighlight %}
   
2. The following screenshot illustrates the tab with state maintenance.

![](Behavior-Settings_images/Behavior-Settings_img3.png)

State before page refresh

{:.caption}

![](Behavior-Settings_images/Behavior-Settings_img4.png)