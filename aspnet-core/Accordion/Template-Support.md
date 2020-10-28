---
layout: post
title: Template Support | Accordion  | ASP.NET Core | Syncfusion
description: Syncfusion Accordion control has a template for its header and its content. It is used to customize the overall look and layout of a site.
platform: aspnet-core
control: Accordion 
documentation: ug
---

# Accordion Template support

The Content template option provided here is used to specify the HTML elements inside the Accordion control. You can use this option to load any HTML elements and display it in the Accordion panels as per your requirement.

The following code example explains how to use content template option in the Accordion control.

{% highlight CSHTML %}

<div style="width:500px;">
    <ej-accordion id="basicAccordion" enable-multiple-open="true">
        <e-accordion-items>
            <e-accordion-item text="GARDEN FRESH (Veg)">
                <e-content-template>
                   <div>
                    <img src="~/Content/accordion/garden-veggie.png" alt="garden-fresh" />
                      <div class="ingredients">
                        Rate    : $50
                        <br />
                        Ingredients : cheese, onions, green capsicums & tomatoes.
                    </div>
                </div>
                </e-content-template>
            </e-accordion-item>
            <e-accordion-item text="CORN & SPINACH (Veg)">
                <e-content-template>
                    <div>
                        <img src="~/Content/accordion/corn-and-spinach-05.png" alt="garden-fresh" />
                        <div class="ingredients">
                            Rate    : $70
                            <br />
                            Ingredients : cheese, sweet corn & green capsicums.
                        </div>
                    </div>
                </e-content-template>
            </e-accordion-item>
            <e-accordion-item text="CHICKEN DELITE (Non-veg)">
                <e-content-template>
                    <div>
                        <img src="~/Content/accordion/chicken-delite.png" alt="garden-fresh" />
                        <div class="ingredients">
                            Rate    : $100
                            <br />
                            Ingredients : cheese, chicken chunks, onions & pineapple chunks.
                        </div>
                    </div>
                </e-content-template>
            </e-accordion-item>
            <e-accordion-item text="KEEMA LA JAWAB (Non-veg)">
                <e-content-template>
                    <div>
                        <img src="@Url.Content("~/Images/accordion/chicken-delite.png")" alt="garden-fresh" />
                        <div class="ingredients">
                            Rate    : $95
                            <br />
                            Ingredients : lamb keema, onions, garlic & tandoori seasoning.
                        </div>
                    </div>
                </e-content-template>
            </e-accordion-item>
        </e-accordion-items>
    </ej-accordion>
</div>

{% endhighlight %}

Output:

![Customizing the layout using template option in asp net core accordion](Template-Support_images/Template-Support_img1.png)